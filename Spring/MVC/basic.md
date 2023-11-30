# Spring MVC

[Spring MVC](https://docs.spring.io/spring-framework/reference/web/webmvc.html)는 Servlet API 기반으로 만들어진 Spring 웹 모듈이다.
정식 명칭은 Spring Web MVC (spring-webmvc) Spring MVC 라고 부른다.

## Servlet?
Servlet은 자바를 사용하여 웹페이지를 동적으로 생성하는 서버측 프로그램 혹은 그 사양을 말한다. Servlet은 웹 서버의 성능을 향상하기 위해 사용되는 자바 클래스의 일종이다.

Java Servlet은 자바 EE 사양의 일부분으로, 주로 이 기능을 이용하여 다양한 웹 시스템을 구현한다.

## MVC?
MVC는 소프트웨어를 개발 할 때 적용하는 디자인 패턴 중 하나이다. Model, View, Controller 세 단어의 약자이다.

이 패턴은 관심사를 나누어 Model의 역할은 비즈니스 로직(데이터 등등)을, View는 사용자에게 보여지는 부분, 즉 사용자 인터페이스에 관심을 둔다. Controller은 Model과 View 사이를 연결해주는 역할을 담당하고 있다.

## DispatcherServlet
Spring MVC는 DispatcherServlet이 프론트 컨트롤러 역할을 하고, 실제 요청에 대한 작업은 위임 가능한 컴포넌트들이 처리한다. 이런 위임 가능한 컴포넌트들을 (Special Bean Types)[https://docs.spring.io/spring-framework/reference/web/webmvc/mvc-servlet/special-bean-types.html]라고 부른다.

HandlerMapping
HandlerAdapter




