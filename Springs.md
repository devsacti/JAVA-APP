# Spring framework
(TO ME) Spring Legacy Project && Spring MVC Project with Maven

단어적으론 spring legacy prj, spring boot prj, spring cloud prj 등등 모두 해당가능하지만, 이 중 spring legacy prj 만 사용

## Main Features
java EE와 같은 플랫폼 상에서 개발된 앱의 경우, (아마)모듈간 높은 결합도 등으로 인해 코딩 분업도 어렵지만, 단일테스트가 어려움

=>느슨한 결합과 테스트 용이성을 위해 Spring이란 프레임워크가 개발되고 아래와같은 특징들이 나타남

#### DI : Dependency Injection

DI : bean은 추상화,상속 등의 특징들을 승계는데, container가 상속이나 타 클래스 내 이종클래스 선언 등의 참조를 '개발자 대신' 수행한다는 개념

=> 객체 간 의존성 최소화 => 테스트 용이, 코드 확장 용이, 순환참조 방지

* bean : 초기 spring의 경우, 개발자가 xml 등을 활용 우선 직접 입력, 혹은 spring boot의 경우 어노테이션 like @Controller 등 을 통해서 등록 
[참고링크](https://atoz-develop.tistory.com/entry/Spring-%EC%8A%A4%ED%94%84%EB%A7%81-%EB%B9%88Bean%EC%9D%98-%EA%B0%9C%EB%85%90%EA%B3%BC-%EC%83%9D%EC%84%B1-%EC%9B%90%EB%A6%AC)


#### IoC : Inversion of Control
IoC : 기존에 개발자가 new를 통해서 Java 객체를 생성 및 제어하던 방식을 벗어나, Java 객체 제어 및 관리를 Spring IoC Container에 모두 전임되어 제어권이 뒤바뀌는 것

한편, 기존 '객체'로 정의되던 클래스(혹은 인스턴스)들이 Spring IoC Container에 등록저장되어 제어될 경우 '빈(bean)'이라는 개념으로 재정의(혹은 맵핑)된다.


###### container ? '보관'의 의미보단, '경계_Border'의 의미로!

기존 객체지향 자바의 추상화,상속를 바탕으로, 주요 객체들을 bean이라는 (어쩌면)더 작은 단위로 모듈화 혹은 캡슐화하여,

'객체1 => 객체2 has 객체1 by 개발자'를

'개발자 make context to access bean2 which is injected bean1 by container'

결과적으로 추상화 실현과 재사용성 향상에 충실

[참조링크](https://gmlwjd9405.github.io/2018/11/09/dependency-injection.html)

* spring (IoC) container : ex) ApplicationContext_xml 파일 형태로 객체 정보가 bean 태그로 저장_, BeanFactory , 

* context in computer science : the minimal set of data used by a task(which may be a process, thread, or fiber)


#### AOP : Aspect Oriented Programming

(의역)monolithic 다층적 관점의 프로그래밍(스프링 프레임워크의 맞춤 MVC 커스텀버전)

![spring web layer](https://user-images.githubusercontent.com/88543657/133958708-4a020612-4bc6-4efc-be65-59803cfdd72b.JPG)

[spring web layer](https://lifelife7777.tistory.com/100)

? Service layer vs Business layer [참고링크](https://docs.microsoft.com/en-us/previous-versions/msp-n-p/ee658090(v=pandp.10)?redirectedfrom=MSDN)

전통 아키텍쳐에서는 분명 독립 개념이나, 서로 인접 개념으로서 현실에서는 구분이 불명확하게 쓰이기 쉽다고 생각

무엇보다 spring에서는 거의 service라는 용어로 종합된 듯함

물론, spring에도 Domain Model에서 비즈니스 로직이 등장하는데, 현재로선 뚜렷하게 그 구분을 체감하기 힘듦

#### PSA : Portable Service Abstraction

(예시)@Transactional 어노테이션만으로 DB 접근의 여러 절차를 자동 지원하게 해주는 스프링 기능

가령, jdbc, jpa는 각각 다른 스텝으로 DB에 접근하나, 스프링 사용 개발자는 (코딩된 숨겨진)스프링 기능을 통해 패스 

## Spring with Build Tool : maven and gradle

(간단) 앱 실행 시 참조되야 하는 방대한 외부파일(ex 의존성들)을 제어/호출하기 위한 파일, pom.xml build.gradle

일반적으로 java 코딩할 때, import를 통해서 다른 ~.java의 정보를 가져온다고 배움

그런데, 앞서 배운 spring 관련 개념들로 볼 때, 상당수의 객체(혹은 빈)들이 더 큰 단위_컨테이너나 DI_로 묶여 있거니와,

앱 구동 시 jvm 등 다른 요소들이 많음

직관적으로 다른 단위의 정보를 좀더 효과적으로 끌어올때, 새로운 효과적인 중심 제어파일이 필요하고 이것이 pom.xml과 build.gradle

## spring framework and build Tool
(TO ME) maven => spring legacy project, gradle => spring boot project

maven vs gradle

공통적으로 빌드툴이란 일종의 'java app 조립 메뉴얼'로서, 꼭 spring에 의존하는 개념이라고 보기는 힘듦.

어떤 빌드툴로 시작하든, 개발자의 추가 설정에 따라서 프로젝트 파일구조는 spring legacy가 될수도 spring boot가 될 수 있음.

하지만 '추가설정'이라는 수고스러움을 겪은 이전 개발자들이 편리하게 패키지 형태로 묶어서 프로젝트를 자동생성하게 지원함. 

이런 상황에서 maven은 주로 legacy, gradle은 주로 spring boot랑 묶이고

직면하기 전까진 의미없는 수많은 세부조건들에 따라 이 두가지 줄기 사이의 수많은 varitation들은 파생된다고 봄
