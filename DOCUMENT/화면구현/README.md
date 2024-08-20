<h1>화면 구현</h1>		
		
				
<h2>HTML</h2>		
		
html- hyper text markup language 약어로 hypertext(웹 페이지에서 다른 페이지로 이동할 수 있도록 하는 것) 기능을 가진		
문서를 만드는 언어		
		
시멘틱 마크업 (head, body, footer)		
		
element - content를 감싸는 태그		
		
<!DOCTYPE html> : 문서의 유형을 선언, HTML 문서파일		
		
<html lang="ko"></html> : HTML문서의 시작/끝, lang 속성을 이용하여 문서의 기본언어가 한국어임을 명시		
		
<head></head> : 문서의 메타데이터와 제목등을 포함하는 머리말		
		
<meta charset="UTF-8"> : 문서의 문자 인코딩을 UTF-8으로 설정 		
		
<meta name="viewport" content="width=device-width, initial-scale=1.0"> - 반응형 웹 디자인을 위한 뷰포트 설정		
:width=device-width : 뷰포트의 너비를 디바이스의 너비만큼 지정		
initial-scale=1.0 : 페이지가 처음 로드될때 기본 확대/축소 수준을 지정		
		
<body></body> : 문서의 본문, 브라우저에 viewport(웹페이지를 사용자가 보는영역)에 표시되는 내	용		
		
auto rename tag : 태그의 시작 또는 끝을 수정하면 자동으로 수정		
		
live server : rerode를 수동으로 하지 않아도 자동으로 반영		
		
prettier : 코드 자동 정렬		
		
태그는 라인형 태그와 블럭형 태그로 나눠짐 		
- 블럭형 태그 : 사용하면 행 전체를 사용 <div>		
- 라인형 태그 : 한 행 안에 포함되어서 사용되는 태그 <span>		
		
<h3>EMMET</h3> 	
자식요소 : > 사용 (div>ul>li)		 </br>
형제 : + 사용 (div>ul+ol)		</br>
상위태그 : ^ 사용 (div>ul>li^p)		</br>
문자열처리 : {}사용 (div>ul>li*4>a{기본메뉴})		</br>
반복처리 : * 사용 (div>ul>li*3)		</br>
인덱스처리: $ 사용 ( div>ul>li*4>a{$.기본메뉴}) : 숫자가 나온다		</br>
클래스 선택자 : . 사용 (div.items)		</br>
ID선택자 : # 사용 (div#slider)		</br>
LAYOUT EMMET : .wapper>header>.top-header+nav^main>section^footer		</br>
attr 추가 : [] 사용 (div>ol[type="I"])		</br>
시작 인덱스 번호 지정 : @ 사용 (div>ul>li*4{TEXT_$@5})	1</br>		
		
table 태그 안에는 기본적으로 만들지 않아도 tbody 태그가 들어간다. (나중에 js쓸때 주의)		
div>ul>li>a+ul>li>a : 기본 메뉴구조		

table 행병합 : rowspan		
table 열병합 : colspan		
		
a 태그 target = "_blank" : 새 탭에서 이동		
		
a href javascript:void(0) : href에 아무것도 넣지 않아도 #이 자동으로 들어가서 현재 위치로 이동하기 때문에 나중에 문제가 생길수 있음. 꼭 javascript:void(0) 를 넣어서 방지하기.		


<h3>video</h3> 
<video> <source src ="img" type="video/mp4">

type 로 비디오냐 문서냐 이미지냐 구분

type = "video/mp4" 파일명 구분

<h4> video 태그 속성 </h4> 
controls autoplay - 비디오 자동재생
muted - 음소거가 아니면 자동재생이 안됨 (js api를 써야함)
loop - 무한재생

<h4>form</h4>
form : 사용자로부터 특정정보를 받아 서버로 전달하는데 사용되는 태그

action attribute : 전달받는 서버 API() (or Endpoint)
mehod attribute : 서버로 요청 방식 
  -GET : 사용자 요청 정보를 QUERY STRING으로 전달(DEFAULT)
  -POST : 사용자 요청 정보를 REQUEST BODY에 담아 전달(OPTIONAL)
  -PUT 
  -PATCH
  -DELETE

<h5>input</h5>
type : email = 이메일 타입 (@넣지않으면 유효성에서 탈락)
       password = 비밀번호 타입 (별으로 표시됨) 
       radio = 택1 할때 선택 (name을 동일하게 하지 않으면 둘다 선택이 가능해짐)
       tel = 전화번호 입력 시 사용 pattern 속성 사용 가능 (pattern="[0]{1}[1]{1}[0]{1} - 010만 가능)
       checkbox = 여러개 선택 가능 (동일한 파라미터에 여러 벨류값들을 전달할 때 사용)
       file = 파일 업로드 할 때 사용 (multiple 사용 시 여러 파일 선택가능)
       submit = button과 동일 form action 실행 
       date = 날짜 
       select = 여러목록에서 하나를 선택할때 사용 <select name=""> <option value="">대구</option> (selected 넣으면 디폴트값으로 설정)
       required = 입력 안하면 안넘어감
       readonly = 입력 불가 (값은 전달 됨) - value로 전달
       disabled = 입력 불가 (값이 전달 안됨)
       oninvaild : 유효하지 않은 이벤트가 들어왔을 때
       
^(?=.*[A-Za-z])(?=.*\d)[A-Za-z\d]{8,}$ 해석
^ : 문자열의 시작
$ : 문자열의 끝
()  :패턴을 구분하는 부분식
?= : 전방탐색
. : 모든 문자 일치
* : 앞의 문자나 부분식이 0개 이상 탐욕적으로 찾기
[A-za-z] : 영어 알파벳이 하나이상 포함되어야 한다(대문자, 소문자)
\d : 모든 숫자와 일치, [0~9]와 동일 

^(?=.*[A-Za-z]) : 전방탐색(?=), 임의의 문자가 0개 이상 존재할 경우(.*) 영문 대문자/ 소문자 이상 하나이상 포함하는지 여부 ([A-Za-z])















