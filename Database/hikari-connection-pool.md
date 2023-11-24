# HikariCP

HikariCP(Connection Pool)는 JDBC Connection Pool 종류 중 하나이다.

[HikariCP 벤치 마크](https://github.com/brettwooldridge/HikariCP#checkered_flag-jmh-benchmarks)를 참조하면 다른 Connection Pool에 비해 성능이 월등히 좋다는 것을 알 수 있다.

Spring Boot 2.0 이전에는 tomcat-jdbc pool을 사용했지만 Spring Boot 2.0 이후부터는 기본 Connection Pool로 사용되고 있다.

## 설정

| 속성             | 설명                          | 기본값 | 추천값 | 
|----------------|-----------------------------|-----|----|
| name           | 식별자 생성기 이름                  | 필수  | |
| sequenceName   | 데이터베이스의 시퀀스 이름              |     | |
| catalog        | 데이터베이스 catalog              |     | |
| schema         | 데이터베이스 스키마                  |     | |
| initialValue   | DDL 생성 시 시작 값               | 1   | |
| allocationSize | 시퀀스에서 시퀀스 번호를 할당 할 때 증가하는 양 | 50  | |

