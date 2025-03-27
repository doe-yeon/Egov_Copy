# Egov_Copy
패키지 구조 이해, 주요 파일 분석<br>

Spring 노베이스 🤣<br>

**🚀먼저!!**

1️⃣ 패키지 구조 이해하기<br>
egovframework.example.cmmn → 공통 기능 (ExceptionHandler 등)<br>
egovframework.example.sample.service → 서비스 로직 (비즈니스 로직)<br>
egovframework.example.sample.web → 컨트롤러 (요청 처리)<br>
src/main/resources → 설정 파일 (log4j2.xml, spring, sqlmap 등)<br>
<br>
💡 👉 해야 할 것:<br>
✔ 각 패키지 안의 클래스들 이름/역할 정리<br>
✔ service, web, cmmn 간의 연결 구조 파악<br>
<br>
2️⃣ 주요 파일 분석 (순서대로 읽기)<br>
📌 [1] log4j2.xml → 로그 설정<br>
📌 [2] spring/*.xml → Spring 설정<br>
📌 [3] sqlmap/*.xml → MyBatis(SQL 매핑)<br>
📌 [4] service 패키지 → 인터페이스 & Impl 확인<br>
📌 [5] web 패키지 → Controller 역할 파악<br>
<br>
💡 👉 해야 할 것:<br>
✔ 설정 파일 한 번씩 열어보고 역할 파악<br>
✔ 서비스 로직(Impl)과 Controller가 어떻게 연결되는지 따라가 보기<br>
<br>
3️⃣ 간단한 기능 추가해보기 (실습 추천)<br>
egovframework.example.sample 패키지에 새로운 서비스 & 컨트롤러 추가<br>
<br>
예제 데이터(DB 없이 가짜 데이터)로 목록 조회 기능 만들어보기<br>
<br>
💡 👉 해야 할 것:<br>
✔ 기존 Sample 코드 복사해서 TestSample 같은 새 기능 만들기<br>
✔ 컨트롤러 추가하고 화면에서 출력 확인<br>
<br>
📢 💡 요약<br>
✔ ① 패키지 구조부터 이해<br>
✔ ② 설정 파일(log4j, Spring, SQL) 한 번씩 보기<br>
✔ ③ 서비스 & 컨트롤러 흐름 익히기<br>
✔ ④ 간단한 기능 추가해보면서 응용<br>
<br><br>

================================================================================================<br>
<br>
**🚀 카피해가며 공부하기!!**<br>

1️⃣ 전체 파일 구조 카피 (그대로 가져오기)<br>
2️⃣ 필요한 주요 파일만 직접 작성해보기 (빈칸 채우기 방식)<br>
3️⃣ 코드 흐름 따라가면서 작동 방식 익히기<br>
4️⃣ 작은 기능 추가하면서 응용 연습<br>
<br>

🔹 꼭 카피해보면 좋은 파일 (필수)<br>
✔ Controller (web 패키지)<br>
✔ Service (service 패키지, Impl 포함)<br>
✔ Mapper(XML, sqlmap 폴더)<br>
✔ 설정 파일 (spring/*.xml, log4j2.xml)<br>
<br>
💡 👉 이유:<br>
Controller → Service → Mapper 흐름을 익히는 게 중요<br>
sqlmap/*.xml에서 DB와 연결되는 방식 익히기<br>
spring/*.xml에서 Bean 설정 방식 이해<br>
<br>

🔸 카피 안 해도 되는 파일 (참고용)<br>
✖ 기본 예외 처리 (cmmn 패키지 일부)<br>
✖ 테스트 코드 (src/test/java)<br>
✖ 자동 생성된 target/, generated-sources/ 폴더<br>
<br>
💡 👉 이유:<br>
예외 처리는 기본 흐름만 이해하면 직접 구현할 때 참고하면 됨<br>
테스트 코드는 처음엔 안 봐도 무방<br>

<br><br>
================================================================================================<br>
<br><br>

**🚀 추가 공부!!**<br>

🔹 설정 파일 추가 분석 → context-datasource.xml, context-transaction.xml<br>
🔹 MyBatis CRUD 실습 → sqlmap/sample.xml에 새 SQL 추가<br>
🔹 보안 & 예외처리 학습 → context-security.xml, web.xml<br>
🔹 AOP + 로깅 실습 → context-aspect.xml, log4j2.xml<br>
🔹 배포 테스트 (WAR 빌드 & 실행)<br>
<br>
1️⃣ Egov 주요 개념 & 설정 파일 추가 공부<br>
🔹 추가로 보면 좋은 설정 파일들 ✔ context-datasource.xml → DB 커넥션 관리 (HikariCP 등)<br>
✔ context-transaction.xml → 트랜잭션 설정 (AOP 기반)<br>
✔ context-aspect.xml → AOP 설정, 로깅 및 공통 처리<br>
✔ dispatcher-servlet.xml → 스프링 MVC 설정<br>
<br>
💡 왜 공부해야 해?<br>
egov는 기본적으로 Spring 기반 + MyBatis 조합이라 설정 파일을 이해하면 흐름을 쉽게 파악 가능<br>
특히, 트랜잭션 설정(AOP), DB 연결, MVC 흐름(dispatcher-servlet.xml) 익혀두면 다른 프로젝트에도 응용 가능<br>
<br>
2️⃣ DB 연동 기능 확장 (MyBatis & SQL 학습)<br>
🔹 SQL 관련 추가 분석 ✔ sqlmap/*.xml → MyBatis에서 SQL을 어떻게 매핑하는지 분석<br>
✔ context-mapper.xml → MyBatis 설정 파일 확인<br>
<br>
💡 실습 추천<br>
✅ sqlmap/sample.xml에 새로운 SQL 추가<br>
✅ 기존 샘플 서비스 확장 → CRUD 기능 직접 추가해보기<br>
✅ MyBatis Mapper를 활용한 동적 SQL(<if>, <foreach> 등) 활용<br>
<br>
3️⃣ 보안 & 예외처리 추가 학습<br>
🔹 보안 관련 설정 파일 ✔ context-security.xml → Spring Security 설정 확인<br>
✔ web.xml → 필터/인터셉터 설정 분석<br>
<br>
💡 이거 공부하면 좋은 이유<br>
Spring Security가 어떻게 적용되는지 기본 흐름 이해<br>
web.xml에서 XSS, CSRF 방어용 필터 설정 확인<br>
<br>
4️⃣ 로그 및 AOP 학습 (서비스 추적 연습)<br>
🔹 AOP 활용해서 로그 남기는 방식 학습 ✔ log4j2.xml → 로그 출력 방식(Custom 로그 추가해보기)<br>
✔ context-aspect.xml → AOP 기반 공통 처리 분석<br>
<br>
💡 추천 실습<br>
✅ 기존 서비스에 "서비스 실행 시간 측정" 기능 추가 (@Around 활용)<br>
✅ AOP로 "메서드 실행 시 로그 자동 남기기" 실습<br>
<br>
5️⃣ 배포 및 실행 환경 이해 (WAR & Tomcat)<br>
🔹 실제 배포할 때 필요한 파일 & 설정 학습 ✔ pom.xml → war 패키징 확인 (빌드 옵션 추가 가능)<br>
✔ web.xml → 서블릿 & 필터 설정 분석<br>
✔ target/*.war → 빌드 결과물이 어떻게 나오는지 확인<br>
<br>
💡 배포 실습 추천<br>
✅ mvn clean package로 직접 빌드 실행<br>
✅ Tomcat에서 .war 파일 배포 & 실행 테스트<br>
<br><br>


