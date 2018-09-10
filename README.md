Promise
=========
##Promise��
Promise�� �ڹٽ�ũ��Ʈ �񵿱�ó���� ���Ǵ� ��ü�̴�. '�񵿱�ó��'�� 'Ư�� �ڵ��� ������ �Ϸ�� ������ ��ٸ��� �ʰ� ���� �ڵ带 ���� �����ϴ� �ڹٽ�ũ��Ʈ�� Ư��'�̴�.
Promise �� �ַ� �������� �޾ƿ� �����͸� ȭ�鿡 ǥ���� �� ����Ѵ�.

###Promise�� 3���� ����

1. Pending(���) : �񵿱� ó�� ������ ���� �Ϸ���� ���� ���� 
```js
new Promise();
```
`new Promise()` �޼��带 ȣ���ϸ� Pending���°� �ȴ�.
2. Fulfilled(����) : �񵿱� ó���� �Ϸ�Ǿ� ���ι̽��� ��� ���� ��ȯ���� ����
```js
new Promise(function (resolve, reject) {
  resolve();
});
```
�ݹ��Լ��� ���� resolve�� �Ʒ��Ͱ��� �����ϸ� Fullfilled ���°� �ȴ�.
3. Rejected(����) : �񵿱� ó���� �����ϰų� ������ �߻��� ����
```js
new Promise(function (resolve, reject) {
  reject();
});
```
`new Promise()` �� ���ι̽� ��ü�� �����ϸ� �ݹ� �Լ� ���ڷ� resolve�� reject�� ����� �� �ִ�.
���⼭ reject ���ڷ� reject() �޼��带 �����ϸ� Rejected ���°� �ȴ�.

##�ڹٽ�ũ��Ʈ�� ���� const, let, var 

###var, let ,const�� ������

1.var�� function-scoped�̰� let, cosnt�� block-scoped�̴�.
2.function-scoped�� var�� �ϳ��� �Լ� �������� ���� ������ ��ȿ�ϴ�.
3.blocked-scoped�� let�� const�� { }�� ���ΰ� �ִ� ���� ������ ��ȿ�ϴ�. 

###let�� const�� ���̴� �����ΰ�. 
const�� Primitive type�� string, number, boolean, null, undefined�� ��� ���� ���ȴ�.
����̱� ������ �ѹ� �����ϰ� �ٽ� ���� �� ��쿡�� ������ �߻��Ѵ�. let�� ���� ���� ���ȴ�.
const�� ��쿡 ����� ������ ��ü������ property���� ��� ������ �Ǿ property���� ������ �ʴ°��� �ƴϴ�. 
```js
const dog = {
	name: "waley",
};
dog.name = "hook";
console.log(dog);
{ name: 'minky }
```
���� ���ô� ��� ����� ��ü�� property�� ���� �� ������ �����ش�

## Arrow function

Arrow function�� �Ϲ� �Լ� ǥ������ �����ϰ� �Լ��� ǥ���� �� �ִ�.
this, argumentm superm new.target�� ���ε����� �ʴ´�.
�͸� �Լ��̱� ������ �޼ҵ尡 �ƴ� �Լ��� ����ϴ°��� �����ϴ�. ���� �͸��̱⿡
�����ڷ� ����� �� ����.
---
�⺻ ����
```js 
(param1, param2, ��, paramN) => { statements }
(param1, param2, ��, paramN) => expression	
		           // => {return expresstion} �� �����ϴ�.
```

-�Ű������� �ϳ��϶��� ��ȣ�� ���û����̴�. 
```js
(singleParam) => { statements }
singleParam => { statements }
//���� ���� ǥ���̴�.
```
-�Ű������� �������� ��ȣ�� �����Ѵ�.
```js
() => { statements }
```
##Array Methods (map, reduce, filter, slice, splice)

### map 
```js
var new_array = arr.map(function 
callback(currentValue[, index[, array]]) { // new_array
�� �� ��� ��ȯ }[, thisArg])
```
-map�� callback �Լ��� ������ ��ҿ� ���� �ѹ��� ������� �ҷ� �� �Լ��� 
��ȯ������ ���ο� �迭�� �����. callback �Լ��� �迭 ���� ����ִ� �ε����� ���ؼ��� ȣ��ȴ�.

-callback �Լ��� ȣ��� �� ��� ����� �� �� ����� �ε��� �׸��� map�� ȣ����
���� �迭 3���� �μ��� ���޹޴´�.

-thisArg �Ű������� map�� ���޵� ��� callback �Լ��� this ������ ���ȴ�.

###reduce 

reduce �޼����� ����
```js
array1.reduce(callbackfn[, initialValue])
```
-array1 = Array ��ü�̴�.
-callbackfn = �ִ� 4������ �μ��� ����ϴ� �Լ��̴�. reduce �޼���� �迭�� �ִ� �� ��Ҹ��� �ѹ��� callback �Լ��� ȣ���Ѵ�.
-intialValue = ���û������� initialValue�� ������ ��� ������ �����ϴ� �ʱ� ������ ���ȴ�.  callbackfn�Լ��� ���� ù ��° ȣ���� �� ���� �迭 �� ��� �μ��� �����Ѵ�. 
-�� ������ ���� ��ȯ���� �ݹ��Լ��� ���� ������ ȣ��κ��� ������ ����̴�.

###filter 
filter �޼���� map �� ���������� ù ��° ���ڷ� 
�ݹ� �Լ�(�ݹ� �Լ��� ù ��° ���ڴ� ��ȸ�ϴ� �迭�� ��(value), �� ��° ���ڴ� �� ���� �ε���(index), �� ��° ���ڴ� �迭 ��ü(array)�̴�)�� �޴µ� �� �ݹ��Լ��� return ���� Boolean, �� true Ȥ�� false �� �Ǿ�� �Ѵ�. �׸��� �� return ���� true �� ���, �� �迭�� ���� ���������� return �Ǵ� �迭�� ���Եǰ� false �� ��쿡�� ���ܵȴ�.

����
```js
const data = [1, 2, 3, 4, 5]

const oddNumber = data.filter(val => { return val % 2 != 0 });

console.log(oddNumber); // [1, 3, 5]

console.log(data); // [1, 2, 3, 4, 5]
```
-filter
  -�޼����� ���ڷ� ���޵� �Լ��� �������Լ��̴�. ���� filter�� �޼��带 ȣ���� ���� �迭�� ��ȭ��Ű�� �ʴ´�.

-slice
  -�迭�� ��ü Ȥ�� �κ� ����(clone)�� �� ����Ѵ�.
  -���� index(����) �� �� index(������) ���ڸ� �ΰ� �޴´�.

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
�⺻ ����
```js
array.splice(start, deleteCount[, item1[, item2[, ...]]])
```

-���� ��Ҹ� �����ϰų� �� ��Ҹ� �߰��Ͽ� �迭�� ������ �����Ѵ�.
-start: �迭�� ������ �����ϴ� �ε���
-deleteCount: �迭���� ���Ÿ� �� ����� ��
-itemN: �迭�� �߰��� ���, ���� ��: ������ ��ҵ��� �迭�� ����

##Spread Operator (����������)
-Iterable Object�� �ϳ��� �����Ѵ�.
-`[...iterable_object]`
-iterable object �տ� ...�� �ٿ��� �����Ѵ�.

����
```js
let one = [1, 2]; let two = [3, 4]; let spread = [0 , ...one, 5, ...two ]; console.log(spread); // [ 0, 1, 2, 5, 3, 4 ]
```

## Export�� Import

-export
  -export�� �����̳� ������ �Լ���, ��ü�� export �ϴµ� ���ȴ�. ES6���� ���ǵ� API��, ���������� �⺻���� �������� �ʱ� ������ Traceurur Complier, Babel, Rollup, Webpack�� ���� ������ Ʈ�������Ϸ��� �Բ� ���Ǿ�� �Ѵ�.

-import
  -�ܺ� ��ũ��Ʈ �Ǵ� �ܺ� ����� export�� �Լ�, ��ü�� �������µ� ���ȴ�. export�� ����������, ES6���� ���ǵ� API �̴�. import�� ��� ���������� �⺻���� �������� ���� �ʱ� ������ Traceur Compiler, Babel, Rollup, Webpack�� ���� ������ Ʈ�������Ϸ��� �Բ� ���Ǿ�� �Ѵ�.