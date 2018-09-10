Promise
=========
## Promise란
Promise는 자바스크립트 비동기처리에 사용되는 객체이다. '비동기처리'란 '특정 코드의 실행이 완료될 때까지 기다리지 않고 다음 코드를 먼저 수행하는 자바스크립트의 특성'이다.
Promise 는 주로 서버에서 받아온 데이터를 화면에 표시할 때 사용한다.

### Promise의 3가지 상태

1. Pending(대기) : 비동기 처리 로직이 아직 완료되지 않은 상태 
```js
new Promise();
```
`new Promise()` 메서드를 호출하면 Pending상태가 된다.
2. Fulfilled(이행) : 비동기 처리가 완료되어 프로미스가 결과 값을 반환해준 상태
```js
new Promise(function (resolve, reject) {
  resolve();
});
```
콜백함수의 인자 resolve를 아래와같이 실행하면 Fullfilled 상태가 된다.
3. Rejected(실패) : 비동기 처리가 실패하거나 오류가 발생한 상태
```js
new Promise(function (resolve, reject) {
  reject();
});
```
`new Promise()` 로 프로미스 객체를 생성하면 콜백 함수 인자로 resolve와 reject를 사용할 수 있다.
여기서 reject 인자로 reject() 메서드를 실행하면 Rejected 상태가 된다.

## 자바스크립트의 변수 const, let, var 

### var, let ,const의 차이점

1.var은 function-scoped이고 let, cosnt는 block-scoped이다.
2.function-scoped인 var은 하나의 함수 내에서만 적용 범위가 유효하다.
3.blocked-scoped인 let과 const는 { }로 감싸고 있는 범위 내에서 유효하다. 

### let과 const의 차이는 무엇인가. 
const는 Primitive type인 string, number, boolean, null, undefined의 상수 선언에 사용된다.
상수이기 떄문에 한번 선언하고 다시 선언 할 경우에는 에러가 발생한다. let은 변수 선언에 사용된다.
const의 경우에 상수로 선언한 객체변수의 property까지 상수 선언이 되어서 property까지 변하지 않는것은 아니다. 
```js
const dog = {
	name: "waley",
};
dog.name = "hook";
console.log(dog);
{ name: 'minky }
```
위의 예시는 상수 선언된 객체의 property가 변할 수 있음을 보여준다

## Arrow function

Arrow function은 일반 함수 표현보다 간결하게 함수를 표현할 수 있다.
this, argumentm superm new.target은 바인딩하지 않는다.
익명 함수이기 때문에 메소드가 아닌 함수에 사용하는것이 적절하다. 또한 익명이기에
생성자로 사용할 수 없다.
---
기본 문법
```js 
(param1, param2, …, paramN) => { statements }
(param1, param2, …, paramN) => expression	
		           // => {return expresstion} 과 동일하다.
```

-매개변수가 하나일때는 괄호는 선택사항이다. 
```js
(singleParam) => { statements }
singleParam => { statements }
//둘은 같은 표현이다.
```
-매개변수가 없을때는 괄호가 들어가야한다.
```js
() => { statements }
```
## Array Methods (map, reduce, filter, slice, splice)

### map 
```js
var new_array = arr.map(function 
callback(currentValue[, index[, array]]) { // new_array
의 새 요소 반환 }[, thisArg])
```
-map은 callback 함수의 각각의 요소에 대해 한번씩 순서대로 불러 그 함수의 
반환값으로 새로운 배열을 만든다. callback 함수는 배열 값이 들어있는 인덱스에 대해서만 호출된다.

-callback 함수는 호출될 때 대상 요소의 값 그 요소의 인덱스 그리고 map을 호출한
원본 배열 3개의 인수를 전달받는다.

-thisArg 매개변수가 map에 전달된 경우 callback 함수의 this 값으로 사용된다.

### reduce 

reduce 메서드의 구문
```js
array1.reduce(callbackfn[, initialValue])
```
-array1 = Array 객체이다.
-callbackfn = 최대 4개까지 인수를 허용하는 함수이다. reduce 메서드는 배열에 있는 각 요소마다 한번씩 callback 함수를 호출한다.
-intialValue = 선택사항으로 initialValue가 지정된 경우 누적을 시작하는 초기 값으로 사용된다.  callbackfn함수에 대한 첫 번째 호출은 이 값을 배열 값 대신 인수로 제공한다. 
-이 구문에 대한 반환값은 콜백함수에 대한 마지막 호출로부터 누적된 결과이다.

### filter 
filter 메서드는 map 과 마찬가지로 첫 번째 인자로 
콜백 함수(콜백 함수의 첫 번째 인자는 순회하는 배열의 값(value), 두 번째 인자는 그 값의 인덱스(index), 세 번째 인자는 배열 자체(array)이다)를 받는데 이 콜백함수의 return 값은 Boolean, 즉 true 혹은 false 가 되어야 한다. 그리고 그 return 값이 true 일 경우, 그 배열의 값은 최종적으로 return 되는 배열에 포함되고 false 일 경우에는 제외된다.

예시
```js
const data = [1, 2, 3, 4, 5]

const oddNumber = data.filter(val => { return val % 2 != 0 });

console.log(oddNumber); // [1, 3, 5]

console.log(data); // [1, 2, 3, 4, 5]
```
-filter
  -메서드의 인자로 전달된 함수는 조건자함수이다. 또한 filter는 메서드를 호출한 원래 배열을 변화시키지 않는다.

-slice
  -배열을 전체 혹은 부분 복제(clone)할 때 사용한다.
  -시작 index(포함) 와 끝 index(비포함) 인자를 두개 받는다.

```js
var items = [1, 2, 3, 4, 5];
var copy = items.slice();
copy[0] = 100;
console.log(items); // [1, 2, 3, 4, 5]
console.log(copy); // [100, 2, 3, 4, 5]
var copy2 = items.slice(2, 3); // [3]
var copy3 = items.slice(2); // [3, 4, 5]
var copy4 = items.slice(-2); // [4, 5]
var copy5 = items.slice(1, -1); // [2, 3, 4]
``` 

-splice
기본 구문
```js
array.splice(start, deleteCount[, item1[, item2[, ...]]])
```

-기존 요소를 제거하거나 새 요소를 추가하여 배열의 내용을 변경한다.
-start: 배열의 변경을 시작하는 인덱스
-deleteCount: 배열에서 제거를 할 요소의 수
-itemN: 배열에 추가될 요소, 리턴 값: 삭제된 요소들의 배열이 리턴

## Spread Operator (전개연산자)
-Iterable Object를 하나씩 전개한다.
-`[...iterable_object]`
-iterable object 앞에 ...를 붙여서 선언한다.

예시
```js
let one = [1, 2]; let two = [3, 4]; let spread = [0 , ...one, 5, ...two ]; console.log(spread); // [ 0, 1, 2, 5, 3, 4 ]
```

## Export와 Import

-export
  -export는 파일이나 모듈안의 함수나, 객체를 export 하는데 사용된다. ES6에서 정의된 API로, 브라우저에서 기본으로 제공되지 않기 때문에 Traceurur Complier, Babel, Rollup, Webpack과 같은 별로의 트랜스파일러와 함께 사용되어야 한다.

-import
  -외부 스크립트 또는 외부 모듈의 export된 함수, 객체를 가져오는데 사용된다. export와 마찬가지로, ES6에서 정의된 API 이다. import는 모든 브라우저에서 기본으로 제공되지 있지 않기 때문에 Traceur Compiler, Babel, Rollup, Webpack과 같은 별도의 트랜스파일러와 함께 사용되어야 한다.