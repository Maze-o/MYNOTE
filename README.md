# 정보처리산업기사 과정평가형 메모

<h2>1. OSI 7계층 정리 (2024.07.30)</h2>

<h4>물리계층</h4>
- 실제 장치를 전선(케이블,리피터,허브)로 연결해서 디지털 신호(부호)를 (전기 에너지, 통신망)을 통해 전달
  케이블 - UTP,STP,FTP 등

<h4>데이터링크 계층</h4>
- 장치 (Point to Point)간 운송방식을 결정하기 위해 존재 (신뢰성을 보장하는 역할)
  그러기 위해서 장치 식별 ,연결 제어, 흐름 제어 필요

    데이터 링크에 사용되는 프로토콜(운송방식)
  - LAN (근거리 통신망) - Ethernet
  - WAN (광역, 원거리 통신망) - HDLC, PPP, ATM, Frame Relay

    이더넷 프로토콜 - LAN 환경에서 거의 절대 다수를 차지하는 프로토콜
    초기 이더넷 사용 방식 : CSMA/CD -찔러보며 매체가 사용중인지 확인 하며 눈치보고 들어가는 방식
    (5차선에서 1차선으로 좁아지는 고속도로 느낌)
    문제 - 통신이 많아지면 충돌 발생 ' 해결방안 - L2 SWITCH 사용

<h4>네트워크 계층</h4>
-데이터를 목적지로 빠르고 정확하게 안내하기 위한 경로탐색을 함(네비게이션 느낌), 라우터 사용

  프로토콜 종류
  -IP : 인터넷에서 사용되는 주소
  -ICMP : 통신 가능여부를 확인
  -ARP
  -Routing Protocol - 최적 경로탐색에 사용되는 프로토콜(네비게이션 어플 느낌)

<h4>전송 계층</h4>
-End to End 호스트간 데이터가 잘 왔는지 확인 하고, 종단간 데이터의 신뢰성을 보장

  프로토콜 종류
  -TCP : 연결지향 신뢰도높음 (느리지만 보안이 좋다)
  -UDP : 비연결지향 신뢰도낮음 (빠르지만 보안이 좋지 않다)

<h3>문제풀이는 github 참조</h3>
---------------------------------
</div>
<h2>네트워크 실습 (2024.07.31)</h2>
Routing Protocol - 라우터 2개 이상부터 사용
1. 정적 Routing (수동으로 넣는방법) - Static(하나의 목적지에 대한 방향)과 
				Default(지정하지않은 나머지 모든 방향)로 나눠짐

2. 동적 Routing (프로그램이 알아서 넣는 방법)

Route : 길/경로
Router : 경로안내장치
Routing : 길안내작업

경로를 안내해주기 위해서 사용되는 프로토콜

1. IP입력		

2.응용Sw기초기술활용 > 01 네트워크 기초활용하기 > 05 Routing > 정적라우팅		
11번문제 시험에 똑같이 나옴 꼭 한번 다시 풀기!!		

3.응용Sw기초기술활용 > 01 네트워크 기초활용하기 > 05 Routing > RIP DNS+HTTP > 6번문제		

4. 미들웨어 구축 문제		

5. mysql DB - Database -  Forward Engineer(다이어그램 DB테이블로 바꾸기) , Reverser Engineer(DB테이블 다이어그램으로 바꾸기

6. crud		

DNS SERVICE (스마트폰의 주소록과 비슷한 역할) / SYSTEM / SERVER		
Domain Name Service / System / Server
    
Domain : 영역		
Name : 이름		
Service : 제공하다		

WEB SERVICE 		
하이퍼텍스트 형식의 문서파일을 제공하는 서비스		

HTML
Hyper Text Markup Language

HTTP
Hyper Text Transfer Protocol


프로젝트 메모

개념(조직화,관계도,그림,무슨 기능을 넣을것인지) -> 논리(탭에 대한 필요한 세부항목) -> 물리(개발환경 구축)
draw.io

주유소 정보 만들 예정.

기능 - 주유소 위치(지도에서 반경 내 위치), 가격(평균가격, 경유, 휘발유)
-주유소 api, 지도 api 필요

-스프링부트, 타임리프, 마이바티스

io.start.spring 사이트를 이용하면 쉽게 프로젝트 템플릿 파일을 얻을 수 있다

빌드구성 - maven or gradle . gradle 픽
편집툴 - 이클립스
DBMS - 오라클
DB Connect - JPA
View Template - thymeleaf
배포파일 - BootWar
배포서버 -
AWS EC2 - AWS 정식 서버 버젼, 1년 무료후 유료(유료가 비쌈. 몇만원대)
AWS 라이트세일 - AWS 가상서버 버전, 3달무료 후 한달에 5천원 발생. 사용량 만큼이므로 잠시 정지시켜 두거나, 필요없을시 지워도 됨.

https://blog.naver.com/nissisoft21/222802517122


<h2>2024 08 06</h2>
시험에 나옴 	
mysql DB - Database -  Forward Engineer(다이어그램 DB테이블로 바꾸기) , Reverser Engineer(DB테이블 다이어그램으로 바꾸기)		





