# JS / Variable(변수)



## 변수의 종류(var, const, let)

자바스크립트에서의 변수는 아래와 같이 정의할 수 있다.
```js
var a;
```
위는 `a`라는 변수를 선언한 상태.(값은 주지 않은 상태)
변수를 선언하고 아무 값도 할당하지 않으면 기본적으로 `undefined`라는 초기값을 가진다.
- unll - 변수에만 할당할 수 있는 값이며 비어있음을 뜻한다. '비어있음'이라는 값이 들어있는 상태.
- undefined - 변수에 값을 주지 않은 상태.


```js
const a;
let b;
```
`const`는 변하지 않는 값을 할당할 때 사용한다.
반면 `let`은 변할 수 있는 값을 할당 한다.

> 변수 var 을 잘 사용하지 않는 이유는 매개변수가 const인지 let인지 알기위해서다.



## 변수에 값 할당하기
일반적으로 변수를 선언하고 나면 변수 안에 원하는 값을 할당할 수 있다.
```js
const a = 5;
console.log(a); // a = 5

const a = 8;
console.log(a); // Error
```
위 코드는 `const`라는 변수안에 `5`라는 숫자를 할당했다.
두번째 코드에서는 `cosnt`는 변하지 않는 값을 지니므로 위에서 이미 값을 할당했기 때문에 다시 다른 값을 할당해도 값이 변하지 않는 모습이며 이는 에러값을 갖는다.

```js
let a = 5;
console.log(a); //5

a = 10;
console.log(a); //10

a = "hello";
console.log(a); // "hello"
```
반면에 `let`변수는 선언한 뒤에도 값을 바꿀 수 있다.


## 변수의 타입 확인하기 - typeof
코딩을 하다보면 변수의 값이 문자열인지, 숫자인지 구분하기 어려울 때가 있다.
```js
const hi = "100"
console.log(typeof hi); // string
```
`typeof`는 뒤에오는 값의 데이터타입이 무엇인지 알려준다.

>데이터 타입을 숫자로만 받고싶다면 `parseInt`를 사용한다.

```js
const age = parseInt(prompt());
// prompt에 10을 입력받으면
// "10" 이라는 값을 받을 것이고
// parseInt로 인해 숫자타입으로 형변환되어 배출된다.
// const age = 10
```
스트링값을 넣게되면 NaN이라는 값을 받게된다.
(Not a Number)
