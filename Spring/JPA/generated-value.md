# @GeneratedValue

JPA Entity 에서 기본 키 생성을 자동으로 해주기 위해서 사용하는 어노테이션이다.
생성 전략은 총 5가지가 있다.

# AUTO

- 데이터베이스 벤더(hibernate.dialect 설정 값)에 따라서 hibernate가 자동으로 전략을 지정합니다.
- hibernate 버전에 따라 AUTO 지정할 경우 키 전략이 다르다. (공식 문서 링크

# IDENTITY

- IDENTITY 전략은 키 생성을 데이터베이스에게 위임합니다.

# SEQUENCE

- 데이터베이스의 시퀀스를 이용하여 키를 생성하는 전략입니다.
- @SequenceGenerator 어노테이션을 이용하여, 시퀀스 생성기를 등록할 수 있습니다.

## @SequenceGenerator

| 속성             | 설명                          | 기본값 | 
|----------------|-----------------------------|-----|
| name           | 식별자 생성기 이름                  | 필수  |
| sequenceName   | 데이터베이스의 시퀀스 이름              |     |
| catalog        | 데이터베이스 catalog              |     |
| schema         | 데이터베이스 스키마                  |     |
| initialValue   | DDL 생성 시 시작 값               | 1   |
| allocationSize | 시퀀스에서 시퀀스 번호를 할당 할 때 증가하는 양 | 50  |

# UUID
-

# TABLE

- TABLE 전략은 시퀀스 대신에 테이블을 이용한다.
- @TableGenerator 어노테이션을 이용하여, 테이블 생성기를 등록할 수 있습니다.

## @TableGenerator

| 속성                | 설명                        | 기본값 | 
|-------------------|---------------------------|-----|
| name              | 식별자 생성기 이름                | 필수  |
| table             | 키 생성 시 사용할 테이블명           |     |
| catalog           | 데이터베이스 catalog            |     |
| schema            | 데이터베이스 스키마                |     |
| pkColumnName      | 키 생성 시 사용할 테이블의 기본 키 컬럼명  |     |
| pkColumnValue     | pkColumnName에서 지정한 컬럼의 값  |     |
| valueColumnName   | ID로 사용할 컬럼                |     |
| initialValue      | DDL 생성 시 시작 값             | 0   |
| allocationSize    | 생성기에서 ID 번호를 할당할 때 증가하는 양 | 50  |
| uniqueConstraints | 유니크 제약 조건                 |     |
| indexes           | 테이블에 추가될 인덱스              |     |
