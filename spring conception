# Spring like spring legacy, spring boot, spring cloud ~

java EE와 같은 플랫폼 상에서 개발된 앱의 경우, (아마)모듈간 높은 결합도 등으로 인해 코딩 분업도 어렵지만, 단일테스트가 어려움

=>느슨한 결합과 테스트 용이성을 위해 Spring이란 프레임워크가 개발됨

## features
### IoC/DI : Inversion of Control / Dependency Injection

기존에 개발자가 new를 통해서 Java 객체를 생성 및 제어하던 방식을 벗어나, Java 객체를 Spring Container에 모두 전임_IoC

/

IoC 개념에 의해 기존 '객체'는 spring 상에서의 '빈(bean)'이라는 개념이자 단위로 맵핑될 수 있어지고, 추상화와 상속 등의 특성을 승계한다.

이러한 bean은 spring IoC container에 저장되고, container가 상속이나 타 클래스 내 이종클래스 선언 등의 참조를 '개발자 대신' 진행한다_DI

=> 객체 간 의존성 최소화 => 테스트 용이, 코드 확장 용이, 순환참조 방지


#### container ? '보관'의 의미보단, '경계'의 의미로!

기존 객체지향의 추상화,상속 등의 기술 외로 새로운 기능이 컨테이너에 있는 것으로 보이진 않고,

(주로 자주 쓸)객체들을 bean이라는 (어쩌면)더 작은 단위로 모듈화한 다음, 

결과적으로 추상화 실현과 재사용성 향상에 충실

* bean : @Componenent annotation을 통해 빈으로 등록된 클래스

* spring (IoC) container : ex) ApplicationContext_xml 파일 형태로 객체 정보가 bean 태그로 저장_, BeanFactory , 

* context in computer science : the minimal set of data used by a task(which may be a process, thread, or fiber)


[참조링크](https://gmlwjd9405.github.io/2018/11/09/dependency-injection.html)

### AOP : Aspect Oriented Programming

(의역)다각적 관점의 분석 프로그래밍, 모듈 지향 프로그래밍이되 좀더 아키텍쳐의 관점이 녹아든 것

클래스를 더 세부모듈로 쪼개고, 클래스 간 공통 모듈을 도출하여 재사용성을 높이겠다는 목표

* Aspect : 특정 관점을 기반으로 도출된 독립 모듈 from Target_class, method..
* advice : 실질적인 부가기능을 담은 구현체
* jointPoint and Pointcut : 

### PSA

# Spring Legacy vs Spring boot


#temp
https://gmlwjd9405.github.io/2018/11/09/dependency-injection.html

https://atoz-develop.tistory.com/entry/Spring-%EC%8A%A4%ED%94%84%EB%A7%81-%EB%B9%88Bean%EC%9D%98-%EA%B0%9C%EB%85%90%EA%B3%BC-%EC%83%9D%EC%84%B1-%EC%9B%90%EB%A6%AC

https://stackoverflow.com/questions/4108824/service-layer-vs-business-layer-in-architecting-web-applications

https://www.google.com/search?q=monolithic+vs+aop&oq=monolithic+vs+aop&aqs=chrome..69i57j33i160.8700j1j7&sourceid=chrome&ie=UTF-8

https://www.google.com/search?q=aop+vs+msa&oq=aop+vs+msa&aqs=chrome..69i57j33i160l4.7766j1j7&sourceid=chrome&ie=UTF-8

https://engkimbs.tistory.com/746
