<h1>JS</h1>

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

타입 연산자 (typeof Operator):
typeof (피연산자의 타입을 문자열로 반환)

인스턴스 검사 연산자 (instanceof Operator):
instanceof (객체의 인스턴스 여부를 확인)
```
















