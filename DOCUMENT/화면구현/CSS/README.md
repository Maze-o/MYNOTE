<h1>CSS</h1>

적용법 - 1. style 태그를 만들어서 적용</br>
	2. 단일 태그(inline) 안에 style 속성을 넣어서 적용 (유지보수가 힘들어서 권장하지않음)</br>
 	3. 외부 파일으로 link</br>
  	(충돌이 일어나면 가장 나중에 있는 style을 적용)</br>
  	강제 적용 :  !important 속성 (남발 x 나중에 반응형 쓸때 모바일 적용을 위해 사용 할수도 있다)</br>
   
<hr/>

<h3>block, line 태그</h3>		

```
display: block; // 블럭형 태그로 지정
display: line; // 라인형 태그로 지정
		
block tag // 한 행전체를 차지하는 태그
-width : o , height : o
-margin : 0, padding : 0
		
line tag // 한 행안에 포함되어지는 태그
-width : o , height : o
-margin : left, right만 o, padding :o</br>
		
inline-block tag // 한 행안에 포함되어지는 태그  (line형안에 포함되어있다)</br>
-width : o , height : o</br>
-margin : 0, padding : 0</br>
```
  
<hr/>

<h3>width, height</h3>

```
width : auto; //너비 (default값 : auto, 전체너비 사용) </br>
	width의 auto : 브라우저의 너비만큼 쓰려고 하는 성질이 있다</br>
height : auto; //높이 (default값 : auto, 최소한의 높이 사용)</br>
	height의 auto : 최소한의 높이를 가지려고 하는 성질이 있다</br>

min-width : 최소 너비 </br>
max-width : 최대 너비</br>
min-height : 최소 높이</br>
max-height : 최대 높이 height가 auto일시 의미가 없어짐 (작아질려고 하기 때문에)</br>
```

<hr/>

<h3>자식간의 수평 가운데 배치법</h3>

```
1. 부모요소에 display: flex; , justify-content: center; align-items: center;
2. 부모요소에 position: relative; 자식요소에 left, right, top, bottom 을 0으로 설정 , margin: auto;
```

<hr/>

<h3>margin , border, padding</h3>

```
margin = 요소간의 간격을 지정

margin: 20px 40px // 20px : top bottom // 40px : left,right으로 적용		
margin: 10px 20px 30px // 10px : top // 20px : right left // 30px : bottom 으로 적용	
margin: 10px 20px 30px 40px; // 시계방향으로 적용		

border = 내용 사이의 간격을 지정할때 사용
border: 1px 옵션들 : 
	1. solid : 테두리 생성
	2. dashed : 대시선
 	3. dotted : 점선
  	4. double : 선두개
   	
border-radius: 15px (테두리 깎기)
border-radius: 15px 35px 50px 100px; (시계방향으로 깎음)

padding = 테두리와 border 사이의 간격
```

<hr/>

<h3>단위</h3>

```
px : 고정크기
% : 가변크기 // 상위태그를 기준으로 %만큼 크기 지정
vw, vh : 가변크기 // viewport(브라우저에 표시되는 영역)를 기준으로 백분율만큼 크기지정
rem : 상대적 크기 // 루트(html)글자크기를 기준으로 배수만큼 크기 지정
em : 상대적 크기 // 부모글자크기를 기준으로 배수형태의 크기 지정

clamp - 반응형 글자크기 조절 옵션
font-size: clamp(기준값, 최소값, 최대값)

font
letter-spacing - 글자 사이에 간격 지정
word-spacing - 단어 사이에 간격 지정


텍스트 수평정렬 : text-align: center;
텍스트 수직정렬 : line-height:200px; (px은 height랑 같게 지정)

 @font-face { // 폰트 임포트 (style태그 안에서 설정)
            font-family:"edu"; // font class 이름 설정 
            src: url("./font/EduVICWANTBeginner-Bold.ttf"); // 주소 (라이브러리)
            font-weight:300; (폰트 높이)
            font-style: normal;     }

```

<hr>



<h3>overflow</h3>

```
overflow - 부모태그의 크기보다 자식태그가 커지면 생기는 현상
```

<hr>

<h3>boxsizing</h3>

```
* // 전체선택자
* {bow-sizing:border-box;} (테두리를 기준으로 px을 잡게된다) // 하지 않으면 border나 padding을 추가했을때 contents영역이 
커져버린다
```



<hr>

<h3>selector</h3>		

```
전체선택자 		
- * {} // 모든 태그 선택 (전역변수를 많이 건들면 유지보수가 힘들어지기때문에 지양하기)		
				
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

특성선택자 [] 
- input [type='checkbox'] {} // 주어진 특성의 존재 여부나 그 값에 따라 요소를 선택
		
~ : 동위선택자, 같은 형제의 하위 모든 선택자		
- c2~p {} // c2의 하위 모든태그 선택		
		
+ : 동위선택자, 같은 Depth의 하위 1개 선택자		
- c2+p {} // c2의 하위 태그 1개만 선택

의사선택자 (:)
- a:hover{} // 마우스를 올렸을때 발생
- a:active{} // 마우스를 클릭했을 때 발생

가상선택자 
- ::before // contents 영역 앞부분에 표시할 스타일
- ::after // contents 영역 뒷부분에 표시할 스타일
- before after는 라인형태그이기때문에 width height가 적용되지 않는다 (display:block;적용하면 가능)

요소선택자
- :first-child // 첫번째요소
- :last-child // 마지막요소
- :nth-child(n) //n번째 요소

checkbox
- label for="chk" // input type checkbox id="chk" 의 아이디와 동일하게 넣으면 글자를 클릭해도 체크가 됨
- input [type='check'box] {}

checkbox에서는 background-color, image 적용이 되지 않는다

```

<hr/>

<h3>POSITION</h3>

```
Positon 
-box의 위치를 지정할때 사용하는 속성
		
static (D) 
-box요소가 문서 흐름에 따라 배치(순차적)			 	
			
relative 	
-box요소가 문서 흐름에 따라 배치(순차적), 상위 box요소를 기준으로 위치 지정가능
-기본위치(static)를 기준으로 top,left,right,bottom 설정
		
absolute 		
-상위 box요소를 기준으로 위치 지정가능		
-상위 box요소가 position 설정이 되어 있어야 기준으로 지정됨	
-상위 box요소가 position 설정이 되어 있지 않다면 viewport를 기준으로 위치 조정 가능
-absolut지정하는 순간 상위에대한 flex가 없어져버림

fixed 		
-viewport를 기준으로 위치조정 가능, scroll event와 무관하게 고정위치 선점		
		
sticky 		
-스크롤 영역을 기준으로 배치, 스크롤 위치를 따라가다가 일정위치를 넘어서면 고정

z-index
- z축을 임의로 설정 (다른 요소와 겹치면 기준요소를 보이게 만듬)
- static상태에서는 적용이 되지 않는다. 포지셔닝을 해야함
```

<hr/>

<h3>RAYOUT</h3>

```
flex

수평배치형태
- justify-content: center, right, left, apace-between, space-evenly, space-around

수직배치형태 (컨텐츠의 크기만큼만 부여 (height를 지정해줘야함))
- align-items: center, end, start, stretch, baseline // 상위태그에서 사용

- align-self: stretch, flex-end, flex-start //자식태그에서 사용
flex-grow: //브라우저의 크키에 맞게 비율을 지정
flex-shrink: // 줄어드는 비율 
flex-basis: // 기본크기지정 (shrink를 0으로 잡았을 때 지정해줌)
flex: 1 1 2 // 첫번째는 grow, 두번째는 shrink, 세번째는 basis가 됨


flex방향
- flex-direciton: row(기본값), row-reverse, column, column-reverse

flex-wrap: (display flex가 적용된 부모의 width보다 자식의 width가 더 클 경우 줄바꿈을 할지말지 여부)
- flex-wrap: wrap(width적용), nowrap(기본값) 
```

<hr/>

<h3>animation</h3>

```
transition: // 크기,위치 변화가 있을 때 지연값 설정 (div:hover {width:800px;} 후 사용)
- focus옵션에 넣으면 클릭했을 때만 설정, 요소 자체에 넣으면 클릭, 클릭해제 둘다 발생

input[type='text']:focus{} // 인풋 area를 클릭했을때의 설정
outline:none; // 인풋박스가 표시되지않음
background:linear-gradient(방향, 컬러) // 포커스되었을때 설정한 방향으로 설정한 컬러가 생김 (transition을 따른다)

transform: translate(x축, y축) // 으로 위치 이동
           scale(x축, y축) // 만큼 배수로 크기 조정
	   rotate(270deg) // 270도 회전
	   skew(20deg) // 각도만큼 왜곡시키기
	   
```









