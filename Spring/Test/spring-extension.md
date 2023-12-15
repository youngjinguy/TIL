# SpringExtension
SpringExtension 클래스는 Spring에서 Junit을 통해 테스트를 쉽게 할 수 있도록 지원해주는 확장 클래스이다.

실제 SpringExtension 클래스를 들어가보면 구현하고 있는 interface는 전부 org.junit.jupiter.api.extension에 위치하고 있다. (spring-test는 junit에 의존적이다.) 

``` java
package org.springframework.test.context.junit.jupiter;

import ...

public class SpringExtension implements BeforeAllCallback, AfterAllCallback, TestInstancePostProcessor, BeforeEachCallback, AfterEachCallback, BeforeTestExecutionCallback, AfterTestExecutionCallback, ParameterResolver {
    ...생략
}
```

SpringExtension 클래스를 JUnit에서 사용하기 위해서는 JUnit의 `@ExtendWith` 어노테이션을 이용하면 된다.

```kotlin
@ExtendWith(SpringExtension::class)
```

## 특징
