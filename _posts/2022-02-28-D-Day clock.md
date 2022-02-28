# D-Day Clock
디데이 계산기를 만들어보자
구하는 날짜는 크리스마스 이브로 설정했다.
HTML/CSS 부분은 크게 신경쓰지 않고 
기능구현에만 집중했다.

```html
  <body>
    <h1>Time Until Christmas Eve</h1>
    <h2 class="clock"></h2>
    <script src="clock.js"></script>
  </body>
```
HTML은 간단히 시계를 넣을 공간만 만들어줬다.

```js
const clock = document.querySelector(".clock");
```
자바스크립트에서
먼저 시계를 넣을 부분을 불러온다.

```js
const today = new Date().getTime();
const christmas = new Date(2022, 11, 25).getTime();
```
오늘 날짜는 `new Date()`를 사용하면 된다.
구하고싶은 특정 날짜가 있다면 괄호안에 넣으면 된다.
뒤에 `getTime()`를 사용하여 컴퓨터식 시간으로 바꿨다. 밀리세컨식

```js
const leftDay = (christmas - today)/1000;
//24hours, 60minutes, 60seconds, 1000milliseconds
const day = Math.floor(leftDay/(60*60*24));
const hour = Math.floor(leftDay/(60*60)) % 24;
const minute = Math.floor(leftDay/60) % 60; 
const second = Math.floor(leftDay) % 60;
```
구하고싶은 날짜에서 오늘 날짜를 뺀뒤에 1000으로 나눈다. (계산을 편리하게 하기위해 미리 밀리세컨식으로 나눔)
이제 컴퓨터시간을 우리가 알고있는 시간대로 바꾸는 작업이 필요하다.

>`second`는 초단위이기때문에 60초로 나눈 나머지 값.
>`minute`는 분단위를 구해야하므로 초단위(60)로 나눈뒤 분단위(60)으로 나눈 나머지 값
>`hour`는 24시간 단위를 사용하므로 초단위(60)로 나눈뒤 분단위(60)으로 나눈것을 24로 나눈 나머지 값
>`floor`을 사용하여 소수점을 제외한 정수만 얻도록 한 뒤 나머지를 시간대에 맞게 계산한다.

```js
const dDayText = `${day}D ${hour}h ${minute}m ${second}s`;
    
clock.innerText = dDayText;
````

숫자를 모두 구했다면 넣을 자리에 넣어주기만 하면 된다.
`innerText`를 사용해 해당 엘리먼트에 넣어준다.

```js
dDay();
setInterval(dDay, 1000);
```
만든 함수를 `dDay()`안에 담아주고 `setInterval`을 초단위로 실행시킨다.
페이지에 들어가자마자 시계가 작동하길 바라므로 함수를 한 번 선언한 뒤 `setInterval`해주면 된다.
