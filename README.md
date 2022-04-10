### box-sizing

- 요소의 크기 계산 기준을 지정
- `content-box` 요소의 내용(content)으로 크기 계산
- `border-box` 요소의 내용 + padding + border 로 크기 계산
- `padding`, `border` 등 요소의 크기를 크게 하는 요소를 사용하면  
  본래의 의도보다 요소의 크기가 커질 수 있다.  
  그렇기에 `box-sizing`을 이용해 크기를 맞출 수 있다.
- `box-sizing`의 기본 값은 `content-box`이다.

### overflow

- 요소의 크기 이상으로 내용이 넘쳤을 때, 보여짐을 제어

- `visible`(default) 넘친 내용을 그대로 보여줌
- `hidden` 넘친 내용을 잘라냄
- `scroll` 넘친 내용을 잘라내고 스크롤바 생성
- `auto` 넘친 내용이 있는 경우에만 잘라내고 스크롤바 생성
- `overflow-x`, `overflow-y`의 개별 속성이 있다.
