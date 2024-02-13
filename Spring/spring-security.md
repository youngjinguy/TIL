# Spring Security
## SecurityBuilder & SecurityConfigurer
`SecurityBuilder`는 웹 보안을 구성하는 빈 객체와 설정 클래스들을 생성하는 역할을 하며, WebSecurity, HttpSecurity 가 있다.

`SecurityConfigurer`는 Http 요청과 관련된 보안을 담당하는 필터들을 생성하고 초기화 설정에 관여한다.

`SecurityBuilder`는 `SecurityConfigurer`를 포함하고 있다. 인증 및 인가 작업은 `SecurityConfigurer`에 의해 진행된다.

### WebSecurity
`SecurityFilterChain`을 거치지 않기 때문에 인증과 인가를 거치지 않는다.

즉 인증,인가 서비스가 필요하지 않는 정적파일에 대한 접근을 관리할 때 주로 사용된다.

우선 순위는 `HttpSecurity` 보다 높아서, `WebSecurity`가 먼저 동작한다.

### HttpSecurity
인증,인가에 대한 것을 관리하고, Http 요청과 관련된 보안 설정을 할 수 있다. 

URL 패턴, 권한, CORS, CSRF와 같은 설정이 예시이다.

## FilterChainProxy

## SecurityFilterChain
