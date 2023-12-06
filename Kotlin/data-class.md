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

## Destructuring declarations
data 클래스는 Destructuring declarations 지원한다.
data 클래스는 컴파일 시 기본적으로 componentN() 함수가 생성된다. 그래서 각 속성에 번호가 붙어 Destructuring 가능하다.

``` kotlin
data class Person(
    val id: Long,
    val name: String,
)

val person = Person(id = 1L, name = "Kim")
val (id, name) = person
println("id: $id, name: $name")
// id: 1, name: Kim
```

여기서 주의해야할 점은 속성의 순서대로 변수에 할당 된다는 점이다. 속성명을 똑같이 쓴다고해서 속성명의 값이 변수에 할당된다고 생각하면 안된다. 아래 예제를 참고하자.

```kotlin
data class Person(
    val id: Long,
    val name: String,
)

val person = Person(id = 1L, name = "Kim")
val (name, id) = person
println("id: $id, name: $name")
// id: Kim, name: 1
```

Underscore를 사용하면 특정 변수를 무시 가능하다
``` kotlin
data class Person(
    val id: Long,
    val name: String,
)

val person = Person(id = 1L, name = "Kim")
val (name) = person
println("name: $name")
// name: 1

val (_, name) = person
println("name: $name")
// name: Kim
```

# 정리
- data 클래스를 활용하면 Boilerplate code(반복적으로 작성하는 코드)를 줄일 수 있다.
- `toString()`, `hashCode()`, `equals()`를 자동으로 생성해주고, `copy()` 함수를 사용할 수 있다.
- `toString()`, `hashCode()`, `equals()` 함수를 명시하면 명시된 코드의 우선순위가 높다.
- data 클래스는 Destructuring declarations 지원하지만 사용 시 변수의 속성에 맞게 선언하여 사용해야 한다. 
- 특정 변수를 무시하고 싶으면 Underscore(_)로 변수를 선언하면 된다.
