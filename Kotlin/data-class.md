# Data classes
Kotlin의 data 클래스는 데이터를 보유하는 것이 목적인 클래스다.
data 클래스 사용은 class 앞에 data 키워드를 붙이면 된다.

``` kotlin
data class Person(
    val id: Long
)
```

data 클래스로 선언하면 기본 생성자(Primary Constructor)에 선언된 프로퍼티에 대해서 `toString()`, `hashCode()`, `equals()`, `copy()`를 자동으로 생성해준다.

data 클래스는 다음과 같은 특징을 가지고 있다.
- 기본 생성자에는 매개변수가 하나 이상 있어야 한다.
- 모든 기본 생성자 매개변수는 val 또는 var로 표시되어야 한다.
- data 클래스는 abstract, open, sealed, inner 키워드를 붙일 수 없다.
- `toString()`, `hashCode()`, `equals()`를 개발자가 명시적으로 재구현하면, 컴파일러는 재구현된 함수는 자동으로 만들어주지 않는다.
