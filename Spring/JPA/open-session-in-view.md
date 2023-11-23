# OSIV(Open Session In View)

## OSIV란?
Open Session In View를 그대로 번역하자면, Session을 View까지 연다는 의미이다.

## Session이 뭐지?
Session이라는 단어를 사용해서 우리가 흔히 웹에서 사용하는 Session이라고 오해할 수 있지만 여기서의 Session은 Hibernate의 Session(JPA EntityManager 구현체) 이다.

그러므로 Open Session 이라는 것은 Session(EntityManager)을 연다/생성한다의 의미이다.

Session이 생성된다는 것은 Persistence Context(이하 영속성 컨텍스트)가 시작된다는 것을 의미하기도 한다.

## 그래서 OSIV는 뭘까?
정리하자면 Open Session In View 는 영속성 컨텍스트를 View까지 열어둔다(확장한다)는 의미이다.

## 왜 View까지 열어둘까?
우리가 보통 웹 개발 시 서비스로직에 트랜잭션이 필요하다는 의미로 @Transactional 어노테이션을 많이 사용한다.

트랜잭션 시작 시 영속성 컨텍스트는 생성되고, 종료 시 영속성 컨텍스트는 소멸된다.

이 때 만약 View에서 일반적인 데이터 조회는 가능하겠지만, 지연로딩을 할 경우 영속성 컨텍스트 밖에서 이뤄지므로 `LazyInitializationException` 이 발생한다.

## 어떻게 사용하지?
아무 설정을 하지 않으면 기본 설정은 활성화입니다. 하지만 warn 레벨의 로그를 출력해줍니다. 
``` kotlin
public abstract class JpaBaseConfiguration {
    // ...
    @ConditionalOnProperty(prefix = "spring.jpa", name = "open-in-view", havingValue = "true", matchIfMissing = true)
    protected static class JpaWebConfiguration {
    
        @Bean
        public OpenEntityManagerInViewInterceptor openEntityManagerInViewInterceptor() {
            if (this.jpaProperties.getOpenInView() == null) {
                logger.warn("spring.jpa.open-in-view is enabled by default. "
                        + "Therefore, database queries may be performed during view "
                        + "rendering. Explicitly configure spring.jpa.open-in-view to disable this warning");
            }
            return new OpenEntityManagerInViewInterceptor();
        }
    
    // ...
    }
}
```

Spring 설정 파일을 통한 설정 값은 아래와 같습니다.
``` yaml
spring:
  jpa:
    open-in-view: true
```

## 단점은 없을까?
열어 놓고 사용하면 편리하다고 생각할 수 있지만, 단점이 존재한다.
- 영속성 컨텍스트가 View까지 이어지기 때문에 DB 커넥션을 계속 사용된다.
- 영속성 컨텍스트가 끝나지 않았기 때문에 View에서 데이터 조작 후 다시 트랜잭션을 시작하면 데이터가 변경된다.

# 정리
- OSIV란 View까지 영속성 컨텍스트를 유지한다는 의미이다.
- OSIV를 사용하는 이유는 View에서 영속성의 기능을 사용하기 위함이다. (지연 로딩등)
- Spring 설정을 하지 않으면 기본은 활성화이다. 
- 분명한 [단점](#단점은-없을까)들이 존재하기 때문에, 사용할 경우에는 영향도를 생각한 후 사용해야한다.
