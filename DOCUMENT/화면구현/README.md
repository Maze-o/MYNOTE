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
		
table 태그 안에는 기본적으로 만들지 않아도 tbody 태그가 들어간다. (나중에 js쓸때 주의)	</br>	
div>ul>li>a+ul>li>a : 기본 메뉴구조		</br>

table 행병합 : rowspan		</br>
table 열병합 : colspan		</br>
		
a 태그 target = "_blank" : 새 탭에서 이동		</br>
		
a href javascript:void(0) : href에 아무것도 넣지 않아도 #이 자동으로 들어가서 현재 위치로 이동하기 때문에 나중에 문제가 생길수 있음. 꼭 javascript:void(0) 를 넣어서 방지하기.</br>		


<h3>video</h3> 
(video) (source src ="img" type="video/mp4")</br>

type 로 비디오냐 문서냐 이미지냐 구분</br>

type = "video/mp4" 파일명 구분</br>

<h4> video 태그 속성 </h4> 
controls autoplay - 비디오 자동재생</br>
muted - 음소거가 아니면 자동재생이 안됨 (js api를 써야함)</br>
loop - 무한재생</br>

<h4>form</h4>
form : 사용자로부터 특정정보를 받아 서버로 전달하는데 사용되는 태그</br>

action attribute : 전달받는 서버 API() (or Endpoint)</br>
mehod attribute : 서버로 요청 방식 </br>
  -GET : 사용자 요청 정보를 QUERY STRING으로 전달(DEFAULT)</br>
  -POST : 사용자 요청 정보를 REQUEST BODY에 담아 전달(OPTIONAL)</br>
  -PUT </br>
  -PATCH</br>
  -DELETE</br>

<h5>input</h5>
type : email = 이메일 타입 (@넣지않으면 유효성에서 탈락)</br>
       password = 비밀번호 타입 (별으로 표시됨) </br>
       radio = 택1 할때 선택 (name을 동일하게 하지 않으면 둘다 선택이 가능해짐)</br>
       tel = 전화번호 입력 시 사용 pattern 속성 사용 가능 (pattern="[0]{1}[1]{1}[0]{1} - 010만 가능)</br>
       checkbox = 여러개 선택 가능 (동일한 파라미터에 여러 벨류값들을 전달할 때 사용)</br>
       file = 파일 업로드 할 때 사용 (multiple 사용 시 여러 파일 선택가능)</br>
       submit = button과 동일 form action 실행 </br>
       date = 날짜 </br>
       select = 여러목록에서 하나를 선택할때 사용 (select name="") (option value="")대구(/option) (selected 넣으면 디폴트값으로 설정)</br>
       required = 입력 안하면 안넘어감</br>
       readonly = 입력 불가 (값은 전달 됨) - value로 전달</br>
       disabled = 입력 불가 (값이 전달 안됨)</br>
       oninvaild : 유효하지 않은 이벤트가 들어왔을 때</br>
       </br>
(해석^(?=.*[A-Za-z])(?=.*\d)[A-Za-z\d]{8,}$ 해석)</br>
^ : 문자열의 시작</br>
$ : 문자열의 끝</br>
()  :패턴을 구분하는 부분식</br>
?= : 전방탐색</br>
. : 모든 문자 일치</br>
* : 앞의 문자나 부분식이 0개 이상 탐욕적으로 찾기</br>
[A-za-z] : 영어 알파벳이 하나이상 포함되어야 한다(대문자, 소문자)</br>
\d : 모든 숫자와 일치, [0~9]와 동일 </br>
</br>
^(?=.*[A-Za-z]) : 전방탐색(?=), 임의의 문자가 0개 이상 존재할 경우(.*) 영문 대문자/ 소문자 이상 하나이상 포함하는지 여부 ([A-Za-z])</br>


<h2>CSS</h2>

적용법 - 1. style 태그를 만들어서 적용</br>
	2. 단일 태그(inline) 안에 style 속성을 넣어서 적용 (유지보수가 힘들어서 권장하지않음)</br>
 	3. 외부 파일으로 link</br>
  	(충돌이 일어나면 가장 나중에 있는 style을 적용)</br>
  	강제 적용 :  !important 속성 (남발 x 나중에 반응형 쓸때 모바일 적용을 위해 사용 할수도 있다)</br>

display: block; - 블럭형 태그로 지정</br>
display: line; 라인형 태그로 지정</br>

width : auto; //너비 (default값 : auto, 전체너비 사용) </br>
	width의 auto : 브라우저의 너비만큼 쓰려고 하는 성질이 있다</br>
height : auto; //높이 (default값 : auto, 최소한의 높이 사용)</br>
	height의 auto : 최소한의 높이를 가지려고 하는 성질이 있다</br>

min-width : 최소 너비 </br>
max-width : 최대 너비</br>
min-height : 최소 높이</br>
max-height : 최대 높이 height가 auto일시 의미가 없어짐 (작아질려고 하기 때문에)</br>

자식간의 수평 가운데 배치법
1. 부모요소에 display: flex; , justify-content: center; align-items: center;
2. 부모요소에 position: relative; 자식요소에 left, right, top, bottom 을 0으로 설정 , margin: auto;


<h4>margin , border, padding</h4>
margin = 요소간의 간격을 지정 </br>

margin: 20px 40px // 20px : top bottom // 40px : left,right으로 적용		
margin: 10px 20px 30px // 10px : top // 20px : right left // 30px : bottom 으로 적용	
margin: 10px 20px 30px 40px; // 시계방향으로 적용		

border = 내용 사이의 간격을 지정할때 사용</br>
border: 1px 옵션들 : 
	1. solid : 테두리 생성
	2. dashed : 대시선
 	3. dotted : 점선
  	4. double : 선두개
   	
border-radius: 15px (테두리 깎기)
border-radius: 15px 35px 50px 100px; (시계방향으로 깎음)

<br>

padding = 테두리와 border 사이의 간격</br>



block tag = 한 행전체를 차지하는 태그</br>
-width : o , height : o</br>
-margin : 0, padding : 0</br>
line tag = 한 행안에 포함되어지는 태그</br>
-width : o , height : o</br>
-margin : left, right만 o, padding :o</br>
inline-block tag = 한 행안에 포함되어지는 태그  (line형안에 포함되어있다)</br>
-width : o , height : o</br>
-margin : 0, padding : 0</br>

<hr/>
<h3>단위</h3>
px : 고정크기 </br>
% : 가변크기 // 상위태그를 기준으로 %만큼 크기 지정</br>
vw, vh : 가변크기 // viewport(브라우저에 표시되는 영역)를 기준으로 백분율만큼 크기지정 </br>
rem : 상대적 크기 // 루트(html)글자크기를 기준으로 배수만큼 크기 지정</br>
em : 상대적 크기 // 부모글자크기를 기준으로 배수형태의 크기 지정</br>

clamp - 반응형 글자크기 조절 옵션</br>
font-size: clamp(기준값, 최소값, 최대값)</br>

font</br>
letter-spacing - 글자 사이에 간격 지정</br>
word-spacing - 단어 사이에 간격 지정</br>


텍스트 수평정렬 : text-align: center;</br>
텍스트 수직정렬 : line-height:200px; (px은 height랑 같게 지정)</br>

 @font-face { // 폰트 임포트 (style태그 안에서 설정) <br>
            font-family:"edu"; // font class 이름 설정 <br>
            src: url("./font/EduVICWANTBeginner-Bold.ttf"); // 주소 (라이브러리) <br>
            font-weight:300; (폰트 높이) <br> 
            font-style: normal;     } <br>

<hr>

<h3>overflow</h3>
overflow - 부모태그의 크기보다 자식태그가 커지면 생기는 현상

<hr>

<h3>boxsizing</h3>
* // 전체선택자
* {bow-sizing:border-box;} (테두리를 기준으로 px을 잡게된다) // 하지 않으면 border나 padding을 추가했을때 contents영역이 커져버린다

<hr>

<h3>selector</h3>		
		
전체선택자 		
- ★ {} // 모든 태그 선택 (전역변수를 많이 건들면 유지보수가 힘들어지기때문에 지양하기)		
				
요소선택자		
- div {} // 문서 내의 모든 div태그 선택		

id선택자		
- #id-1 {} // 유일한 요소 위치를 잡을때 사용		
		
class선택자		
- .group {} //특정한 요소 여러개를 쓸 때 사용				
		
group선택자(,)		
- #id-1, .group {} //여러개의 선택자를 동시 적용시킬 때 사용		
				
자식선택자 (>)				
- .par>.son>div {} // 자식 전부 선택 (자손은 선택 안됨)		
		
자손선택자 (공백)		
- .par div {} //자식을 포함한 자손 전부 선택				
		
~ : 동위선택자, 같은 형제의 하위 모든 선택자		
- c2~p {} // c2의 하위 모든태그 선택		
		
+ : 동위선택자, 같은 Depth의 하위 1개 선택자		
- c2+p {} // c2의 하위 태그 1개만 선택		













