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

### Book
- [Real MySQL 8.0 (1권)](https://search.shopping.naver.com/book/catalog/32443973624?query=Mysql%208.0&NaPm=ct%3Dlw7gpmy8%7Cci%3D32cea7114111a158e964d9be5c0c7fa73cfd7af7%7Ctr%3Dboksl%7Csn%3D95694%7Chk%3D5bc7b1d55bfde67cae5194b43438b99fc60c30ed)
- [이것이 레디스다](https://search.shopping.naver.com/book/catalog/32436028951?query=%EC%9D%B4%EA%B2%83%EC%9D%B4%20%EB%A0%88%EB%94%94%EC%8A%A4%EB%8B%A4&NaPm=ct%3Dlw7gqnzk%7Cci%3D17a10802e0c9cbf97ef55bff9cdade78631e2969%7Ctr%3Dboksl%7Csn%3D95694%7Chk%3Db45e38a69a38726078cbec6d00669cc9bfb1b7d8)
- [리팩터링](https://www.yes24.com/Product/Goods/89649360)
- [Java의 정석](https://search.shopping.naver.com/book/catalog/32466681076?cat_id=50010920&frm=PBOKPRO&query=Java+%EC%9D%98+%EC%A0%95%EC%84%9D&NaPm=ct%3Dlw7gw048%7Cci%3D6d50d41884f105fdd1789de7b5997091ea592337%7Ctr%3Dboknx%7Csn%3D95694%7Chk%3D3b79e636e98238b285a7696dfb9ca84aba974338)
- [밑바닥부터 만드는 컴퓨팅 시스템](https://search.shopping.naver.com/book/catalog/39383703623?cat_id=50010921&frm=PBOKPRO&query=%EB%B0%91%EB%B0%94%EB%8B%A5%EB%B6%80%ED%84%B0+%EB%A7%8C%EB%93%9C%EB%8A%94+%EC%BB%B4%ED%93%A8%ED%8C%85+%EC%8B%9C%EC%8A%A4%ED%85%9C&NaPm=ct%3Dlw7gwxao%7Cci%3Dca55422478c3ddb738d46eb7d86a85358cf81939%7Ctr%3Dboknx%7Csn%3D95694%7Chk%3Df5cf1ea2bbae389d59ab4d7d5f971437d06ac640)
- [스프링 입문을 위한 자바 객체 지향의 원리와 이해](https://search.shopping.naver.com/book/catalog/32462919817?cat_id=50010920&frm=PBOKPRO&query=%EC%8A%A4%ED%94%84%EB%A7%81+%EC%9E%85%EB%AC%B8%EC%9D%84+%EC%9C%84%ED%95%9C+%EC%9E%90%EB%B0%94+%EA%B0%9D%EC%B2%B4+%EC%A7%80%ED%96%A5%EC%9D%98+%EC%9B%90%EB%A6%AC%EC%99%80+%EC%9D%B4%ED%95%B4&NaPm=ct%3Dlw7gxsxk%7Cci%3D09f7a89688a71d5324542a08cccf981af11bccfa%7Ctr%3Dboknx%7Csn%3D95694%7Chk%3D5b5f855b66aa95ee8316e70a9ac5bb60ab01236d)
- [MongoDB 완벽 가이드](https://search.shopping.naver.com/book/catalog/32481967929?cat_id=50010586&frm=PBOKPRO&query=MONGODB+%EC%99%84%EB%B2%BD+%EA%B0%80%EC%9D%B4%EB%93%9C&NaPm=ct%3Dlw7gyt74%7Cci%3D7a6c1982bb77a030462df471eee56ad34fe49ab3%7Ctr%3Dboknx%7Csn%3D95694%7Chk%3Da628c67a344293ad848763efedcbc698a3d665cf)
