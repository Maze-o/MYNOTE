<h1>CSS</h1>

적용법 - 1. style 태그를 만들어서 적용</br>
	2. 단일 태그(inline) 안에 style 속성을 넣어서 적용 (유지보수가 힘들어서 권장하지않음)</br>
 	3. 외부 파일으로 link</br>
  	(충돌이 일어나면 가장 나중에 있는 style을 적용)</br>
  	강제 적용 :  !important 속성 (남발 x 나중에 반응형 쓸때 모바일 적용을 위해 사용 할수도 있다)</br>
   
<hr/>

<h3>block, line 태그</h3>		
		
display: block; // 블럭형 태그로 지정</br>
display: line; // 라인형 태그로 지정</br>
		
block tag // 한 행전체를 차지하는 태그</br>
-width : o , height : o</br>
-margin : 0, padding : 0</br>
		
line tag // 한 행안에 포함되어지는 태그</br>
-width : o , height : o</br>
-margin : left, right만 o, padding :o</br>
		
inline-block tag // 한 행안에 포함되어지는 태그  (line형안에 포함되어있다)</br>
-width : o , height : o</br>
-margin : 0, padding : 0</br>
		
<hr/>

<h3>width, height</h3>
width : auto; //너비 (default값 : auto, 전체너비 사용) </br>
	width의 auto : 브라우저의 너비만큼 쓰려고 하는 성질이 있다</br>
height : auto; //높이 (default값 : auto, 최소한의 높이 사용)</br>
	height의 auto : 최소한의 높이를 가지려고 하는 성질이 있다</br>

min-width : 최소 너비 </br>
max-width : 최대 너비</br>
min-height : 최소 높이</br>
max-height : 최대 높이 height가 auto일시 의미가 없어짐 (작아질려고 하기 때문에)</br>

<hr/>

<h3>자식간의 수평 가운데 배치법</h3>
1. 부모요소에 display: flex; , justify-content: center; align-items: center;
2. 부모요소에 position: relative; 자식요소에 left, right, top, bottom 을 0으로 설정 , margin: auto;

<hr/>

<h3>margin , border, padding</h3>
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
