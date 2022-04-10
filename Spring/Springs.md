# Spring framework
(TO ME) Spring Legacy Project && Spring MVC Project with Maven

단어적으론 spring legacy prj, spring boot prj, spring cloud prj 등등 모두 해당가능하지만, 이 중 spring legacy prj 만 사용

## Main Features
DI and IoC, AOP, PSA

#### Dependency Injection and Inversion of Control
(TO ME) spring (IoC) container에 의한 의존객체 주입

###### Dependency and How to deal with(IoC)
자바 클래스 간 의존성 이란 ? 현재 클래스 안에 다른 클래스가 new 되어 있는 것, 한편으로는 피할 수 없는 것

의존성로 인해서 다른 클래스가 변동 시 현재 클래스도 다시 컴파일되야 하고, 복잡한 구조에서는 개발 시 변동에 따른 코딩 작업량이 급증하기 좋음

=> 이러한 의존성(또는 의존객체)의 주입을 집중적으로 관리할 새로운 수단이 필요

=> ApplicationContext라는 컨테이너에 의해 '개발자 대신(IoC)' 의존 객체 주입 수행, 이때 컨테이너의 제어를 받는 객체는 '빈(Bean)'이라고 별칭

=> 객체 간 의존성 최소화

=> 테스트 용이, 코드 확장 용이, 순환참조 방지


###### Bean
기존 '객체'로 정의되던 클래스(혹은 인스턴스)들이 Spring IoC Container에 등록저장되어 제어될 경우 '빈(bean)'이라는 개념으로 재정의(혹은 맵핑)된다.

초기 spring의 경우, 개발자가 xml 등을 활용 우선 직접 입력, 혹은 spring boot의 경우 어노테이션 like @Controller 등 을 통해서 등록 

[참고링크](https://atoz-develop.tistory.com/entry/Spring-%EC%8A%A4%ED%94%84%EB%A7%81-%EB%B9%88Bean%EC%9D%98-%EA%B0%9C%EB%85%90%EA%B3%BC-%EC%83%9D%EC%84%B1-%EC%9B%90%EB%A6%AC)

###### container 
'보관'의 의미보단, '울타리'의 의미로!

spring (IoC) container : ex) ApplicationContext_xml 파일 형태로 객체 정보가 bean 태그로 저장

Ex) BeanFactory , ApplicationContext

* context in computer science : the minimal set of data used by a task(which may be a process, thread, or fiber)

[참고링크](https://gmlwjd9405.github.io/2018/11/09/dependency-injection.html)


#### AOP : Aspect Oriented Programming
(TO ME)횡단 관심사를 해결하는것

아래와 같은 프로세스에서 같은 관심사(대표적으로 log 출력)가 반복적으로(cross)하면

process 1 : (=====)|=====================>

process 2 : (=====)|=====================>

process 3 : (=====)|=====================>

반복코드를 모듈화하여 중요한 관심사(core point of Aspect)에 집중하도록 지원하는 것 


위 |(모듈화) 를 일종 인터럽트로 이해하면, 횡단 관심사를 프로세스별로 따로 매번 실행이 아니라,

| 에 의해 만나면 공용을 쓴다는 느낌, 이때 | 는 메소드단위나 클래스단위 등 옵션에 따라 다양한 것으로 보인다.


#### PSA : Portable Service Abstraction


@Transactional 어노테이션만으로 DB 접근의 여러 절차를 자동 지원하게 해주는 스프링 기능

가령, jdbc, jpa는 각각 다른 스텝으로 DB에 접근하나, 스프링 사용 개발자는 (코딩된 숨겨진)스프링 기능을 통해 패스 

[참고링크](https://sabarada.tistory.com/127)

## Appendix
[spring framework and Build Tool : Maven, Gradle](./BuildTool.md)

[spring web layer](./servicelayer.md)