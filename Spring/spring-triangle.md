# Spring 3대 요소 (Spring 삼각형)

`Spring Framework`의 핵심 3대 요소라고 불리는 것이 있다.
DI/IOC, AOP, PSA 세가지가 바로 그것이다.

## DI(Dependency Injection) 와 IoC(Inversion Of Control)

DI는 의존성 주입이다. 쉽게 얘기해서 객체를 외부에서 주입을 받는다는 것이고, 이를 통해 객체간의 결합도를 줄일수 있다.

DI의 방법은 여러가지가 있는데, 생성자 주입, 필드 주입, Setter 주입이 대표적이다. 스프링에서는 생성자 주입을 권장한다. setter 같은 경우에는 생성자로 주입받지 않아도 객체 생성이 가능한데, 그렇게되면 생성된 객체가 제대로 동작하지 않을수 있기 때문이다.

IoC는 제어의 역전이라는 뜻. 일반적으로 객체 안에서 다른 객체를 생성하고 사용한다고 하면 이것을 일반적인 제어권이라고 한다. 하지만 DI는 객체 생성 자체를 외부에서 해주기 때문에 제어권이 역전되었다고 얘기할 수 있다.

## AOP(Aspect Oriented Programming)

단어의 뜻대로 보면 관점 지향적 프로그래밍이다.

관심사를 하나로 모아서 비즈니스로직과 분리하여 재사용한다는 하겠다는 것이 AOP의 컨셉
스프링에서 대표적으로 @Transational이 있다.

## PSA(Portable Service Abstraction)

일관성있는 서비스 추상화. 환경과 기술의 변화에 관계 없이 일관된 방식으로 기술을 사용 할 수 있도록 하는 것.

대표적인 예로는 JDBC가 있다. 스프링에서는 다양한 어댑터를 이용하여 서비스 추상화를 하였다. 
