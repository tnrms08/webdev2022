# 1장. 자바스크립트 입문

```js
//변수 : 바뀔 수 있는 값
let value = 1;        //Number
let text = "hello";   //String
let good = true;      //Boolean

//상수 : 한번 선언하면 바뀌지 않는 값
const a = 1;
```

### null

- 값이 없음을 나타냄
- 우리가 없다고 고의적으로 설정

### Undefined

- 값이 설정되지 않았음을 나타냄
- 우리가 설정X

### 비교 연산자(===, !==)

- 두 값이 일치하는지, 아닌지 확인
- 타입 검사 포함

### 비교 연산자(==, !=)

- 두 값이 일치하는지, 아닌지 확인
- 타입 검사 포함X

```js
const a = 1;
const b = '1';

const equals1 = a == b;
console.log(equals1);    //결과 : true

const equals2 = a === b;
console.log(equals2);    //결과 : false
```

### 조건문(if 문)

```jsx
if (조건) {
  코드;
} else if (조건) {
	코드;
} else {
	코드;
}
```

### 조건문(switch/case 문)
```js
switch (변수) {
  case 1:
    코드;
    break;
  case 2:
    코드;
    break;
  default:
    코드;
}
```

### 함수1

```jsx
function 함수명 (파라미터){
	코드;
}

//예제
function hello(name) {
	//(')말고 (`) 사용
  console.log(**`**Hello, ${name}!**`**);
	//console.log('Hello, '+ name + '!'); 가능
}
hello('velopert');
```

### 함수2 (화살표 함수)
```jsx
const 함수명 = 파라미터 => {
	코드;
};

//예제
const add = (a, b) => {
  return a + b;
};

console.log(add(1, 2));

//위의 함수와 동일한 코드
const add = (a, b) => a + b;
```