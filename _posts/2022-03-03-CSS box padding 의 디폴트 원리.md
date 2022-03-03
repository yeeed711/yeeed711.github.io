# CSS box padding 의 디폴트 원리

- css박스 모델의 기본값에서, 지정한 너비와 높이는 요소의 콘텐츠 박스 크기에만 적용된다.
- 요소의 테두리나 안쪽 여백이 있다면 width값과 height값을 고려해서 지정해줘야한다.


`box-sizing`속성을 사용하면 이 방식을 바꿀 수 있게 된다.

> - `content-box` -
> css박스 모델의 초기 기본값을 따른다. `width`와`heught`속성이 콘텐츠 영역만 포함하고 안쪽여백과 바깥쪽 여백, 테두리는 포함하지 않는다.
>```css
>.box {
>  width: 350px;
>  border: 10px solid black;
>}
>```
>요소의 크기는 `width`값을 고정으로하고 나머지 `border`값을 추가해 최종적으로 370px을 갖게된다.

> - `border-box` -
> 다음 예제는 두 개의 동일한 크기를 가진 박스모델이 서로다른 `box-sizing`값으로 어떻게 달라지는지 확인해볼 수 있다.
> ```html
> <div class="content-box">content-box</div>
><br />
><div class="border-box">border-box</div>
>```
>```css
>.div {
>  width: 100px;
>  height: 50px;
>  border: 5px solid yellow;
>}
>
>.content-box {
>  box-sizing: content-box;
>}
>  /* Total width: 100px + (2 * 5px) = 110px
>     Total height: 50px + (2 * 5px) = 60px */
>.border-box {
>  box-sizing: border-box;
>}
>  /* Total width: 100px - (2 * 5px) = 90px
>     Total height: 50px - (2 * 5px) = 40px */
>```

