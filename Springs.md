# Spring framework

like spring legacy, spring boot, spring cloud ~

java EE와 같은 플랫폼 상에서 개발된 앱의 경우, (아마)모듈간 높은 결합도 등으로 인해 코딩 분업도 어렵지만, 단일테스트가 어려움

=>느슨한 결합과 테스트 용이성을 위해 Spring이란 프레임워크가 개발됨

## Main Features
### IoC/DI : Inversion of Control / Dependency Injection
IoC : 기존에 개발자가 new를 통해서 Java 객체를 생성 및 제어하던 방식을 벗어나, Java 객체 제어 및 관리를 Spring IoC Container에 모두 전임되어 제어권이 뒤바뀌는 것

한편, 기존 '객체'로 정의되던 클래스(혹은 인스턴스)들이 Spring IoC Container에 등록저장되어 제어될 경우 '빈(bean)'이라는 개념으로 재정의(혹은 맵핑)된다.

* bean : 초기 spring의 경우, 개발자가 xml 등을 활용 우선 직접 입력, 혹은 spring boot의 경우 어노테이션 like @Controller 등 을 통해서 등록 
[참고링크](https://atoz-develop.tistory.com/entry/Spring-%EC%8A%A4%ED%94%84%EB%A7%81-%EB%B9%88Bean%EC%9D%98-%EA%B0%9C%EB%85%90%EA%B3%BC-%EC%83%9D%EC%84%B1-%EC%9B%90%EB%A6%AC)

/

DI : bean은 추상화,상속 등의 특징들을 승계는데, container가 상속이나 타 클래스 내 이종클래스 선언 등의 참조를 '개발자 대신' 수행한다는 개념

=> 객체 간 의존성 최소화 => 테스트 용이, 코드 확장 용이, 순환참조 방지


#### container ? '보관'의 의미보단, '경계_Border'의 의미로!

기존 객체지향 자바의 추상화,상속를 바탕으로, 주요 객체들을 bean이라는 (어쩌면)더 작은 단위로 모듈화 혹은 캡슐화하여,

'객체1 => 객체2 has 객체1 by 개발자'를

'개발자 make context to access bean2 which is injected bean1 by container'

결과적으로 추상화 실현과 재사용성 향상에 충실

[참조링크](https://gmlwjd9405.github.io/2018/11/09/dependency-injection.html)

* spring (IoC) container : ex) ApplicationContext_xml 파일 형태로 객체 정보가 bean 태그로 저장_, BeanFactory , 

* context in computer science : the minimal set of data used by a task(which may be a process, thread, or fiber)


### AOP : Aspect Oriented Programming

(의역)monolithic 다층적 관점의 프로그래밍(스프링 프레임워크의 맞춤 MVC 커스텀버전)

Web layer                         

Service layer(or Business layer)  

Repository layer                  

| DTO

| -

| Domain model

[spring web layer](https://lifelife7777.tistory.com/100)

? Service layer vs Business layer [참고링크](https://docs.microsoft.com/en-us/previous-versions/msp-n-p/ee658090(v=pandp.10)?redirectedfrom=MSDN)

전통 아키텍쳐에서는 분명 독립 개념이나, 서로 인접 개념으로서 현실에서는 구분이 불명확하게 쓰이기 쉽다고 생각

무엇보다 spring에서는 거의 service라는 용어로 종합된 듯함

물론, spring에도 Domain Model에서 비즈니스 로직이 등장하는데, 현재로선 뚜렷하게 그 구분을 체감하기 힘듦

### PSA : Portable Service Abstraction

(예시)@Transactional 어노테이션만으로 DB 접근의 여러 절차를 자동 지원하게 해주는 스프링 기능

가령, jdbc, jpa는 각각 다른 스텝으로 DB에 접근하나, 스프링 사용 개발자는 (코딩된 숨겨진)스프링 기능을 통해 패스 

# Spring Legacy with Maven vs Spring boot with Gradle

