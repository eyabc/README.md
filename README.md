### Currier
#### EST AID (구 Zum Internet)
- Position
  - FullStack Developer
- 재직 기간
  - 2020.11 ~ 재직중 
- 업무
  - 줌인터넷 포털 뉴스줌 웹서비스 풀스택 개발 https://news.zum.com/
  - 매체사로부터 기사데이터 송고받기 위한 FTP 서버와 NAS 시스템 이슈 대응
  - 기사데이터 문서를 파싱 하여 뉴스줌 DB 에 저장하는 어플리케이션 개발
  - DB 의 기사 데이터를 포털에 노출하기 위한 Rest API 개발
  - 뉴스 Backoffice 개발
  - 뉴스 Pc 및 Mobile SSR 서버 개발
  - DB 데이터 유지보수를 위한 Batch 어플리케이션 개발
 
### TechSet
★★★ Java, Javascript, SpringFramework, Vue.js, MySql, Jooq, Linux,  Jquery, Git, Gitlab, IDC

★★ Shell script, CSS, Nginx, FTP, SFTP, Redis, Spring Batch, JPA, Quartz, Docker, Jenkins, Javadoc, UnitTest, TDD, Swagger, CrossBrowsing, Ehcache, Redis Sentinel, Kafka

★dart, Express.js, Nest.js, Flutter, React.js, MongoDB

### Project

#### 뉴스 검색 파서 리팩터링 
- 개요
  - 여러 매체사에서 송고한 XML 파일을 파싱하여 뉴스줌과 줌인터넷의 여러 서비스에서 기사 컨텐츠를 노출하기 위한 프로젝트. 검색엔진에만 노출되는 기사를 송고하는 매체사의 XML 파싱 관리. 검색제휴 기사 파싱 과정 중 기존 현황과 문제점을 분석하여 전체적인 개선을 진행함
- articles
  - [java-inotify](https://medium.com/@bey4314/mysql-%EC%BF%BC%EB%A6%AC-%EC%84%B1%EB%8A%A5-%EA%B0%9C%EC%84%A0-0141d9d062da)
  - [어떤 Queue 를 사용해야 할까](https://medium.com/@bey4314/%EC%96%B4%EB%96%A4-queue-%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%B4%EC%95%BC-%ED%95%A0%EA%B9%8C-fe5bcc0afdc1)

#### collosseum-ticketing
- 개요
  - 콜로세움 예약 가능 티켓 발생 시, slack 으로 알림을 받을 수 있는 git action flow 작성. 
- repository
  - https://github.com/eyabc/collosseum-ticketing-macro
- tech
  - node.js

#### culture-infomation
- 개요
  - 문화 정보를 크롤링하는 git action flow 작성하고, react 로 웹뷰 구현
- tech
  - node.js, react.js
- repository
  - https://github.com/eyabc/culture-infomation
  - https://github.com/eyabc/culture-infomation-frontend
 
#### MySQL 업그레이드, 슬로우 쿼리 및 Replication Delay 이슈 해결, 데이터 일관성 강화, 안정성 개선 등 다양한 작업 수행
- MySQL 슬로우 쿼리로 인한 Connection request timed out 이슈 해결 [🔗](https://medium.com/@EeUuNnYuOuUuNnGg/mysql-slow-query-%EB%A1%9C-%EC%9D%B8%ED%95%9C-connection-request-timed-out-%EC%9D%B4%EC%8A%88-37bf90eda792)
- MySQL 의 Replication Delay 발생사례와 VIP 에서 서버를 제외하여 데이터 갱신 이슈 해결 [🔗](https://medium.com/@EeUuNnYuOuUuNnGg/mysql-%EC%9D%98-replication-delay-%EB%A1%9C-%EC%9D%B8%ED%95%9C-%EB%B2%84%EA%B7%B8-%EB%B0%9C%EC%83%9D-2456ed49f693)
- MySql 5.5 → 8.0 업그레이드
  - 어플리케이션의 mysql connector driver 버전 업그레이드
  - 업그레이드 후 옵티마이저의 쿼리 실행계획의 변경으로 일부, 쿼리들에 straight join Hint 문 추가
  - 트랜잭션에 서로 다른 스토리지엔진의 테이블 접근이 존재할 때 에러나는 이슈, MyISAM 테이블을 innoDB 로 변경
- Slow query 를 유발하는 원인에 대한 해결책을 기획적으로 고민 [🔗](https://www.notion.so/image/https%3A%2F%2Fprod-files-secure.s3.us-west-2.amazonaws.com%2F119ddbc4-c469-4b2a-ad73-653ceed5ec81%2Fa2922253-a639-4a66-9f05-039d2ae18e49%2FUntitled.png?table=block&id=956cd31e-7c21-4da3-9af1-ef501342f886&spaceId=119ddbc4-c469-4b2a-ad73-653ceed5ec81&width=2000&userId=3870e774-c131-4649-accd-876479d0a85d&cache=v2)
- Join 관련 이슈로 인해 테이블 분석 후, 중복 데이터로 인한 2번 노출 문제 해결 [🔗]()
 
#### 줌인터넷 프로젝트 기능 개발 
- 기간 2021.02 ~
  
- [줌프런트 뉴스박스](https://www.notion.so/image/https%3A%2F%2Fprod-files-secure.s3.us-west-2.amazonaws.com%2F119ddbc4-c469-4b2a-ad73-653ceed5ec81%2Fadc05539-8696-499c-91ac-fba7ec95df85%2FUntitled.png?table=block&id=68f63463-6f5d-4d45-8376-40e3e5ea9d45&spaceId=119ddbc4-c469-4b2a-ad73-653ceed5ec81&width=2000&userId=3870e774-c131-4649-accd-876479d0a85d&cache=v2) 기능 개발
  - 데이터 중심의 자동화된 뉴스 생성 및 편집 시스템 개발. 빅데이터 추천 기사목록 중 조건에 따라 뉴스박스 데이터 서빙 구현
  - Backoffice의 뉴스박스 편집 기능 외부링크 기사 추가, 이미지 편집, 순서 편집, 기사 제외/포함, 미리보기, 생성, 순서 고정 등의 기능 제공.
  - Batch 로 주기적인 뉴스박스 데이터 갱신.
  - 생성된 데이터 서빙을 위한 Rest Api 개발.
- 매체사 기사 원문 주소 변경 작업
  - 매체사 도메인 변경 및 기사 식별자 변경을 대응하기 위하여, Spring Batch 와 정규식을 활용하여 DB 의 컬럼 값을 수정하는 작업을 수행하였음.
  - 변경된 기사 데이터를 다른 플랫폼의 뉴스DB에 갱신하기 위해 ActiveMQ를 활용.
  - 변경 진행 사항을 모니터링하기 위해 임시 데이터를 Redis에 저장하고, Backoffice 에서 변경 진행사항을 조회할 수 있도록 개발
- 팝업 설정 어드민 및 API 개발
  - Vue.js, Spring boot 를 이용하여 Backoffice 팝업 설정 기능 개발. 팝업 데이터 사용을 위한 Rest API 개발
- Health Check 프로젝트 설계
  - Pingdom 기능 분석 진행     
  - 프로젝트의 개발 스프린트 및 일정, 프로젝트 타당성 비용 기술
  - 보일러플레이트의 Kotlin 으로의 마이그레이션 
  - MongoDB 연동 및 설정, 사용자 및 알림 관리에 대한 스키마 설계.
- 연관 기사 추천 시스템 적용
  - 뉴스줌 기사 소비 트래픽 향상을 위해 기사 조회 시 연관 기사 알고리즘 데이터를 사용자에게 서빙하기 위한 개발
  - RestAPI 를 개발하고, Redis 캐시를 적용함으로서 사용자에게 빠른 데이터 서빙으로 사용자 경험 향상 및 서버 부하 감소.
  - Spring MVC Template Engine 을 사용하여 SSR Endpoint 를 구현하고, 사용자의 기사 click, scroll 브라우저 이벤트 발생 시 통계 서버에 전송하는 기능 개발
- Backoffice 기능 개발
  - CSV 파일 입력을 받아 운영담당자가 기사의 처리 업무 향상에 도움.
  - ...
- 투자줌 해외증시 국내증시 API 개발
  - 사내 투자 서비스 종료로 코드 삭제 및 뉴스줌 프로젝트 정리를 위한 배포 프로세스 구축. 코드 제거 시 객체지향의 중요성을 포스팅함 [🔗](https://medium.com/@EeUuNnYuOuUuNnGg/%EC%84%9C%EB%B9%84%EC%8A%A4-%EC%A2%85%EB%A3%8C-%EB%8C%80%EC%9D%91-%EC%97%B0%EA%B4%80-%EC%BD%94%EB%93%9C-%EC%A0%9C%EA%B1%B0-9c6308c83ee8)
  - 국내증시 및 해외증시 페이지 Rest API, Backoffice, Batch 개발 및 MySQL 스키마 설계
- 뉴스줌 news.zum.com 리뉴얼
  - 뉴스줌 웹사이트 리뉴얼을 위해, 레거시 아키텍쳐를 분석하고 신규 RestAPI 개발, 복잡한 로직 처리와 기사 배열 자동 편집을 위한 Batch 개발, Backoffice 개발
- 2022 대선 이벤트 뉴스 페이지 개발
  - 프론트엔드 담당자에 제공할 Rest API 개발. Backoffice 및 Batch Job 개발을 통해 효율적인 데이터 편집 및 관리 체계 구축.
  - 선거정보, D-day, 개표결과, 대선 속보, 대선 주요뉴스, 예비후보 및 정당 정보, 테마주, 후보자 별 정책 뉴스, 테마주 평균 수익률, 대선 최신 뉴스, 득표정보 기능 개발
  - 효과적인 협업으로 원활한 개발 진행 및 팀 간 원활한 의사소통 달성.
    - API 명세서를 통해 명확한 업무 이해도 및 프로젝트 진행 상황을 공유하고 투명한 협업환경 조성.
    - 작업 전 Notion을 활용하여 빠르게 API 명세를 프론트엔드 팀에 전달하며, 기획 내용과 함께 API 구성 이유를 설명.
    - 프론트엔드 담당자에게 내가 알고 있는 모든 내용을 공유하고, 피드백 적극 수용.
    - 실제 구현이 시작되면 API 명세서 페이지에 구현과정을 기록하여 히스토리를 공유.
- 스타트줌 [start.zum.com](https://start.zum.com/), 뉴스 컨텐츠 서빙 Rest API 개발
  - 스타트줌은 줌인터넷의 브라우저 시작페이지 서비스.
  - 스타트줌 백엔드 개발자 및 기획자, 데이터 엔지니어 등 모든 담당자 간 뉴스 API 개발 히스토리를 공유하며 협업에 중점을 두었음.
  - Swagger-UI를 적용하여 API 개발 투명성 향상
 
#### 뉴스줌 프로젝트 개선
- 기간
  - 2021.02 ~ 
- 내용
  - Migration 된 테이블의 데이터를 제거하여, 불필요한 자원을 소모하는 문제를 해결. Batch, CMS, API, 파서 등에서 데이터소스와 관련 코드 제거하고 안전하게 DB를 삭제하는 작업 완료
  - 사내 Nexus의 프레임워크의 의존성을 제거하기 위해, 신규 멀티 모듈 프로젝트를 생성함으로써 신규 개발에 유연성을 부여하였음. MySQL 업그레이드 후 Jooq 버전 변경, Redis 도입, 테스트코드 도입과 같은 어려움을 해결하였습니다.
  - 레거시 모듈은 스파게티 코드로 인해 테스트 작성과 리팩터링이 어려웠고, 이로 인해 프로그램의 신뢰성과 안정성이 저하되었습니다. 또한, 신규 개발자의 적응이 어려워 프로그램 품질이 저하되는 문제점을 인식했습니다. 새로운 기술을 유연하게 적용하고 유지보수성을 향상시키기 위해 서브 프로젝트 간의 의존성을 최소화함으로써 프로그램의 품질과 안정성 향상.
  - 테스트 코드의 중요성을 팀원에게 공유 [🔗](https://medium.com/@EeUuNnYuOuUuNnGg/%ED%85%8C%EC%8A%A4%ED%8A%B8-%EC%BD%94%EB%93%9C-%EC%BB%A4%EB%B2%84%EB%A6%AC%EC%A7%80%EC%9D%98-%ED%9A%A8%EA%B3%BC-13c83b661e6a)
  - 단일 gradle 모듈에서 멀티 모듈로 합쳐진 프로젝트의, 스파게티 코드를 인터페이스로 통합하는 개선 작업 진행
  - 캐시 데이터 관리 시스템으로, TTL을 활용하여 주기적인 갱신 및 불필요한 데이터 관리를 수행함. [🔗](https://medium.com/@EeUuNnYuOuUuNnGg/ttl-%EC%9D%B4-%ED%95%84%EC%9A%94%ED%95%9C-%EC%BA%90%EC%8B%9C%EC%99%80-ttl-%EC%9D%B4-%ED%95%84%EC%9A%94%ED%95%98%EC%A7%80-%EC%95%8A%EB%8A%94-%EB%8D%B0%EC%9D%B4%ED%84%B0-%EA%B5%AC%EB%B6%84%ED%95%98%EA%B8%B0-4f76572cf9ef)
  - API 프로젝트 전체 endpoint 의 swagger 적용 및 문서화. nginx access 로그를 통한 사용되지 않는 endpoint 분석. endpoint 사용처 문서화
  - Java melody 모니터링 라이브러리 적용 [🔗](https://medium.com/@EeUuNnYuOuUuNnGg/java-melody-af186124ac4c)


#### Quartz Scheduler 어드민의 동적 데이터소스 구현 [🔗](https://zuminternet.github.io/ZUM-Pilot-advanced_quartz_scheduler_admin/)
- 기간
  - 2020.12 ~ 2021.02  
- 개요
  - 다중 데이터 소스를 동적으로 관리하고 모니터링하는 어드민 구현
- 사용 기술
  - SpringBoot, Java, Node, SpringJPA, Spring Security, Vuex, Vue2, ES2020, MySQL, RoutingDataSource
- 내용
  - 어드민 패널을 통해 동적으로 데이터 소스를 추가 및 제거할 수 있는 기능을 구현하여 다중 데이터베이스 간의 전환을 쉽게 수행하도록 하였음.
  - 데이터 소스의 Connection 설정을 동적으로 설정할 수 있도록 개발
  - 각 데이터 소스의 연결 상태 모니터링 기능 개발
  - 사용자의 역할에 따라 어드민의 특정 기능에 대한 접근을 제한하는 기능 개발
  - 배포된 프로젝트 버전을 확인할 수 있는 StateController 추가
  - Gradle 을 최신 버전으로 업그레이드
  - Spring Boot 버전 업그레이드 중 Quartz jobData Converter 의 직렬화/역직렬화 오류 수정. [🔗](https://medium.com/@EeUuNnYuOuUuNnGg/spring-quartz-jobdata-%EC%9D%98-deserialization-serialization-ingore-serialversionuid-exception-847aaf3ebec2)
  - Spring Security의 PasswordEncoder를 사용하여 안전한 비밀번호 저장
  - 백엔드 예외를 프론트엔드가 이해할 수 있는 예외 코드로 처리하여 브라우저 클라이언트가 대응할 수 있는 동작을 정의함
  - SecurityContextHolder를 활용하여 요청이 인증 확인
  - Spring Data의 AuditorAware를 구현하여 JpaAuditing으로 자동으로 사용자 정보 기록
  - Google OAuth 로그인 시 회사 이메일 유효성 검증
  - 사용자 역할 변경 시 세션 무효화를 통한 보안 강화
  - 중복 코드 제거를 위해 공통 모달 컴포넌트 생성
  - 톰캣 재시작 시 세션을 디스크에 저장하지 않도록 구성
  - Axios 요청 타임아웃 설정으로 백엔드 서버 부하 최소화
  - Vue keep-alive 제거로 데이터 초기화 개선
  - 텍스트 엘리먼트에 대한 상수 선언으로 오타 최소화 및 코드 가독성 향상
  - 실행 중인 job의 ID를 조회하는 기능 추가
  - logback 설정 추가
  - Batch 사용이 없는 데이터베이스에 연결된 Quartz Scheduler 예외 처리.  


### Articles

#### IDE
- [IntelliJ Java SonarLint Plugin](https://medium.com/@bey4314/intellij-java-sonarlint-plugin-6af7b29b0cdc)

#### Test Code
- [JUnit 5 gradle (groovy) 의존성 설정하기](https://medium.com/@bey4314/junit-5-gradle-groovy-%EC%9D%98%EC%A1%B4%EC%84%B1-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0-11a5ff79245e)

#### Java
- [JMX > javax.management.InstanceNotFoundException](https://medium.com/@bey4314/javax-management-instancenotfoundexception-6d3182917f87)
- [Java 의 Record 타입 굳이 써야 할까?](https://medium.com/@bey4314/java-%EC%9D%98-record-%ED%83%80%EC%9E%85-%EA%B5%B3%EC%9D%B4-%EC%8D%A8%EC%95%BC-%ED%95%A0%EA%B9%8C-cfd65814e51e)
- [Java Record — Non-canonical record constructor must delegate to another constructor](https://medium.com/@bey4314/java-record-53768e6eaedf)
- [Java UnMarshall: XML to Object](https://medium.com/@bey4314/java-xml-to-object-8e63d98ace3a)
- [Javadoc 작성하기 with IntelliJ, jenkins 서버 배포까지](https://medium.com/@bey4314/javadoc-%EC%9E%91%EC%84%B1%ED%95%98%EA%B8%B0-with-c8fd2f0cc8d8)
- [Java HTML Unescape](https://medium.com/@bey4314/java-html-unescape-4401bae5744e)
- [Effective Java > Ch1 들어가기](https://eyabc.github.io/docs/java/effective-java/ch1)
- [Effective Java > Ch2 객체 생성과 파괴](https://eyabc.github.io/docs/java/effective-java/ch2/index)
- [Effective Java > Ch2 객체 생성과 파괴 > 생성자 대신 정적 팩터리 메서드를 고려하라](https://eyabc.github.io/docs/java/effective-java/ch2/ITEM1)
- [JAXB Unmarshal Setter, EnumType](https://medium.com/@bey4314/jaxb-unmarshal-setter-dbf560fedea3)
- [Java 15 Multi-line String Text Block](https://medium.com/@bey4314/java-15-multi-line-string-text-block-307125d98c87)
- [Java9 Module](https://medium.com/@EeUuNnYuOuUuNnGg/java9-module-79f060b2a9bb)

#### JPA
- [JPA, javax.persistence, Hibernate, Spring Data JPA](https://medium.com/@EeUuNnYuOuUuNnGg/spring-jpa-%EA%B0%9C%EB%85%90-%EC%A0%95%EB%A6%AC%ED%95%98%EA%B8%B0-d32a07dd045a)

#### MySql
- [MySql 필드 값에 여러가지 값을 넣기 위한 방법](https://medium.com/@bey4314/mysql-%ED%95%84%EB%93%9C-%EA%B0%92%EC%97%90-%EC%97%AC%EB%9F%AC%EA%B0%80%EC%A7%80-%EA%B0%92%EC%9D%84-%EB%84%A3%EA%B8%B0-%EC%9C%84%ED%95%9C-%EB%B0%A9%EB%B2%95-be29b68462d1)
- [MySql 쿼리 성능 개선](https://medium.com/@bey4314/mysql-%EC%BF%BC%EB%A6%AC-%EC%84%B1%EB%8A%A5-%EA%B0%9C%EC%84%A0-0141d9d062da)

#### Spring
- [Property ‘spring.profiles.active’ imported from location ‘class path resource](https://medium.com/@bey4314/springboot-property-spring-profiles-active-imported-from-location-class-path-resource-b1078ceaccc2)
- [Gradle Mutli-module Property 정의하기](https://medium.com/@bey4314/gradle-mutli-module-property-%EC%A0%95%EC%9D%98%ED%95%98%EA%B8%B0-7a15b9c0bbe7)

#### Kafka
- [docker-compose 로 Kafka 컨테이너를 생성하고, 어플리케이션에서 접근하기](https://medium.com/@bey4314/docker-compose-%EB%A1%9C-kafka-%EC%BB%A8%ED%85%8C%EC%9D%B4%EB%84%88%EB%A5%BC-%EC%83%9D%EC%84%B1%ED%95%98%EA%B3%A0-%EC%96%B4%ED%94%8C%EB%A6%AC%EC%BC%80%EC%9D%B4%EC%85%98%EC%97%90%EC%84%9C-%EC%A0%91%EA%B7%BC%ED%95%98%EA%B8%B0-f7915850619c)
- [IntelliJ Kafka 도구 사용하기](https://medium.com/@bey4314/intellij-kafka-%EB%8F%84%EA%B5%AC-%EC%82%AC%EC%9A%A9%ED%95%98%EA%B8%B0-4e9db6b2d742)
- [Java Kafka Consumer 구현](https://medium.com/@bey4314/java-kafka-consumer-%EA%B5%AC%ED%98%84-5c186307800a)
- [Java Kafka CommonErrorHandler 에 예외가 전파되기 전에 AOP 로 예외 처리하기](https://medium.com/@bey4314/java-kafkalistenrerrorhandler-%EC%97%90-%EC%98%88%EC%99%B8%EA%B0%80-%EC%A0%84%ED%8C%8C%EB%90%98%EA%B8%B0-%EC%A0%84%EC%97%90-%EC%98%88%EC%99%B8-%EC%B2%98%EB%A6%AC%ED%95%98%EA%B8%B0-0d8c621f571f)

#### ETC

- [UTF-8, UNICODE](https://gitmind.com/app/docs/m1qjle9c)
- [BSON VS JSON](https://gitmind.com/app/docs/me7laubd)
- [Planning with Google Presentation](https://eyabc.github.io/Doc/dev-nodes/%EA%B5%AC%EA%B8%80%ED%94%84%EB%A0%88%EC%A0%A0%ED%85%8C%EC%9D%B4%EC%85%98%EC%9C%BC%EB%A1%9C%20%EA%B8%B0%ED%9A%8D%ED%95%98%EA%B8%B0.html)
- [Introduction to Website Planning](https://eyabc.github.io/Doc/dev-nodes/%EA%B8%B0%ED%9A%8D.html#%EC%8A%A4%EC%BC%80%EC%B9%98-%EC%9E%91%EC%84%B1-%EC%9A%94%EB%A0%B9)
- [Iterator Pattern](https://eyabc.github.io/Doc/dev/design-pattern/iterator%20pattern.html#%EC%98%88%EC%8B%9C)
- [Why use Kafka Connect as a data pipeline? Unpacking the open source kafka-sink-connector!](https://gitmind.com/app/docs/mhbifts9)
- [AB Test](https://gitmind.com/app/docs/m5hxci8q)
- [Jira 적응기](https://medium.com/@bey4314/jira-%EC%A0%81%EC%9D%91%EA%B8%B0-9f2158d637ae)
- [비밀번호와 무의식적 암시](https://medium.com/@bey4314/%EB%B9%84%EB%B0%80%EB%B2%88%ED%98%B8-%EB%B3%80%EA%B2%BD%ED%95%98%EA%B8%B0-7831cad2c59c)
  
#### Search Engine Optimization
- [robots.txt, sitemap.xml](https://medium.com/@bey4314/robots-txt-sitemap-xml-343a317a75f2)

#### Linux

#### frontend
- [Webpack devserver proxy](https://medium.com/@bey4314/webpack-devserver-proxy-52cf5047301b)

#### Spring Batch
- [실행중인 Job 을 종료하는 Job 개발, JobOperator, JPA](https://medium.com/@bey4314/spring-batch-%EC%8B%A4%ED%96%89%EC%A4%91%EC%9D%B8-job-%EC%9D%84-%EC%A2%85%EB%A3%8C%ED%95%98%EB%8A%94-job-%EA%B0%9C%EB%B0%9C-95e559cd953d)
- [쓰레드 파티션 네임 중첩 이슈](https://medium.com/@EeUuNnYuOuUuNnGg/spring-batch-cannot-restart-step-from-starting-status-e4ab9fa761a3)
- [Datasource ConnectionPoolSize Exception](https://medium.com/@EeUuNnYuOuUuNnGg/spring-batch-datasource-connectionpoolsize-exception-293d2def021b)
- [flow 의step 에서 StepExitStatus 를 Failed 로 변경한다면 다음 Step 은 실행되지 않는다](https://medium.com/@EeUuNnYuOuUuNnGg/spring-batch-flow-%EC%9D%98step-%EC%97%90%EC%84%9C-stepexitstatus-%EB%A5%BC-failed-%EB%A1%9C-%EB%B3%80%EA%B2%BD%ED%95%9C%EB%8B%A4%EB%A9%B4-%EB%8B%A4%EC%9D%8C-step-%EC%9D%80-%EC%8B%A4%ED%96%89%EB%90%98%EC%A7%80-%EC%95%8A%EB%8A%94%EB%8B%A4-d39c4e35413c)
- [ScopeNotActiveException](https://medium.com/@EeUuNnYuOuUuNnGg/spring-batch-scopenotactiveexception-8e63bfc35b7d)
- [Spring Batch JobParameter 는 변경할 수 없다](https://medium.com/@EeUuNnYuOuUuNnGg/spring-batch-jobparameter-%EB%8A%94-%EB%B3%80%EA%B2%BD%ED%95%A0-%EC%88%98-%EC%97%86%EB%8B%A4-36ab28607357)
- [Spring Quartz JobData 의 Deserialization, Serialization Ingore serialVersionUID Exception](https://medium.com/@EeUuNnYuOuUuNnGg/spring-quartz-jobdata-%EC%9D%98-deserialization-serialization-ingore-serialversionuid-exception-847aaf3ebec2)
- [MySQL 과 Spring Batch 의 통계 작업 개발](https://medium.com/@EeUuNnYuOuUuNnGg/mysql-%EA%B3%BC-spring-batch-%EC%9D%98-%ED%86%B5%EA%B3%84-%EC%9E%91%EC%97%85-%EA%B0%9C%EB%B0%9C-c119a4ca6c1c)
- [MultiResourceItemReader 는 Resource 를 어떻게 읽어 올까?](https://medium.com/@EeUuNnYuOuUuNnGg/spring-batch-multiresourceitemreader-%EB%8A%94-resource-%EB%A5%BC-%EC%96%B4%EB%96%BB%EA%B2%8C-%EC%9D%BD%EC%96%B4-%EC%98%AC%EA%B9%8C-416fee7b3d4a)
- [Spring Batch ExitStatus 과 Test Code 작성하기](https://medium.com/@EeUuNnYuOuUuNnGg/spring-batch-exitstatus-%EA%B3%BC-test-code-%EC%9E%91%EC%84%B1%ED%95%98%EA%B8%B0-7a67d6baca21)
- [Spring Batch 의 ExecutionContext 의 value 타입](https://medium.com/@EeUuNnYuOuUuNnGg/spring-batch-%EC%9D%98-executioncontext-%EC%9D%98-value-%ED%83%80%EC%9E%85-60983a109c4b)
- [Spring Batch Partitioner JobScope 의 중복](https://medium.com/@EeUuNnYuOuUuNnGg/spring-batch-jobscope-%EC%9D%98-%EC%A4%91%EB%B3%B5-96383da69808)
- [Spring Batch Test 코드에서 Job 실행 시키기](https://medium.com/@EeUuNnYuOuUuNnGg/spring-batch-test-%EC%BD%94%EB%93%9C%EC%97%90%EC%84%9C-job-%EC%8B%A4%ED%96%89-%EC%8B%9C%ED%82%A4%EA%B8%B0-5f57c46972aa)
- [SimpleStepHandler](https://medium.com/@EeUuNnYuOuUuNnGg/simplestephandler-0f5b68a55516)

### Book
- [Real MySQL 8.0 (1권)](https://search.shopping.naver.com/book/catalog/32443973624?query=Mysql%208.0&NaPm=ct%3Dlw7gpmy8%7Cci%3D32cea7114111a158e964d9be5c0c7fa73cfd7af7%7Ctr%3Dboksl%7Csn%3D95694%7Chk%3D5bc7b1d55bfde67cae5194b43438b99fc60c30ed)
- [이것이 레디스다](https://search.shopping.naver.com/book/catalog/32436028951?query=%EC%9D%B4%EA%B2%83%EC%9D%B4%20%EB%A0%88%EB%94%94%EC%8A%A4%EB%8B%A4&NaPm=ct%3Dlw7gqnzk%7Cci%3D17a10802e0c9cbf97ef55bff9cdade78631e2969%7Ctr%3Dboksl%7Csn%3D95694%7Chk%3Db45e38a69a38726078cbec6d00669cc9bfb1b7d8)
- [리팩터링](https://www.yes24.com/Product/Goods/89649360)
- [Java의 정석](https://search.shopping.naver.com/book/catalog/32466681076?cat_id=50010920&frm=PBOKPRO&query=Java+%EC%9D%98+%EC%A0%95%EC%84%9D&NaPm=ct%3Dlw7gw048%7Cci%3D6d50d41884f105fdd1789de7b5997091ea592337%7Ctr%3Dboknx%7Csn%3D95694%7Chk%3D3b79e636e98238b285a7696dfb9ca84aba974338)
- [밑바닥부터 만드는 컴퓨팅 시스템](https://search.shopping.naver.com/book/catalog/39383703623?cat_id=50010921&frm=PBOKPRO&query=%EB%B0%91%EB%B0%94%EB%8B%A5%EB%B6%80%ED%84%B0+%EB%A7%8C%EB%93%9C%EB%8A%94+%EC%BB%B4%ED%93%A8%ED%8C%85+%EC%8B%9C%EC%8A%A4%ED%85%9C&NaPm=ct%3Dlw7gwxao%7Cci%3Dca55422478c3ddb738d46eb7d86a85358cf81939%7Ctr%3Dboknx%7Csn%3D95694%7Chk%3Df5cf1ea2bbae389d59ab4d7d5f971437d06ac640)
- [스프링 입문을 위한 자바 객체 지향의 원리와 이해](https://search.shopping.naver.com/book/catalog/32462919817?cat_id=50010920&frm=PBOKPRO&query=%EC%8A%A4%ED%94%84%EB%A7%81+%EC%9E%85%EB%AC%B8%EC%9D%84+%EC%9C%84%ED%95%9C+%EC%9E%90%EB%B0%94+%EA%B0%9D%EC%B2%B4+%EC%A7%80%ED%96%A5%EC%9D%98+%EC%9B%90%EB%A6%AC%EC%99%80+%EC%9D%B4%ED%95%B4&NaPm=ct%3Dlw7gxsxk%7Cci%3D09f7a89688a71d5324542a08cccf981af11bccfa%7Ctr%3Dboknx%7Csn%3D95694%7Chk%3D5b5f855b66aa95ee8316e70a9ac5bb60ab01236d)
- [MongoDB 완벽 가이드](https://search.shopping.naver.com/book/catalog/32481967929?cat_id=50010586&frm=PBOKPRO&query=MONGODB+%EC%99%84%EB%B2%BD+%EA%B0%80%EC%9D%B4%EB%93%9C&NaPm=ct%3Dlw7gyt74%7Cci%3D7a6c1982bb77a030462df471eee56ad34fe49ab3%7Ctr%3Dboknx%7Csn%3D95694%7Chk%3Da628c67a344293ad848763efedcbc698a3d665cf)
