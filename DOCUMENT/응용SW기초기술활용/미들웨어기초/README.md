<h2>JDK 설치 </h2>
open jdk version 설치 후 sysdm.cpl -> 고급 -> 환경변수 -> path에 jdk 경로 추가 후 제일 위로 올리기

<h2>이클립스 설치</h2>
window -> preference -> files 검색 후 css, html, jsp, xml UTF-8 설정, workspace UTF-8 설정

<h2>톰캣 설치 </h2>

apache tomcat 사이트에서 설치 후
services.msc -> apache tomcat 설치 확인 -> 실행 -> localhost:8080 실행 확인 -> 중지

이클립스에서 연동 : 
file -> new - other -> server 검색 후 톰캣 설치 경로로 browse (꼭 설치경로 안으로 들어가서 권한 허용 해야함!!)
하단 탭 server 에 있는 톰캣 더블클릭 후 tomcat adimin port 설정
프로젝트 src -> main -> webapp -> WEB-INF -> lib 안에 tomcat -> lib 안에 있는 jsp-api.jar , servlet-api.jar 붙여넣기

