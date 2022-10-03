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

### 객체

```jsx
const 객체명 {
	키: 원하는 값
};

//Ex
const dog = {
	name: "멍멍이",
	age: 2,
	sound: '멍멍!',
	//객체 안에 함수 넣기
	//*화살표 함수(say()=>{})를 선언하면 제대로 작동하지 않는다.*
	say: function say() {
    console.log(this.sound);
  }
};
```

- 키에 해당하는 값에는 공백이 있으면 안된다.
⇒ 공백이 있는 경우 따옴표로 감싼다. Ex) ‘key with space’: true
```jsx
//객체의 정보를 배열 형태로 받아올 수 있는 함수
console.log(Object.entries(dog));    //[[name: "멍멍이"],[age: 2],[sound: "멍멍"]]
console.log(Object.keys(dog));       //[name, age, sound]
console.log(Object.values(dog));     //["멍멍이", 2, "멍멍"]
```


### Getter함수

특정 값을 조회 할 때 우리가 설정한 함수로 연산된 값을 반환한다.

```jsx
const numbers = {
  a: 1,
  b: 2,

  get sum() {
    console.log('sum 함수가 실행됩니다!');
    return this.a + this.b;
  }
};

//numbers.sum 이 조회 될 때마다 덧셈이 이루어짐
console.log(numbers.sum);    //3(1+2)
numbers.b = 5;
console.log(numbers.sum);    //6(1+5)
```

### Setter 함수

특정 값을 바꾸려고 할 때 우리가 설정한 함수로 연산된 값을 반환한다.

```jsx
const numbers = {
  _a: 1,
  _b: 2,
  sum: 3,
  calculate() {
    console.log('calculate');
    this.sum = this._a + this._b;
  },

  get a() {
    return this._a;
  },
  get b() {
    return this._b;
  },
	//a 혹은 b 값이 바뀔 때마다 sum 값을 연산함
  set a(value) {
    console.log('a가 바뀝니다.');
    this._a = value;
    this.calculate();
  },
  set b(value) {
    console.log('b가 바뀝니다.');
    this._b = value;
    this.calculate();
  }
};

console.log(numbers.sum);    //a=1, b=2, sum=3
numbers.a = 5;    //a가 바뀝니다. -> calculate
numbers.b = 7;    //b가 바뀝니다. -> calculate
numbers.a = 9;    //a가 바뀝니다. -> calculate
console.log(numbers.sum);    //16(9+7)
console.log(numbers.sum);    //16(9+7)
console.log(numbers.sum);    //16(9+7)
```

### 배열

```jsx
//배열 선언(숫자 배열)
const array = [1,2,3,4,5];

//배열 선언(객체 배열)
const objects = [{ name: '멍멍이' }, { name: '야옹이' }];

//배열 값 출력
console.log(objects);    //name: "멍멍이"    name: "야옹이"
console.log(objects[0]); //name: "멍멍이"
console.log(objects[1]); //name: "야옹이"
```

- 배열에 새 항목 추가(push)
    
    ```jsx
    object.push({
    	name: '멍뭉이'
    });
    
    console.log(objects);  //[[name: "멍멍이"], [name: "야옹이"], [name: "멍뭉이"]]
    ```
    
- 배열의 크기 알아내기(length)
    
    ```jsx
    console.log(objects.length);    //3
    ```
    

### 반복문(for)

```jsx
for (초기 구문; 조건 구문; 변화 구문;) {
  코드
}

//Ex. 0부터 9까지 출
for (let i = 0; i < 10; i++) {
  console.log(i);
}
```

### 반복문(while)

특정 조건이 참이라면 계속해서 반복하는 반복문

```jsx
let i = 0;
while (i < 10) {
  console.log(i);
  i++;
}
```

<aside>
while 문을 사용 할 때에는 조건문이 언젠간 false 가 되도록 신경써야한다.
만약에 언젠간 false 로 전환이 되지 않는다면 반복문이 끝나지 않고 영원히 반복된다.

</aside>

### 반복문(for…of) → 많이 사용X

배열에 관한 반복문을 돌리기 위해 만들어진 반복

```jsx
let numbers = [10, 20, 30, 40, 50];
for (let number of numbers) {
  console.log(number);    //10 20 30 40 50
}
```