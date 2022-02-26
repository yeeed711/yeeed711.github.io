# String(문자열)

문자열은 변수의 여러 타입 중 하나.
일반적으로 스트링이라고 부르며 아래와 같이 선언한다.
```js
const a = "hello";
```
위 코드는 `a`라는 변수에 `hello`라는 문자열을 할당했다.
문자열은 작은 따옴표(') 또는 큰 따옴표(")를 사용하여 정의한다.


## 숫자와 문자열의 구분
```js
const a = 10;
const b = "10";
console.log(a); //10
console.log(b); //10
```
위 코드에서 변수 `a`는 숫자타입, 변수 `b`는 스트링타입이다.
하지만 콘솔로그를 사용하여 출력해보면 육안으로는 구분이 어려울 수 있다.

이전에 `typeof`를 사용하여 변수의 타입을 확인할 수도 있지만 `length`라는 자바스크립트에서 제공하는 내장함수로도 확인할 수 있다.
```js
console.log(a.length); // undefined
console.log(b.length); // 2
```
내장함수를 이용하여 확인 가능하며, 이러한 기능들을 자바스크립트 내장 함수(JavaScript Built-in API / JavaScript Native API)라고 한다.
