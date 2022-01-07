1. API 구현 계획 수립
  <br>○ 스프링 부트 활용
	<br>   - json 구조로 총 로그인 수 3명, 20년도, 정상적인 결과임을 나타내는 값


2. 개발환경 셋팅

  <br>○ 환경 설정
     <br>- Maven 자바 버전은 11
 	    <br>- Spring Boot Devtools, Spring Web, MyBatis Framework 만 선택
 	    <br>- 부트 버전 2.6.1
	    
<br>○ pom.xml 수정 
	<br>- dependency에 org.mariadb.jdbc, rg.apache.tomcat.embed, org.springframework.boot, org.mybatis.spring.boot를 추가


3. DB 구축
<br>○ DATABASE statistc
	<br>- Table statistc.requestInfo 
		requestID numeric NOT NULL primary key,
    		requestCode varchar(5) NOT NULL,
   		userID varchar(5),
    		reateDate varchar(10)
	<br>- table statistc.requestCode
		requestCode varchar(5) NOT NULL primary key,
    		code_explain varchar(50) NOT NULL
	<br>- table statistc.user
		userID varchar(5) NOT NULL primary key,
    		HR_ORGAN varchar(5) NOT NULL,
    		USERNAME varchar(5) NOT NULL


4. 20년도 로그인수 API 구현
  <br>○ Mybatis 설정
     <br> - sql 및 bean 설정
     
 <br>○ mapper 작성
	<br>- Hashmap을 생성하는 selectYearLogin 설정 및 20년도 로그인 수를 찾는 쿼리 작성
	
 <br>○ service 구현
	<br>- mapper에 작성한 selectYearLogin을 활용해서 Hashmap형태로 return하고 값을 json형태로 변환 및 화면에 출력



○ 어려웠던 점
- 스프링 부트를 따로 설치했다. 이전 STS 버전으로는 프로젝트가 실행되지 않았다.
- pom.xml 설정하기 (필요한 dependency를 찾는 것)
- 패키지 이름 설정 (오타 때문에 이름에 차이가 있어서 test과정에서 화면으로 json정보를 출력하는 것이 진행 되지 않았다.)
- DB 설정 계속해서 exception으로 실행이 되어서 없애고 찾아보니 db에서 가져오지 못하는 것이었다.
- 아이디와 비번을 잘 설정해주니 잘 되었다.
