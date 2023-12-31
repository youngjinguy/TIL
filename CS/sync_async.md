# Sync / Async
## 동기(Synchronous)
동기는 작업이 순차적으로 진행된다는 의미이다. Synchronous 단어를 하나 씩 해석해보면, syn는 그리스어로 '함께'라는 뜻이고 chrono는 '시간'이라는 뜻이다.

동기적인 작업에서는 각 작업이 순차적으로 실행되며, 하나의 작업이 완료될 때까지 다음 작업이 시작되지 않습니다. 이는 시간의 순서에 따라 정확한 순서대로 작업이 진행된다는 의미에서 synchronous라는 용어가 사용된다.

## 비동기(Asynchronous)
비동기는 작업의 순서가 보장되지 않는다. Asynchronous 단어를 하나 씩 해석해보면, a는 그리스어에서 부정적인 접두사를 의미한다. 그러므로 A + Synchronous의 조합으로 생각해보면 작업이 순차적으로 진행되지 않는다고 해석 할 수 있다.

다시 말하면, 비동기적인 작업에서는 어떤 작업이 독립적으로 일어나거나 특정한 시간에 종속되지 않고 동작함을 나타낸다.

# 정리
- 동기는 요청한 작업의 완료에 따라 일어나는 순차적인 흐름을 가지고 있다.
- 비동기는 각 작업이 서로 독립적으로 진행되므로 병렬적인 흐름을 가진다.
![sync-async.webp](sync-async.webp "출처: https://medium.com/from-the-scratch/wtf-is-synchronous-and-asynchronous-1a75afd039df")
- 그림과 같이 동기는 호출자(프로세스A)가 호출된 함수(프로세스B)의 작업 완료 여부를 기다리고 있고, 비동기는 호출자(프로세스A)가 호출된 함수(프로세스B)의 작업 완료 여부를 기다리지 않는다.

