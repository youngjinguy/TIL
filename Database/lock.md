# Lock

Lock은 여러 트랜잭션이 동시에 데이터베이스의 일부를 읽거나 쓰는 동작을 수행할 때 데이터 일관성을 보장하기 위해 사용되는 메커니즘이다. Lock은 특정 데이터나 테이블에 대한 접근을 동시에 하나의 트랜잭션에만 허용하고, 다른 트랜잭션들은 해당 데이터나 테이블에 대한 접근을 대기해야 한다. Database Lock은 크게 두 가지로 나뉘는데, Shared Lock(공유 락), Exclusive Lock(배타적 락)으로 나뉜다.

## Shared Lock
Shared Lock은 여러 트랜잭션이 동시에 읽기 작업을 할 때 사용된다. 하나의 트랜잭션이 공유 락을 획득하면, 다른 트랜잭션들도 동시에 같은 데이터에 대한 읽기 작업을 수행할 수 있다. 즉 하나의 데이터를 여러 사용자가 읽을 수 있다는 뜻이다. 

하지만 Shared Lock 걸려 있는 데이터에 대해서는 Exclusive Lock(배타적 락)을 걸 수 없다. 다시 말해 읽고 있는 데이터를 업데이트하려고 한다면, 먼저 걸려 있던 Shared Lock이 종료되고 Exclusive Lock을 획득한 후에 업데이트를 진행할 수 있다.

## Exclusive Lock
Exclusive Lock은 특정 데이터에 대한 쓰기 작업을 할 때 사용된다. 하나의 트랜잭션이 Exclusive Lock을 획득하면, 다른 트랜잭션들은 해당 데이터에 대한 어떠한 락도 획득할 수 없다. 이는 쓰기 작업 간에 충돌을 방지하고 데이터의 무결성을 유지하는 데 사용된다.

# 정리
- Lock은 데이터의 무결성과 일관성을 지키기 위해 사용한다.
- Shared Lock은 읽기 전용 Lock이다. Shared Lock끼리는 서로 읽기가 가능하다.
- Exclusive Lock은 데이터를 변경하고자 할 때 사용하는 Lock이다. Exclusive Lock이 걸려 있으면 어떤 Lock도 얻을 수 없다.
- Shared Lock이 걸려 있는 데이터에 대해서는 Exclusive Lock을 획득할 수 없다.

