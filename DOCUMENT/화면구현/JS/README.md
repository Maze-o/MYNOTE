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

7. 유사배열객체 - {}.forEach() (X)
{}로 선언
obj[0], obj.length로 확인은 할 수 있지만 foreach는 사용 불가능
Array.from(obj) // 배열로 변환해줘서 forEach 사용 가능해짐

8. split : 원하는 값을 배열에서 지움
menu = menu.split('<br />')

```
















