# Answer below questions.
- [x] [var 와 let의 차이점에 대해 서술하고 그 예제 코드 작성](#var-와-let의-차이점에-대해-서술하고-그-예제-코드-작성)
- [x] [반복문(Loop)의 종류와 1부터 10까지 출력하는 코드 작성](#반복문loop의-종류와-1부터-10까지-출력하는-코드-작성)
- [x] [타입 추론(Type Inference)이란?](#타입-추론type-inference이란)
- [x] [논리연산자(Boolean Logic) 인 AND(&&) 와 OR(||) 로 나올 수 있는 경우의 수 4가지](#논리연산자boolean-logic-인-and-와-or-로-나올-수-있는-경우의-수-4가지)

# Questions

## var 와 let의 차이점에 대해 서술하고 그 예제 코드 작성

### 1. 중복선언 가능 여부 
  - var은 중복선언이 가능하지만, let은 불가능하다
``` javascript
// 첫번째 변수 선언+초기화
var sample = 10;
console.log(sample); // 10


// 두번째 변수 선언+초기화
var sample = 20;
console.log(sample); // 20


// 세번째 변수 선언(초기화X)
var sample;
console.log(sample); // 20
```

```javascript
// let 중복 선언
let sample2 = 100;
let sample2 = 200; // SyntaxError: Identifier 'sample2' has already been declared
```

### 2. 재할당 가능 여부
  - var과 let은 둘 다 재할당이 가능하다.
```javascript
var sample = 10;
sample = 20;
console.log(sample);  // 20

let sample2 = 100;
sample2 = 200;
console.log(sample2);  // 200
```

### 3. 지역변수 전역변수
  - var은 함수 내에서 선언했을 때에만 지역변수이며, 그 외에는 전역변수이다.
```javascript
if(true) {
    var sample = 10;
    console.log(sample); // 10
}


console.log(sample);  // 10
```
  - let은 코드 블럭 안에서 선언되면 언제나 지역변수이다.
```javascript
if(true) {
    let sample2 = 10;
    console.log(sample2); // 10
}

console.log(sample2);  // ReferenceError: sample2 is not defined
```

### 4. 호이스팅
  - var은 선언문 이전에 변수를 참조할 수 있다.
```javascript
console.log(sample); // undefined

var sample;
console.log(sample); // undefined

sample = 1; // 할당문에서 할당 단계 실행
console.log(sample); // 1
```
  - let은 선언문 이전에 변수를 참조하면 일시적 사각지대(Temporal Dead Zone; TDZ)에 빠지므로, 오류가 발생한다.
```javascript
console.log(sample2); // ReferenceError: foo is not defined

let sample2; // 변수 선언문에서 초기화 단계 실행
console.log(sample2); // undefined

sample2 = 1; // 할당문에서 할당 단계 실행
console.log(sample2); // 1
```

## 반복문(Loop)의 종류와 1부터 10까지 출력하는 코드 작성
### 1. For
```javascript
for (let i = 1; i < 11; i++){
    console.log(i); // 0~10까지 출력
}
```
### 2. while
```javascriptvar 
j = 1;

while (j < 11) { 
    console.log(j); // 0~10까지 출력
    j++; 
}
```
### 3. for in
```javascript
const obj= {
    a: 1,
    b: 2,
    c: 3,
    d: 4,
    e: 5,
    f: 6,
    g: 7,
    h: 8,
    k: 9,
    l: 10,
}

for (let i in obj) {
    console.log(obj[i]);
}
```
### 4. for of
```javascript
let numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

for (const value of numbers) {
    console.log(value);
}
```
### 5. for each
```javascript
const numbers2 = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];

numbers2.forEach(element => console.log(element));
```
### 6. do while
```javascript
var j = 1
do {
	console.log(j);
    j++ 
} while (j < 11);
```

## 타입 추론(Type Inference)이란?
타입추론(Type Inference) 이란 타입스크립트가 코드를 해석해나가는 동작을 의미한다.

1. 특정 변수를 선언해서 값을 할당
2. 함수 파라미터의 기본값, 반환값 지정

```javascript
var a;		// any
var a = 10;	// number
```

## 논리연산자(Boolean Logic) 인 AND(&&) 와 OR(||) 로 나올 수 있는 경우의 수 4가지

### AND(&&)
```javascript
console.log( true && true );   // true
console.log( false && true );  // false
console.log( true && false );  // false
console.log( false && false ); // false
```

### OR(||)
```javascript
console.log( true || true );   // true
console.log( false || true );  // true
console.log( true || false );  // true
console.log( false || false ); // false
```

