90<h1>JS</h1>

적용법 - 
1. script 태그를 본문 가장 마지막에 배치
2. script src 태그 안에 외부 파일을 link (defer를 써주지 않으면 맨 처음에 적용되서 무용지물)

<hr>

<h3>자료형</h3>


```
Number : 숫자형
String : 문자형
Object : {Key : Value}
null : 
undifined :
boolean : 
```

<hr>

<h3>예약어</h3>

```
let : 변수 선언 예약어
const : 심볼릭 상수 선언 예약어
보간법 :
        변수,함수 호출 및 산술 표현식을 문자열에 직접 삽입할 수 있는 기능
        ${value} 형식을 사용, 백틱(``)에만 사용가능

```

<hr>

<h3>배열</h3>

```
자바스크립트 배열은 동적 확장이 가능하다 (자바는 불가능) ex) 배열을 3개로 설정해놓고 7번째에 값을 넣는다
배열 요소에는 여러 타입이 허용된다
배열 선언 - 예약어, 변수이름 = [배열] ( let arr = [1, 2, 3]; )

PUSH/POP : 마지막 Index에 있는 값을 넣거나 빼는 작업
arr.push(값), arr.pop() 

배열 안 내용 순회반복 -
OLD :
1. for (초기값; 조건식; 탈출연산식) {}
2. for (i in arr) {}
3. arr.forEach((배열요소의 하나하나값) => {console.log(item})

배열관련 함수
1. sort : 정렬 하는데 사용 // 배열안의 값을 바꿈
arr.sort() : 기본 오름차순 정렬
arr.sort((a, b) => {return b - a;}) : 내림차순 정렬

2. filter : 배열.filter((배열요소) => {조건식}) // 배열을 새로 만듬
arr.filter((item) => {return typeof item === "number";}) // 중괄호를 넣을거면 return을 넣어주지 않으면 값이 나오지 않음

3. reduce : 덧셈연산 할 때 사용 
let sumVal = sortedNum.reduce((sum,item) => {return sum = sum+item}, 0);
(sum) : 누산변수 (누적)
(item) : 요소 (하나씩 이동할때 저장되는 변수)
{} : 누산처리작업
0 = sum의 초기값
곱샘으로 하고싶으면 + 를 * 로 변경 후 0을 1으로 변경 (0이면 곱해도 0이니까)

4. 배열 object foreach - [ {}, {}, {} ].foreach() 
arr.forEach((item,) => {
  if (typeof item === "object"){ // 배열의 타입이 오브젝트이면 출력
  console.log(item);
  item.forEach((i) => {console.log(i)}); // 배열에만 foreach를 사용할 수 있음 오브젝트는 안됨.
  }
  for (key in item) { // 오브젝트에 있는 키값을 item이라는 변수에 받아와서
    console.log('key : ', key, ',value : ', item[key] ) // 키값과 벨류값 출력
  }
)

5. map + 일반배열 //새로운 배열을 만듬
let returnedArr = arr.map((item) => {return item+'%'}); // item의 length만큼 반복되며 +% 처리

6. map + 배열 object
let returnedMap = orderList.map((item) =>{
return { oid: item.oid, tel: item.tel } // item안에 있는 oid값을 그대로 받아와 다시 oid에 넣어줌
});

typeof item === "Number")?sum=sum+item: sum=sum+0
(조건식)?참이면 실행할문장 , 거짓일때 실행할 문장

7. 유사배열객체 - {}.forEach() (X)
{}로 선언
obj[0], obj.length로 확인은 할 수 있지만 foreach는 사용 불가능
Array.from(obj) // 배열로 변환해줘서 forEach 사용 가능해짐

8. split : 원하는 값을 배열에서 지움
menu = menu.split('<br />')

```

<hr>

<h3>Object객체</h3>
Object객체 : 객체를 다루는 기본함수를 제공
Object.prototype : 객체가 상속을 구현하는데 사용되는 메커니즘,Object객체 내에 구성

```
Object.prototype
자바스크립트의 모든 객체가 상속하는 프로토타입 체인의 최상위에 있는 객체
따라서 Object.prototype에는 다양한 함수들이 정의되어 있음


toString(): 객체를 문자열로 변환하여 반환
hasOwnProperty(): 객체가 특정 속성을 직접 소유하고 있는지 여부를 확인
isPrototypeOf(): 객체가 다른 객체의 프로토타입 체인에 존재하는지 여부를 확인
valueOf(): 객체의 원시 값 표현을 반환
toLocaleString(): 객체를 지역화된 문자열로 변환하여 반환
propertyIsEnumerable(): 특정 속성이 열거 가능한 속성인지 여부를 확인
constructor: 객체를 생성한 생성자 함수를 참조

Object.keys(obj) : obj 객체의 key 값을 배열로 반환
Object.values(obj) : obj 객체의 value값을 배열로 반환
Object.enntries(obj) : key, value 형태의 배열로 반환
Object.assing(obj, ob1, ob2) : obj에 ob1, ob2속성 복사
Object.freeze(obj) : 객체 수정 불가
Object.seal(obj) : 속성 추가 불가
```

<hr>

<h3>연산자</h3>

```
산술 연산자 (Arithmetic Operators):
+ (덧셈)
- (뺄셈)
* (곱셈)
 / (나눗셈)
% (나머지) : %연산 (짝수,홀수 / 배수 / 자리수 / 수의 범위 제한 가능) //조건식 만들 때 많이 씀
++ (증가) , -- (감소) : 증감연산자 // 변수안의 값을 1증가(++) or 1감소(--)에 사용되는 연산자
++a : a의 값을 1증가 한 후 다른 연산처리
a++ : 다른 연산처리 후 1증가


할당 연산자 (Assignment Operators): 공간 = 값 (먼저처리 == 저장)
= (할당)
+= (더해서 할당) num=num+5 랑 num+=5랑 똑같음 
-= (빼서 할당)
*= (곱해서 할당)
/= (나눠서 할당)
%= (나머지를 할당)

비교 연산자 (Comparison Operators):

== (동등 비교) 
=== (일치 비교) 
!= (부등 비교)
!== (불일치 비교)
> (크다)
< (작다)
>= (크거나 같다)
<= (작거나 같다)

논리 연산자 (Logical Operators):

&& (논리 AND) // 조건식의결과 참 && 조건식의결과 참 == true (둘다 참이여야 true / false면 나머지는 보지도않고 종료) 
|| (논리 OR) // 
! (논리 NOT)
비트 연산자 (Bitwise Operators):

& (비트 AND)
| (비트 OR)
^ (비트 XOR)
~ (비트 NOT)
<< (왼쪽 시프트)
>> (오른쪽 시프트)
>>> (부호 없는 오른쪽 시프트)

삼항 조건 연산자 (Ternary Operator):
condition ? expression1 : expression2
(조건식 ? 참인경우 : 거짓인경우)
타입 연산자 (typeof Operator):
typeof (피연산자의 타입을 문자열로 반환)

인스턴스 검사 연산자 (instanceof Operator):
instanceof (객체의 인스턴스 여부를 확인)
```

<hr>

<h3>흐름제어문</h3>

```
if 문 - (조건식) {종속문장}
if (num > 10) { console.log(num, "은 10보다 큽니다") }


for문 -
기본 for : for (초기값; 조건식; 탈출식)
개량 for : object 내의 값 확인할 때 사용 // for (key in value) {종속문장}
[].forEach 
```

<hr>

<h3>함수</h3>
함수 : 데이터를 받아 특정 처리를 하는 논리적 공간

```
function - 
function 변수이름 (파라미터)  {return 반환값} // 파라미터나 반환값이 있거나 없어도 됨


반환자료형의 object 처리 - 
return 반환값에 { arg1 : n1, agr2 : n2, arg3 : n3 } 식으로 오브젝트로 리턴 (값을 여러개 전달하고 싶을 때 사용)


가변인자 (...args) -
파라미터에 값이 얼마나 들어올지 모를 때 사용 (배열으로 리턴해줌)


hostiong (끌어올린다) - 코드가 실행되기 전 변수선언/함수선언이 해당 스코프의 최상단으로 끌어 올려진 것 같은 현상
(권장하지 않음 : 1. 코드 구조를 무너뜨림 2. 절차대로 처리되지 않음)
// 함수가 생성되기 이전에 호출을 하면 안 돼야 하는게 정상이지만 호출이 된다. (function)


함수 표현식 - hosting을 불가능하게 함 
불가능하게 하는법 : const f2 = function() { console.log('f2함수 호출') } // 이름 없는 함수를 만들고 나서 이름을 부여해주면 됨


클로저 -
클로저는 내부 함수가 외부 함수의 변수에 접근할 수 있는것을 의미
정보 은닉 (Information Hiding) : 클로저를 사용하여 외부에서 접근할 수 없도록 변수를 보호하고, 함수를 통해서만 접근 가능하도록 함
(함수 안에서 선언해서 초기화, 함수이름이 리턴되면 만들어진 함수의 위치정보(주소)가 반환됨)
데이터 보존 (Data Persistence) : 클로저를 사용하여 함수가 생성될 당시의 환경을 유지하면서, 데이터를 영구적으로 보존할 수 있음
비동기 처리(Asynchronous Operations) : 클로저를 사용하여 비동기적인 작업에서 결과를 유지하고, 필요할 때에 접근할 수 있도록 함


콜백함수 (Call Back) -
함수를 호출하는 시점이 바뀌어진 형태의 함수
기존방식 : 사용자(개발자)가 함수를 직접 정의 -> 정의된 함수를 호출(Call)하여 결과를 반환받는 방식 
Callback : 콜백함수에 인자로 로직이 담긴 함수를(함수주소)를 전달하여 콜백함수로부터 처리된 결과를 반환받는 방식


```

<hr>

<h4>이벤트처리</h4>

```

마우스 클릭이벤트 -
1. const d1Tg = document.getElementById('d1') // 아이디 찾기
2. d1Tg.addEventLister('click'. function () { }) // 클릭에 대한 이벤트
3. d1Tg.innerHTML=''; // html 코드 화면에 출력하기


키보드 이벤트 -
1. KEYUP - 키보드가 올라올 때 (keycode값은 무조건 대문자)
2. KEYDOWN - 키보드의 특정 키가 내려갈 때 (keycode값은 무조건 대문자)
3. KEYPRESS - 키보드를 계속 누를 때 (keycode 대소문자 구별)
4. style : 이미 만들어진 태그에는 style으로 접근해서 스타일링이 가능


체크박스 -

onchange :
1. event.target.checked (체크가 됐다면 true, 아니면 false 반환)
2. .setAttribute : 태그 안에 속성을 넣을 수 있음 ('style', 'padding:10px;')


스크롤 -

scroll 
1. window.scrollX : 문서의 수평 스크롤 위치, 뷰포트의 가장 왼쪽 부분의 가로축의 위치를 기준으로 함
2. window.scrollY : 문서의 수직 스크롤 위치, 뷰포트의 가장 위쪽 부분의 세로축의 위치를 기준으로 함
3. document.documentElement.scrollHeight : 문서 뷰포트의 전체 height값
4. document.documentElement.scrollTop : window.scrollY랑 같음

헤더상단고정 -
scroll이벤트 추가 후
if 스크롤이 50보다 작아지면 (scroll <= 50)
이외의 경우에 (else)
헤더에 클래스를 추가 (header.classList.add('fixed')
css 에 class 포지션 fixed 잡기

사이즈조정 -
resize이벤트 추가 후

1. window.addEventListener 
2. window.innerWidth :  브라우저 윈도우 두께를 제외한 실질적 가로 너비
3. window.outerWidth : 브라우저 윈도우 두께를 포함한 전체 가로 너비

if (window.innerWidth <= 400) // 만약 브라우저의 innerwidth가 400보다 작다면
ballElement.style.width="50px"
ballElement.style.height="50px" 으로 스타일 바꾸기


```

<hr>

<h3>NODE CRUD</h3>

```
id : 보통 유일한 값으로 사용
class : 그룹 단위로 사용
name : 서버로 전달 하기위해 사용

노드검색 -
1. get.ElementById : Id 한 개만 들고옴 (들어오는값이 ID밖에없어서 #생략가능)
2. get.Elements (s는 여러개기 때문에 배열으로 들고 옴)
const liEls = document.getElementsByTagName('li') : li의 모든 태그를 가져옴 //배열형태이기 때문에 스타일링 불가
Array.from(liEls).forEach(function (item) { //유사배열 형태이기 때문에 Array.from사용 해서 배열로 만들어서 처리
        item.style.fontSize="2rem";
}

3. document.getElementsByName : name 값 가져오기

4. document.queryselector : 어떤 선택자든 선택 가능 (하나만) #id, .class, input 태그 등등 // 여러개가 검색되면 가장 앞에있는 하나만 가져온다
5. document.querySelectorAll : 어떤 선택자든 선택 가능 (전부) // 배열 형태로 가져와짐 (forEach사용가능)

폼검색 -
1. document.forms (모든 폼 가져옴) // 유사배열이라 forEach사용불가
2. document.(name) // 태그의 name으로 개별 접근 가능

.setAttribute('draggable', true) // 드래그 가능해지게 함

newDiv.addEventListener('dragover', function (e) { 
       console.log('dragover!!', e.target)
       e.preventDefault(); //해주지않으면 drop이 안됨
})

```

<hr>

<h3>동기 / 비동기</h3>
동기 : 미리 약속된 규칙을 근거로 동작하는 방식 //서버에서 응답이 돌아오기 전까지 아무것도 못함 (한 페이지 전체를 요청)
비동기 : 미리 약속된 규칙대로 동작하지 않고 특정한 방식으로 동작하는 방식 // 특정 영역에서 구분적으로 요청을 함 (부분적으로 요청)

```
자바스크립트에서의 동기 : 차례차례 순서대로 코드를 읽음 (싱글 스레드 방식)
자바스크립트에서의 비동기 : 작업하기 위한 공간을 따로 만들어서 동작 (스레드 분할) ex) for문을 100번 돌리는 동안 for문에서 멈춰있는게 아니라 다른 공간으로 빼서 처리하고 바로 밑으로 내려감
// 자바스크립트는 스레드를 나누는 흉내만 냄 

setTimeout : 예약함수 (일정시간 이후 특정작업 수행 - 비동기 처리 함수) // 한번만 수행
setTimeout(function (파라미터), {처리 로직}, 시간)
clearTimeout : 예약을 취소

Interval : 취소하기 전까지 계속 반복됨
setInterval(function (파라미터) {처리로직}, 시간) // 계속 동작하게 만듬
claerInterval(id값) // setinterval함수를 ID안에 대입 후 id값으로 멈춤

Promise() : 비동기 요청 시 예외처리가 포함되어있는 객체
then() : 요청 성공 시 값 받기
catch() : 실패시 값 받기

async 로 비동기 특정 함수를 묶어서
await 로 우선순위를 지정할 수 있음 
```









