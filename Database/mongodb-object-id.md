# MongoDB ObjectId
ObjectId는 MongoDB에서 도큐먼트의 고유 식별자로 사용되는 12바이트 길이를 가진 데이터 형식이다. 12바이트의 구성은 아래와 같다.

- 최초 4바이트는 UNIX timestamp
- 다음 3바이트는 MongoDB를 실행하는 머신의 고유 식별자
- 다음 2바이트는 ObjectId를 생성하는 프로세스의 고유 식별자
- 마지막 3바이트는 ObjectId가 생성될 때마다 증가하는 카운터

이렇게 생성된 ObjectId는 16진수로 저장된다.
``` 
ObjectId("00000020f51bb4362eee2a4d")
```

장점, 단점 정리
