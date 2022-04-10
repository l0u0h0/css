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

### display

- 요소의 화면 출력(보여짐) 특성
- `각 요소에 이미 지정되어 있는 값`
- `block` 상자(레이아웃) 요소, (`div`)
- `inline` 글자 요소, (`span`)
- `inline-block` 글자 + 상자 요소, (``)
- `따로 지정해서 사용하는 값`
- `flex` 플렉스 박스(1차원 레이아웃)
- `grid` 그리드(2차원 레이아웃)
- `none` 보여짐 특성 없음, 화면에서 사라짐
- `기타` table, table-row, table-cell ...

- `inline` 요소는 가로와 세로 넓이를 지정할 수 없다.
