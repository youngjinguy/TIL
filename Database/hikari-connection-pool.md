# HikariCP

HikariCP(Connection Pool)는 JDBC Connection Pool 종류 중 하나이다.

[HikariCP 벤치 마크](https://github.com/brettwooldridge/HikariCP#checkered_flag-jmh-benchmarks)를 참조하면 다른 Connection Pool에 비해
성능이 월등히 좋다는 것을 알 수 있다.

Spring Boot 2.0 이전에는 tomcat-jdbc pool을 사용했지만 Spring Boot 2.0 이후부터는 기본 Connection Pool로 사용되고 있다.

## JDBC?
JDBC(Java Database Connectivity)는 자바로 구현된 프로그램이 데이터베이스와 상호 작용하기 위해 구현된 표준 인터페이스이다.

JDBC를 사용하면 데이터베이스에 연결하고 쿼리를 실행하는 등의 작업을 수행할 수 있다.

## Connection Pool?
자바 프로그램에서 데이터베이스에 접속하기 위해서는 JDBC를 통해 Connection을 가져와야 한다.

데이터베이스에 접근할 때마다 Connection을 생성한다면 시간이 오래걸린다는 문제가 있다.

예를 들어서 동시 접속자수가 1000명이라고 가정하고 1000명이 모두 데이터베이스에 접근해야 하는 서비스를 사용하고 있다면 1000번의 Connection을 생성해야 한다.

이런 문제를 해결하기 위해 Connection을 미리 만들어 놓고 사용하는 방법이 고안되었고, 이 개념이 Connectino Pool이다.

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
