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
