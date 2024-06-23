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
<details>
  <summary>뉴스 검색 파서 리팩터링 </summary>
  
- 기간 2024.03 ~ 진행중
- 개요
  - 여러 매체사에서 송고한 XML 파일을 파싱하여 뉴스줌과 줌인터넷의 여러 서비스에서 기사 컨텐츠를 노출하기 위한 프로젝트. 검색엔진에만 노출되는 기사를 송고하는 매체사의 XML 파싱 관리. 검색제휴 기사 파싱 과정 중 기존 현황과 문제점을 분석하여 전체적인 개선을 진행함
- articles
  - [java-inotify](https://medium.com/@bey4314/mysql-%EC%BF%BC%EB%A6%AC-%EC%84%B1%EB%8A%A5-%EA%B0%9C%EC%84%A0-0141d9d062da)
  - [어떤 Queue 를 사용해야 할까](https://medium.com/@bey4314/%EC%96%B4%EB%96%A4-queue-%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%B4%EC%95%BC-%ED%95%A0%EA%B9%8C-fe5bcc0afdc1)
    
</details>

<details>
  <summary>뉴스 송고 기사 통계 개발</summary>

- 기간
  - 2024.01 ~ 2024.03
- 개요
  - 매체사로 부터 송고 받은 기사데이터 특징을 분류하여 카운트를 통계하는 기능 개발. 통계 데이터를 CMS 에서 운영담당자가 조회하는 페이지 개발
- 내용
  - Spring Batch 와 Redis Hash, Set 타입을 이용한 통계구현. 인덱스가 없는 컬럼으로 인한 MySql의 슬로우 쿼리 문제 해결. 처리 속도 향상을 1시간에서 1분으로 단축 [🔗](https://medium.com/@bey4314/mysql-%EA%B3%BC-spring-batch-%EC%9D%98-%ED%86%B5%EA%B3%84-%EC%9E%91%EC%97%85-%EA%B0%9C%EB%B0%9C-c119a4ca6c1c)
  - MySQL에서 JSON 타입을 활용하여 통계 데이터를 저장하는 테이블을 설계하였음. 새로운 통계 항목을 추가할 때 기존 스키마를 변경하지 않고도 유연하게 데이터를 관리할 수 있도록 함 [🔗](https://medium.com/@EeUuNnYuOuUuNnGg/jackson-databind-exc-inrecognizedpropertyexception-not-marked-as-ignorable-60d7ccd03cfa)
  - 테스트 코드 작성으로, 아키텍쳐 변경이 3번 이상 있었음에도 불구하고, 코드의 검증과정을 테스트 코드를 통해 신속하게 완료
  - 레거시 프로젝트에 포함된 월간 매체 통계 Job 을 새로운 Batch 프로젝트의 Job 으로 Migration 하였음. Maven XML configuration 파일 분석을 통해 기존 통계 방식을 이해하고 코드 Migration 진행. JPA 와 criteria 로 구현된 코드를 Jooq 로 migration 하였음. 통계에 사용 되는 테이블을 분석하고 기존 뉴스시스템과의 커플링 되어있는 로직을 분석하였음.
  - 구현과정에서 발생한 문제를 해결함으로써 Spring Batch 에 대한 이해 향상. Spring Batch 파티션 중첩으로 인한 thread 중복 실행 이슈 수정 [🔗](https://medium.com/@bey4314/spring-batch-cannot-restart-step-from-starting-status-e4ab9fa761a3), Batch DB Connection Pool Size 예외 수정 [🔗](https://medium.com/@EeUuNnYuOuUuNnGg/spring-batch-datasource-connectionpoolsize-exception-293d2def021b) StepExitStatus 종료에 따른 flow 수행 결과 관찰 [🔗](https://medium.com/@EeUuNnYuOuUuNnGg/spring-batch-flow-%EC%9D%98step-%EC%97%90%EC%84%9C-stepexitstatus-%EB%A5%BC-failed-%EB%A1%9C-%EB%B3%80%EA%B2%BD%ED%95%9C%EB%8B%A4%EB%A9%B4-%EB%8B%A4%EC%9D%8C-step-%EC%9D%80-%EC%8B%A4%ED%96%89%EB%90%98%EC%A7%80-%EC%95%8A%EB%8A%94%EB%8B%A4-d39c4e35413c),  Scope 이슈 해결 [🔗](https://medium.com/@EeUuNnYuOuUuNnGg/spring-batch-scopenotactiveexception-8e63bfc35b7d) , JobParameter 와 JobExecution [🔗](https://medium.com/@EeUuNnYuOuUuNnGg/spring-batch-jobparameter-%EB%8A%94-%EB%B3%80%EA%B2%BD%ED%95%A0-%EC%88%98-%EC%97%86%EB%8B%A4-36ab28607357), Spring Quartz JobData 의 Deserialization, Serialization Ingore serialVersionUID Exception [🔗](https://medium.com/@EeUuNnYuOuUuNnGg/spring-quartz-jobdata-%EC%9D%98-deserialization-serialization-ingore-serialversionuid-exception-847aaf3ebec2)

</details>

<details>
  <summary>뉴스줌 저작권 위반 이미지 응답 차단 프로젝트</summary>

- 기간
  - 2023.10
- 개요
  - Copytrack 서비스로 인한 이미지 저작권 문제로 발생한 재정적 문제를 해결하기 위해, 문제가 되는 이미지 리소스 요청의 Response 차단하는 어플리케이션 개발. [🔗](https://medium.com/@EeUuNnYuOuUuNnGg/%EC%9D%B4%EB%AF%B8%EC%A7%80-%EC%A0%80%EC%9E%91%EA%B6%8C-%EA%B4%80%EB%A0%A8-%EC%9D%91%EB%8B%B5-%EC%B0%A8%EB%8B%A8-%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8-84911b405751)

</details>

<details>
  <summary>뉴스줌 Batch 데이터 처리 프로젝트</summary>

- 기간
  - 2022.12 ~
- 개요
  - 대용량 데이터 처리를 중심으로 한 기능들을 구현한 프로젝트. MySql 테이블 대상으로 하는 작업 주로 진행하였음
- 내용
  - Job 실행 중인 Job 종료 기능 개발 [🔗](https://medium.com/@EeUuNnYuOuUuNnGg/spring-batch-%EC%8B%A4%ED%96%89%EC%A4%91%EC%9D%B8-job-%EC%9D%84-%EC%A2%85%EB%A3%8C%ED%95%98%EB%8A%94-job-%EA%B0%9C%EB%B0%9C-95e559cd953d) 배치의 메타 테이블 BATCH_JOB_EXECUTION에서의 ID 값을 Job Parameter로 활용하여 현재 실행 중인 Job을 중단시키는 Tasklet을 구현. 대용량 데이터 처리와 같이 시간이 오래 걸리는 JOB 중단에 대한 문제 해결
  - 제휴 종료된 매체사 데이터 삭제 Job, 기존의 20개가 넘는 외래키를 참조하는 테이블들의 레코드를 삭제하는 프로세스를 개선. 타 서비스에 저장된 데이터 삭제를 동기화 하기 위해 ActiveMQ 사용. NAS 에 저장된 이미지를 삭제 하여 저작권 및 리소스 관리를 개선하였음. 수동으로 삭제하고 있던 프로세스를 자동화
  - 삭제상태 기사 데이터 삭제 Job. 2011년부터 불필요하게 스토리지를 차지하고 있는 삭제상태 기사를 효율적으로 삭제하도록 개선. 1억 건 이상의 대용량 테이블에서 인덱스가 없는 컬럼의 조건으로 데이터를 삭제 하기 위해 chunk 단위로 삭제하여 Query Timeout 이슈 개선.
  - 외래키 참조가 많은 테이블 로그 데이터 삭제 Job. 10년간 축적된 로그 데이터를 삭제하여 200GB 이상의 공간을 확보.
  - 송고 기사 통계 집계 Job. Flow와 Partitioner를 활용하여 매체사별로 병렬로 작업이 실행되도록 하여 처리 속도를 향상. 인덱스가 없어 발생하는 슬로우 쿼리 문제를 Redis 를 사용하여 집계.
  - Quartz + Spring Batch 를 조합하여, 대용량 처리에 적합한 Batch 와, Quartz 를 사용하여 Quartz Job 이 Trigger 가 될 때 Batch Job 을 실행시키는 구조를 구현함
  - Batch Job 테스트와, Jooq 메서드 테스트 코드를 작성 [🔗](https://medium.com/@EeUuNnYuOuUuNnGg/spring-batch-test-%EC%BD%94%EB%93%9C%EC%97%90%EC%84%9C-job-%EC%8B%A4%ED%96%89-%EC%8B%9C%ED%82%A4%EA%B8%B0-5f57c46972aa)

</details>


<details>
  <summary>뉴스줌 파서 프로젝트</summary>

- 기간
  - 2020.10 ~
- 개요
  - 매체사로부터 FTP, SFTP 로 기사의 XML 과 멀티미디어 파일을 송고 받아 NAS 에 저장하는 과정의 서버들을 유지보수 합니다. 그리고 XML 파일을 Java 마샬러 와 정규식을 이용해 본문, 이미지, 캡션 등의 HTML 마크업과 뉴스 메타정보를 파싱합니다. 이 후 뉴스줌의 MySql 에 기사의 메타데이터를 저장하고, 줌인터넷의 데이터 시스템 및 및 서비스에 동기화하기 위해 ActiveMQ 를 사용
  - 제휴 매체사의 지속적인 비즈니스 수익 관계를 위해, 매체사의 문의 대응에 즉시 대응
- 내용
  - PKIX 에러를 해결하고, 파서 서버에서 HTTPS를 통한 매체사서버의 요청을 정상화 [🔗](https://medium.com/@EeUuNnYuOuUuNnGg/java-pkix-%EC%98%88%EC%99%B8-9a2a520daf9e)
  - 특정기간 디렉터리 내의 기사 파일의 재파싱을 위한 리눅스 쉘스크립트 작성
  - FTP PUT, FTP GET, SFTP 서버와 클라이언트를 사용 및 mirror 명령어 등을 통해 다양한 매체사의 기술의 특성에 맞게 송고 서버를 관리하였음
  - 매체사 별 특이사항이 발생하는 XML 파일을 뉴스줌의 메타데이터에 맞게 파싱하기 위해 정규식 파싱 규칙 수정 및 적용하였음. 신규 매체사 제휴를 위한 기사 파서 정규식 설정 적용.
  - 매체사 기사 미노출 시 타 개발부서와 협업하여 원인파악 진행 및 이슈 픽스
  - 뉴스 파서에서 오류를 쉽게 찾을 수 있도록 해당 케이스에 대한 로그를 제공하도록 수정 개발
  - 특정 매체사에서 발생한 대량 정크파일 송고로 인한 최신 기사 미노출 이슈를 조치. dumy 파일을 삭제하는 쉘스크립트를 작성하여 해결. 파일 확장자 화이트리스트를 ftp 송고 정책에 추가하는 등의 보다 강력한 대응 방안을 구상.
  - 미래 시점으로 송출된 기사에 대한 안정적인 처리 로직 설계, MySQL JSON 타입을 활용하여 유연성있는 테이블 설계, 로그 정보를 검색과 분석을 위해 구조적으로 저장. Vue.js 로 구현된 어드민 페이지에서는 파싱 로그 및 에러 로그와 관련된 정보 제공. 매체사 서버와 파싱 서버 간의 TIME 차이로 인해 발생하는 문제에 보간 설계.
  - 리눅스 파일의 ctime 을 통해 동일 기사가 여러번 송고되었을 경우, 최신 파싱 기사를 판단할 수 있도록 개선.
  - 100MB 이상 매체사의 FTP 홈 디렉터리의 과거 데이터를 정리하는 쉘스크립트 작성
  - rsync 를 사용하여 송고된 기사 파일들을 QA 환경에서도 테스트 할 수 있도록 구성하였음
  - ISMS 지적사항 수정. SFTP 전환 매체사 대상 파싱 및 검색 노출 확인, 쉘스크립트를 작성하여 기사 파싱 디렉터리의 목록을 스캔하고, 매체사 사이트를 Javascript 로 크롤링하여 최신기사 리스트의 업데이트 싱크를 확인하는 작업 진행

</details>


<details>
  <summary>뉴스줌 인프라 대응</summary>

- 기간
  - 2020.10 ~
- 개요
  - 인프라 문제를 인프라팀과 협업하여 시스템 안정성 향상 및 장애 대응
- 내용  
  - Route53 이슈 대응 [🔗](https://medium.com/@EeUuNnYuOuUuNnGg/route53-%EC%9D%B4%EC%8A%88-%EB%8C%80%EC%9D%91-a11b998536e4) nginx access log 로그 없음 확인 및 CDN 을 통한 에러 페이지로의 라우팅 문제를 확인하고, Route53 로드 밸런싱 설정 변경으로 해결
  - 모바일 서버와 API 서버 간 도메인 설정 오류 대응 경험 [🔗](https://medium.com/@EeUuNnYuOuUuNnGg/dns-%EC%98%A4%EB%93%B1%EB%A1%9D-%EB%AC%B8%EC%A0%9C-cad62aff3021)
  - Iptables 의 Hang 문제 발생으로 FTP 서버 1 장애 발생, 동기화 미구성된 ftp 서버 2로 전환. 누락된 매체사의 FTP 계정 및 방화벽 설정 추가, crontab 스크립트 복제 및 ftp Access 확인  [🔗](https://medium.com/@EeUuNnYuOuUuNnGg/ftp-%EC%84%9C%EB%B2%84%EC%9D%98-iptables-%EC%84%A4%EC%A0%95%EC%9D%B4-%EC%B4%88%EA%B8%B0%ED%99%94-%EC%9D%B4%EC%8A%88-%EB%8C%80%EC%9D%91-86b5ec7b914c)
  - FTP 서버 2로 전환 후 2년 뒤 루트 디렉터리가 sudo mv 명령어로 손상되었음. 공간 부족으로 NAS 1에서 NAS 2로 데이터 이전하려고 명령어 실행. 중단 시도하나 이미 손상, 복구 불가 판단. FTP 1 로 Migration 진행. HA 미구성으로 Failover 실패로 빠른 전환이 어려웠지만, FTP 2 iptables, IP 변경으로 대응, 빠른 복구하였음. SFTP, FTP 계정의 home 디렉터리 손상으로 인해 매체사 송고 불가. rsync로 이전 시 권한 옵션 미사용으로 문제 발생. sftp와 ftp 계정 디렉터리 권한 구분 후 복구. 재발 방지를 위해 루트 권한 제한, 명령어 입력 시 상대경로 사용, 항상 HA 구성 필요성 강조. [🔗](https://medium.com/@EeUuNnYuOuUuNnGg/ftp-%EC%84%9C%EB%B2%84%EC%9D%98-%EB%A3%A8%ED%8A%B8-%EB%94%94%EB%A0%89%ED%84%B0%EB%A6%AC%EB%A5%BC-%EC%86%90%EC%83%81-%EC%8B%9C%ED%82%A4%EB%8B%A4-decedc8679e0)
  - Zabbix 모니터링 툴에서 소켓 개수 부족으로 인한 에러로 인해 Zabbix 에러 로그 파일이 증가하고, 이로 인해 서버 스토리지가 가득 차게 되어 서버1은 SSH로 접근이 불가능하며, 서버2는 다운되었습니다. Zabbix의 최대 소켓 개수를 조정하여 이러한 문제를 해결하였고, 더불어 Zabbix 로그를 서버의 스토리지 외부로 저장하도록 수정하였음
  -  서버에 /etc/fstab 설정이 안되어 있어 서버 재부팅시 마운트 해제 이슈 대응
  -  Nas 의 snapshot 으로 용량이슈를 snapshot 설정 off 조치하였음
  -  log4j2 보안이슈 확인하여 담당 서버 어플리케이션 체크 점검

</details>

<details>
  <summary>뉴스줌 PC / MOBILE 프로젝트</summary>

- 기간 
  - 2021.03 ~ 2024.01
- 개요
  - 뉴스줌 PC 프로젝트 https://news.zum.com/ 유지보수
  - 뉴스줌 Mobile 프로젝트 https://m.news.zum.com/ 유지보수
  - Spring MVC Template Engine 과 Jquery 환경의 SSR FrontEnd 프로젝트
- 내용
  - 운영 담당자의 버그 및 장애 보고를 대응하기 위해, 문제 원인을 Controller, API, Batch, 파서 등의 어플리케이션을 분석을 통해 파악하고 문제 대응. 데이터 플로우를 문서화하여 공유
  - HTTP Request 예외 발생에 대한 방어 로직 구현
  - 광고 스크립트 HTML, Javascript, CSS 교체 및 삽입
  - 브라우저 이벤트를 감지하여 통계 서버에 메타데이터 데이터 Request 개발.
  - 송고된 기사의 본문을 뉴스줌 Frontend 환경에 맞게 포매팅하여 노출되도록 문자열 치환 로직 유지 보수
  - IOS의 웹브라우저에서 광고 렌더링 이슈 발생, Webkit 기반 모바일 브라우저에서만 재현되며, 특정 스크립트 재로드로 문제 해결 [🔗](https://medium.com/@EeUuNnYuOuUuNnGg/ios-%EC%9D%98-%EC%9B%B9%EB%B8%8C%EB%9D%BC%EC%9A%B0%EC%A0%80-%EC%97%94%EC%A7%84-%ED%8A%B9%EC%9D%B4%EC%84%B1-%EC%9D%B4%EC%8A%88-f069652b50d9)

</details>

<details>
  <summary>뉴스줌 모바일 어플리케이션의 Frontend-Backend 분리</summary>

- 기간
  - 2023.07
- 개요
  -  Spring MVC Template Engine 프로젝트에서 Api Endpoint 분리 개발.
  -  주로 유지보수와 광고삽입에 집중된 모바일 프로젝트의 안정화 상태를 고려하고. 뉴스줌 서비스의 현대적 FE 사용자 경험 향상을 위해 프론트파트에 서비스를 인계하기 위한 작업 진행하였음.
- 내용 [🔗](https://medium.com/@EeUuNnYuOuUuNnGg/spring-mvc-template-engine-%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8%EC%97%90%EC%84%9C-api-endpoint-%EB%B6%84%EB%A6%AC-%EA%B0%9C%EB%B0%9C-2ca4bb04acd1)
  - 비즈니스 로직이 혼재된 Controller 코드와 JavaScript 코드를 분석하여 API 프로젝트로 Migration.
  - 백엔드 API를 모바일 웹 서비스에서 분리하고, Swagger를 활용하여 API 명세서 문서 작성
  - Migration 과정에서는 기존 서비스에 영향을 주지 않도록 Spring RestController의 새로운 Endpoint 생성 및 Migration할 프로젝트의 API 메서드 추가
  - 스프링 캐시 스케줄러 도입으로 모바일 API 에 캐시 적용. TTL 설정과 주기적 업데이트를 고려하여 안정성 강화.

</details>


<details>
  <summary>뉴스줌 Redis Cache 도입 </summary>

- 기간
  - 2023.02
- 개요
  - Redis Cache 사용하여 분산된 서버의 중복된 데이터를 Redis로 중앙 집중화. 데이터 일관성 확립. MySql 서버 부하 감소를 시켜 안정성과 성능 그리고 물리적 리소스 확보.
  - MySql 데이터 마이그레이션, 코드 리팩터링, 최적화, 운영 전략 등을 통해 성과를 달성.
- 내용 [🔗](https://medium.com/@EeUuNnYuOuUuNnGg/redis-cache-%EB%8F%84%EC%9E%85-8cf4565feb43)
  - Redis의 특성에 맞춰 리소스 효율성을 높이기 위해 싱글스레드 이벤트 기반 비동기를 지원하는 Lettuce Redis Client 를 선택하였음
  - 멀티모듈의 스파게티 코드를 하나의 인터페이스로 통합하여 단일포인트 메서드를 만들고, Redis로의 마이그레이션 진행
  - Sentinel을 활용하여 고가용성을 확보
  - Redis Benchmark를 활용하여 어플리케이션에서 사용하는 SET 및 GET 명령어의 처리량을 테스트하고 안정적인 처리를 확인
  - Graphana 를 이용한 레디스 서버 리소스 모니터링 진행
  - Batch 와 CMS 에서 MySQL 에 캐시하였던 데이터를 Redis 로 Migration 하기 위해 StringRedisSerializer 사용. API 는 Ehache 로부터 Migration 하기 위해 CacheManager 에 GenericJackson2JsonRedisSerializer 설정. 상이한 환경에서 레디스 클라이언트 사용 경험하였음.
  - 안정적인 프로젝트 운영을 위한 배포 및 롤백 시나리오를 구성하여 장애 대응 및 시스템 안정성을 고려
  - 도메인 특성을 고려하여 적절하게 Redis의 maxmemory-policy 정책을 volatile-lru로 설정하여 Expire 설정된 키 중에서 오래된 키를 삭제하도록 구성했습니다.
  - Sentinel 의 부하 분산 방법으로, REPLICA_PREFERRED 선택. GET 명령어는 Replica에서 실행하고, 장애를 대비하기 위해 Replica 를 사용할 수 없을 경우 Master에서 실행하도록 설정하였음.

</details>

<details>
  <summary>뉴스줌 NAS의 static 이미지 삭제 프로젝트 </summary>

- 기간
  - 2022.11 
- 개요
  - 이미지 서버에 요청된 path 로, nginx 의 rewrite 규칙을 적용하여 원본 이미지를 리턴하는 서버가 있다. 여러 스토리지가 다양한 경로로 mount 되어 있기 떄문에 nginx 의 rewrite 규칙이 적용되어 있는 것이다.
  - 기존에 저작권 문제가 있는 이미지 삭제를 위해, nginx rewrite 규칙 대상에 위치하는 리소스의 위치들에서 파일들의 존재여부를 모두 확인하고 이미지 삭제 후, CDN 의 캐시를 purge 하는 과정이 있었다.
  - 이 과정들을 어플리케이션으로 자동화 하도록 개발하였다.
- 내용
  - nginx 의 location, rewrite, root, retry_files 등의 명령어를 코드화하여 요청된 path 와 스토리지에 저장된 이미지를 찾아 원본 이미지를 제거하도록 구현
  - nginx proxy_pass 를 이용한 무중단 배포 환경을 IDC 에서 구성하고, 젠킨스의 빌드 파이프라인을 통해 CICD 환경을 구성함.
  - 이미지 삭제 과정의 단위 테스트 코드 작성
  - 사용자 에러 코드를 정의하여, 이미지 삭제를 요청하는 서버에서 문제를 파악하고 대응할 수 있도록하였음

</details>

<details>
  <summary>뉴스줌 MySQL 업그레이드, 슬로우 쿼리 및 Replication Delay 이슈 해결, 데이터 일관성 강화, 안정성 개선 등 다양한 작업 수행</summary>

- MySQL 슬로우 쿼리로 인한 Connection request timed out 이슈 해결 [🔗](https://medium.com/@EeUuNnYuOuUuNnGg/mysql-slow-query-%EB%A1%9C-%EC%9D%B8%ED%95%9C-connection-request-timed-out-%EC%9D%B4%EC%8A%88-37bf90eda792)
- MySQL 의 Replication Delay 발생사례와 VIP 에서 서버를 제외하여 데이터 갱신 이슈 해결 [🔗](https://medium.com/@EeUuNnYuOuUuNnGg/mysql-%EC%9D%98-replication-delay-%EB%A1%9C-%EC%9D%B8%ED%95%9C-%EB%B2%84%EA%B7%B8-%EB%B0%9C%EC%83%9D-2456ed49f693)
- MySql 5.5 → 8.0 업그레이드
  - 어플리케이션의 mysql connector driver 버전 업그레이드
  - 업그레이드 후 옵티마이저의 쿼리 실행계획의 변경으로 일부, 쿼리들에 straight join Hint 문 추가
  - 트랜잭션에 서로 다른 스토리지엔진의 테이블 접근이 존재할 때 에러나는 이슈, MyISAM 테이블을 innoDB 로 변경
- Slow query 를 유발하는 원인에 대한 해결책을 기획적으로 고민 [🔗](https://www.notion.so/image/https%3A%2F%2Fprod-files-secure.s3.us-west-2.amazonaws.com%2F119ddbc4-c469-4b2a-ad73-653ceed5ec81%2Fa2922253-a639-4a66-9f05-039d2ae18e49%2FUntitled.png?table=block&id=956cd31e-7c21-4da3-9af1-ef501342f886&spaceId=119ddbc4-c469-4b2a-ad73-653ceed5ec81&width=2000&userId=3870e774-c131-4649-accd-876479d0a85d&cache=v2)
- Join 관련 이슈로 인해 테이블 분석 후, 중복 데이터로 인한 2번 노출 문제 해결 [🔗](https://www.notion.so/image/https%3A%2F%2Fprod-files-secure.s3.us-west-2.amazonaws.com%2F119ddbc4-c469-4b2a-ad73-653ceed5ec81%2Fa34ae61d-ef0e-4537-a97c-20383269b15c%2FUntitled.png?table=block&id=f4be9b71-d1c3-4e6e-99d2-a6b10679549d&spaceId=119ddbc4-c469-4b2a-ad73-653ceed5ec81&width=2000&userId=3870e774-c131-4649-accd-876479d0a85d&cache=v2)
- Slave, Master MySql DB 커넥션 안정화와 역할 분리를 하기 위해, API 어플리케이션에서는 Slave Datasource 에서 Read 만 하도록 소스 코드를 변경하였고, API 에서 발생하는 Create, Update, Delete 코드를 Batch 혹은 CMS 어플리케이션으로 Migration 진행
- 실서버 DB 의 리플리케이션이 된 QA DB의, autoincrement duplication 문제 해결
- ISMS 지적사항 수정

</details>

<details>
  <summary>줌인터넷 프로젝트 기능 개발 </summary>

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
    
</details>

<details>
  <summary>뉴스줌 프로젝트 개선</summary>


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

</details>

<details>
  <summary> Quartz Scheduler 어드민의 동적 데이터소스 구현  </summary>

- 기간
  - 2020.12 ~ 2021.02  
- 개요 
  - 다중 데이터 소스를 동적으로 관리하고 모니터링하는 어드민 구현 [🔗](https://zuminternet.github.io/ZUM-Pilot-advanced_quartz_scheduler_admin/)
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

</details>

### Side Project

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
 
#### 바코드 사진 인식 앱 개발
- 개요
  - 모바일 갤러리에서 바코드를 포함한 이미지를 스캔하고 모아서 조회할 수 있는 유틸리티 앱. 흩어진 기프티콘, 멤버십, 교통 티켓 등의 바코드를 통합하여 편리하게 확인할 수 있는 기능을 제공
바코드 조회 시 화면 밝기를 최대로 설정하여 인식율을 높이도록 설계함
    


<details>
  <summary> <h4>Articles </h4></summary>

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

- [Effective Java](https://eyabc.github.io/docs/java/effective-java)
- [Spring Batch](https://gitmind.com/app/docs/m2hhq1nr)
- [Spring Scheduler 와 Quartz](https://gitmind.com/app/docs/mc8juh6u)
- [maven](https://eyabc.github.io/docs/java/spring/maven)
- [Application Context](https://gitmind.com/app/docs/mq2fe55k)
- [DAO, DTO, VO](https://gitmind.com/app/docs/md592dfx)
- [Reactive Programming](https://gitmind.com/app/docs/mdfcledj)
- [REST 서비스의 호출 방법](https://gitmind.com/app/docs/m10hzq4m)
- [SpringBoot version](https://gitmind.com/app/docs/mwwckfjg)
- [gradle](https://gitmind.com/app/docs/mde5qnlt)
- [Interface와 Delegate](https://gitmind.com/app/docs/mcfn0xj9)
- [Spring Null-Safety Annotations](https://gitmind.com/app/docs/mh4yxiqf)
- [Spring Environment](https://gitmind.com/app/docs/m1ap6ib0)
- [ServletConfig 서블릿 초기화 파라미터, ServletContext 컨텍스트 초기화 파라미터](https://gitmind.com/app/docs/mnpviogd)
- [Servlet](https://gitmind.com/app/docs/me3c6ydm)
- [세션(Session)](https://gitmind.com/app/docs/mo9fc6gw)
- [외부에서 설정 주입하기](https://gitmind.com/app/docs/mrp9b1lt)
- [web.xml 파일과 배포서술자(Deployment Descritor)](https://gitmind.com/app/docs/m3olmesm)
- [JOOQ & QueryDSL](https://gitmind.com/app/docs/maa53dmz)
- [ProxyPattern, JDK 동적 프록시와 CGLIB, ProxyFactory, @EnableAspectJAutoProxy\(proxyTargetClass = true\)](https://gitmind.com/app/docs/mt4csms5)
- [Spring with proxy](https://gitmind.com/app/docs/mwikbfq7)
- [spring-boot-starter-data-jdbc <CommonDataSource>, DataSource, DelegatingDataSource, LazyConnectionDataSourceProxy, TransactionAwareDataSourceProxy, PlatformTransactionManager, AbstractPlatformTransactionManager, DataSourceTransactionManager, ConnectionProvider, DataSourceConnectionProvider, TransactionSynchronizationManager](https://gitmind.com/app/docs/mb2lynaq)
- [SpringApplicationBuilder](https://gitmind.com/app/docs/md0q04dg)
- [Spring Actuator](https://gitmind.com/app/docs/mbotrvyj)
- [http 로그 DispatcherServlet 구현](https://gitmind.com/app/docs/mv1gvpsd)
- [Quartz Scheduler & Batch](https://gitmind.com/app/docs/me4honp0)
- [Spring Batch](https://gitmind.com/app/docs/m2hhq1nr)
- [Spring RedisTemplate Serializer 설정](https://gitmind.com/app/docs/m66qxwue)
- [빈 등록 초기화, 소멸 메서드 지정 + InitializingBean, DisposableBean + 빈(Bean) 기능 + @PostConstruct, @PreDestroy 어노테이션 사용법](https://gitmind.com/app/docs/mi4quw6g)
- [JDBC](https://gitmind.com/app/docs/m802w3sx)
- [Jsoup](https://gitmind.com/app/docs/mgzvvebp)
- [Java Throwable](https://gitmind.com/app/docs/ml0aorp8)
- [Java Pacakage & Module](https://gitmind.com/app/docs/mdm2fa0s)
- [jackson JSON Library](https://gitmind.com/app/docs/mnxrnoxr)
- [JDK](https://gitmind.com/app/docs/mwen7za2)
- [JVM은 무엇이며 자바 코드는 어떻게 실행하는 것인가](https://gitmind.com/app/docs/m6mzagrd)
- [자바 데이터 타입, 변수 그리고 배열](https://gitmind.com/app/docs/mm2bnfvn)
- [java collection](https://gitmind.com/app/docs/mlg1dh2n)
- [Spring logging Logback](https://gitmind.com/app/docs/m2znzvgs)
- [Property ‘spring.profiles.active’ imported from location ‘class path resource](https://medium.com/@bey4314/springboot-property-spring-profiles-active-imported-from-location-class-path-resource-b1078ceaccc2)
- [Gradle Mutli-module Property 정의하기](https://medium.com/@bey4314/gradle-mutli-module-property-%EC%A0%95%EC%9D%98%ED%95%98%EA%B8%B0-7a15b9c0bbe7)
- [micrometer](https://medium.com/@EeUuNnYuOuUuNnGg/micrometer-%EB%8F%84%EC%9E%85-68fcce6f167b)
- [SpringBoot Runtime 에서 Bean 생성/삭제](https://medium.com/@EeUuNnYuOuUuNnGg/springboot-runtime-%EC%97%90%EC%84%9C-bean-%EC%83%9D%EC%84%B1-%EC%82%AD%EC%A0%9C-e93133bf1231)
- [Bean 이 아니어도 AOP 를 적용할 수 있는 방법 탐구](https://medium.com/@EeUuNnYuOuUuNnGg/bean-%EC%9D%B4-%EC%95%84%EB%8B%88%EC%96%B4%EB%8F%84-aop-%EB%A5%BC-%EC%A0%81%EC%9A%A9%ED%95%A0-%EC%88%98-%EC%9E%88%EB%8A%94-%EB%B0%A9%EB%B2%95-%ED%83%90%EA%B5%AC-70ab58375462)
- [Logback, Fluentd](https://medium.com/@EeUuNnYuOuUuNnGg/logback-fluentd-fbaf2b10b117)

#### JPA
- [JPA, javax.persistence, Hibernate, Spring Data JPA](https://medium.com/@EeUuNnYuOuUuNnGg/spring-jpa-%EA%B0%9C%EB%85%90-%EC%A0%95%EB%A6%AC%ED%95%98%EA%B8%B0-d32a07dd045a)

#### MySql
- [MySql 필드 값에 여러가지 값을 넣기 위한 방법](https://medium.com/@bey4314/mysql-%ED%95%84%EB%93%9C-%EA%B0%92%EC%97%90-%EC%97%AC%EB%9F%AC%EA%B0%80%EC%A7%80-%EA%B0%92%EC%9D%84-%EB%84%A3%EA%B8%B0-%EC%9C%84%ED%95%9C-%EB%B0%A9%EB%B2%95-be29b68462d1)
- [MySql 쿼리 성능 개선](https://medium.com/@bey4314/mysql-%EC%BF%BC%EB%A6%AC-%EC%84%B1%EB%8A%A5-%EA%B0%9C%EC%84%A0-0141d9d062da)

#### Kafka
- [docker-compose 로 Kafka 컨테이너를 생성하고, 어플리케이션에서 접근하기](https://medium.com/@bey4314/docker-compose-%EB%A1%9C-kafka-%EC%BB%A8%ED%85%8C%EC%9D%B4%EB%84%88%EB%A5%BC-%EC%83%9D%EC%84%B1%ED%95%98%EA%B3%A0-%EC%96%B4%ED%94%8C%EB%A6%AC%EC%BC%80%EC%9D%B4%EC%85%98%EC%97%90%EC%84%9C-%EC%A0%91%EA%B7%BC%ED%95%98%EA%B8%B0-f7915850619c)
- [IntelliJ Kafka 도구 사용하기](https://medium.com/@bey4314/intellij-kafka-%EB%8F%84%EA%B5%AC-%EC%82%AC%EC%9A%A9%ED%95%98%EA%B8%B0-4e9db6b2d742)
- [Java Kafka Consumer 구현](https://medium.com/@bey4314/java-kafka-consumer-%EA%B5%AC%ED%98%84-5c186307800a)
- [Java Kafka CommonErrorHandler 에 예외가 전파되기 전에 AOP 로 예외 처리하기](https://medium.com/@bey4314/java-kafkalistenrerrorhandler-%EC%97%90-%EC%98%88%EC%99%B8%EA%B0%80-%EC%A0%84%ED%8C%8C%EB%90%98%EA%B8%B0-%EC%A0%84%EC%97%90-%EC%98%88%EC%99%B8-%EC%B2%98%EB%A6%AC%ED%95%98%EA%B8%B0-0d8c621f571f)
- [Kafka Streams 기반의 분산 처리와 모니터링 개선 사례 연구](https://medium.com/@EeUuNnYuOuUuNnGg/efk-kafka-logback-%EC%9D%B4%EA%B2%83%EC%A0%80%EA%B2%83-f9b8e94d1303)

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
- [함께자라기](https://eyabc.github.io/docs/consultant/%ED%95%A8%EA%BB%98%EC%9E%90%EB%9D%BC%EA%B8%B0/index)
- [소프트웨어 공학](https://gitmind.com/app/docs/mr7xhjad)

  
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

#### Database
- [Managing Hierarchical Data in MySQL](https://eyabc.github.io/docs/database/ManagingHierarchicalData_in_MySQL)
- [오라클 전문가로 가는 지름길](https://eyabc.github.io/docs/database/오라클_전문가로_가는_지름길/1-자료의조회)
- [dynamoDB](https://eyabc.github.io/docs/database/dynamoDB/1-Introduction)
- [Introduction to Redis](https://eyabc.github.io/docs/database/redis/Introduction%20to%20Redis/)
- [MongoDB 완벽가이드](https://medium.com/@bey4314/mongodb-완벽-가이드-05e9e5459a55)
- [mysql json](https://gitmind.com/app/docs/m8zqw2s5)
- [Redis Stream](https://gitmind.com/app/docs/m4zmn1vw)
- [이것이 레디스다](https://gitmind.com/app/docs/mr4ubzki)

#### Infrastructure
- https://eyabc.github.io/docs/infra/index
- [load_balancing](https://eyabc.github.io/docs/infra/load_balancing)
- [Web Server와 WAS](https://gitmind.com/app/docs/mfk7xoyo)
- [Access Control](https://gitmind.com/app/docs/mfpzn9dh)
- [docker](https://gitmind.com/app/docs/mc9ub2zq)
- [RAID](https://gitmind.com/app/docs/miru87x1)
- [수동 IP 로 변경하기](https://gitmind.com/app/docs/m931d7fe)

#### Javascript & Browser
- [Javascript](https://eyabc.github.io/docs/javascript/javascript/index)
- [객체지향 Javascript](https://eyabc.github.io/docs/javascript/OOP/OOP_value_and_identifier_context)
- [Browser window-opener](https://eyabc.github.io/docs/javascript/browser/window-opener), [Browser_Event](https://eyabc.github.io/docs/javascript/browser_events/Browser_Event)
- [Clean Code Javascript](https://eyabc.github.io/docs/javascript/clean_code/CleanCodeJavascript#변수-variables), [airbnb js style guides](https://eyabc.github.io/docs/javascript/airbnb_js_style_guides/%EC%9E%90%EB%B0%94%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8%20%EC%8A%A4%ED%83%80%EC%9D%BC%20%EA%B0%80%EC%9D%B4%EB%93%9C/)
- [Javascript 함수형 프로그래밍](https://eyabc.github.io/docs/javascript/functional_programming/1_%ED%95%A8%EC%88%98%ED%98%95_%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D_%EA%B0%9C%EC%9A%94/)
- [Javascript 비동기 프로그래밍](https://eyabc.github.io/docs/javascript/asynchronous_programming/Sync%20Async/)
- [Javascript 모듈](https://eyabc.github.io/docs/javascript/module/%EB%AA%A8%EB%93%88/)
- [Javascript 객체](https://eyabc.github.io/docs/javascript/object/%EA%B0%9D%EC%B2%B4%20%EA%B8%B0%EB%B3%B8%20%EB%AC%B8%EB%B2%95/)
- [next.js](https://eyabc.github.io/docs/nest-js/index)
- [html](https://eyabc.github.io/docs/html/index)
- [css background-image](https://eyabc.github.io/docs/css/background-image) [graphics_system](https://eyabc.github.io/docs/css/css-rendering/graphics_system)
- [HTTP headers Referrer 보안이슈](https://eyabc.github.io/docs/network/HTTP_headers_Referer_보안이슈)
- [CORS](https://eyabc.github.io/docs/network/CORS)
- [HTTPS 를 개발환경에서 사용하는 이유](https://eyabc.github.io/docs/network/HTTPS_를_개발환경에서_사용하는_이유)


### Book
- [Real MySQL 8.0 (1권)](https://search.shopping.naver.com/book/catalog/32443973624?query=Mysql%208.0&NaPm=ct%3Dlw7gpmy8%7Cci%3D32cea7114111a158e964d9be5c0c7fa73cfd7af7%7Ctr%3Dboksl%7Csn%3D95694%7Chk%3D5bc7b1d55bfde67cae5194b43438b99fc60c30ed)
- [이것이 레디스다](https://search.shopping.naver.com/book/catalog/32436028951?query=%EC%9D%B4%EA%B2%83%EC%9D%B4%20%EB%A0%88%EB%94%94%EC%8A%A4%EB%8B%A4&NaPm=ct%3Dlw7gqnzk%7Cci%3D17a10802e0c9cbf97ef55bff9cdade78631e2969%7Ctr%3Dboksl%7Csn%3D95694%7Chk%3Db45e38a69a38726078cbec6d00669cc9bfb1b7d8)
- [리팩터링](https://www.yes24.com/Product/Goods/89649360)
- [Java의 정석](https://search.shopping.naver.com/book/catalog/32466681076?cat_id=50010920&frm=PBOKPRO&query=Java+%EC%9D%98+%EC%A0%95%EC%84%9D&NaPm=ct%3Dlw7gw048%7Cci%3D6d50d41884f105fdd1789de7b5997091ea592337%7Ctr%3Dboknx%7Csn%3D95694%7Chk%3D3b79e636e98238b285a7696dfb9ca84aba974338)
- [밑바닥부터 만드는 컴퓨팅 시스템](https://search.shopping.naver.com/book/catalog/39383703623?cat_id=50010921&frm=PBOKPRO&query=%EB%B0%91%EB%B0%94%EB%8B%A5%EB%B6%80%ED%84%B0+%EB%A7%8C%EB%93%9C%EB%8A%94+%EC%BB%B4%ED%93%A8%ED%8C%85+%EC%8B%9C%EC%8A%A4%ED%85%9C&NaPm=ct%3Dlw7gwxao%7Cci%3Dca55422478c3ddb738d46eb7d86a85358cf81939%7Ctr%3Dboknx%7Csn%3D95694%7Chk%3Df5cf1ea2bbae389d59ab4d7d5f971437d06ac640)
- [스프링 입문을 위한 자바 객체 지향의 원리와 이해](https://search.shopping.naver.com/book/catalog/32462919817?cat_id=50010920&frm=PBOKPRO&query=%EC%8A%A4%ED%94%84%EB%A7%81+%EC%9E%85%EB%AC%B8%EC%9D%84+%EC%9C%84%ED%95%9C+%EC%9E%90%EB%B0%94+%EA%B0%9D%EC%B2%B4+%EC%A7%80%ED%96%A5%EC%9D%98+%EC%9B%90%EB%A6%AC%EC%99%80+%EC%9D%B4%ED%95%B4&NaPm=ct%3Dlw7gxsxk%7Cci%3D09f7a89688a71d5324542a08cccf981af11bccfa%7Ctr%3Dboknx%7Csn%3D95694%7Chk%3D5b5f855b66aa95ee8316e70a9ac5bb60ab01236d)
- [MongoDB 완벽 가이드](https://search.shopping.naver.com/book/catalog/32481967929?cat_id=50010586&frm=PBOKPRO&query=MONGODB+%EC%99%84%EB%B2%BD+%EA%B0%80%EC%9D%B4%EB%93%9C&NaPm=ct%3Dlw7gyt74%7Cci%3D7a6c1982bb77a030462df471eee56ad34fe49ab3%7Ctr%3Dboknx%7Csn%3D95694%7Chk%3Da628c67a344293ad848763efedcbc698a3d665cf)

</details>
