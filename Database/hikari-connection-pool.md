# HikariCP

HikariCP(Connection Pool)는 JDBC Connection Pool 종류 중 하나이다.

[HikariCP 벤치 마크](https://github.com/brettwooldridge/HikariCP#checkered_flag-jmh-benchmarks)를 참조하면 다른 Connection Pool에 비해
성능이 월등히 좋다는 것을 알 수 있다.

Spring Boot 2.0 이전에는 tomcat-jdbc pool을 사용했지만 Spring Boot 2.0 이후부터는 기본 Connection Pool로 사용되고 있다.

## 주요 설정 값

| 설정                  | 설명                                                                                                             | 기본값 |
|---------------------|----------------------------------------------------------------------------------------------------------------|-----|
| connectionTimeout   | Pool에서 Connection을 기다리는 최대 시간                                                                                  | 30초 |
| idleTimeout         | Connection이 idle 상태로 유지될 수 있는 최대 시간. 이 시간 동안 Connection을 사용하지 않으면 Pool에서 제거된다.                                 | 10분 |
| keepaliveTime       | Pool이 idle 상태의 Connection을 대상으로 데이터베이스에 헬스 체크를 보내는 주기를 지정하는 옵션                                                 | 0초  |    
| maxLifetime         | Pool에서 관리되는 Connection의 최대 생명 주기                                                                               | 30분 |     
| connectionTestQuery | Pool에서 Connection을 주기전에 데이터베이스와 연결이 되어 있는지 확인 하는 쿼리를 설정. <br/> JDBC 드라이버가 JDBC4를 지원하는 경우 이 속성을  설정하지 않는 것이 좋다. | 없음  |
| maximumPoolSize     | Connection이 Pool에 존재할 수 있는 최대 개수                                                                               | 10개 |     
| minimumIdle         | Pool에서 존재할 수 있는 idle 상태의 Connection 최소 개수. 기본값은 maximumPoolSize와 같다.                                           | 10개 |     

## 참고
- https://techblog.woowahan.com/2664/
- https://velog.io/@miot2j/Spring-DB%EC%BB%A4%EB%84%A5%EC%85%98%ED%92%80%EA%B3%BC-Hikari-CP-%EC%95%8C%EC%95%84%EB%B3%B4%EA%B8%B0
