## box-sizing

- 요소의 크기 계산 기준을 지정
- `content-box` 요소의 내용(content)으로 크기 계산
- `border-box` 요소의 내용 + padding + border 로 크기 계산
- `padding`, `border` 등 요소의 크기를 크게 하는 요소를 사용하면  
  본래의 의도보다 요소의 크기가 커질 수 있다.  
  그렇기에 `box-sizing`을 이용해 크기를 맞출 수 있다.
- `box-sizing`의 기본 값은 `content-box`이다.

## overflow

- 요소의 크기 이상으로 내용이 넘쳤을 때, 보여짐을 제어

- `visible`(default) 넘친 내용을 그대로 보여줌
- `hidden` 넘친 내용을 잘라냄
- `scroll` 넘친 내용을 잘라내고 스크롤바 생성
- `auto` 넘친 내용이 있는 경우에만 잘라내고 스크롤바 생성
- `overflow-x`, `overflow-y`의 개별 속성이 있다.

## display

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

## text

- `line-height` 문자열의 높이 지정
- `text-indent` 문자 첫 줄의 들여쓰기  
  음수 사용 가능, 반대는 내어쓰기

## background

- `background-repeat` 요소의 배경 이미지 반복
  - `repeat` 이미지를 수직 수평 반복
  - `repeat-x` 이미지를 수평 반복
  - `repeat-y` 이미지를 수직 반복
  - `no-repeat` 반복없음
- `background-position` 요소 배경 이미지 위치
  - `방향` top, bottom, left, right, center 방향
  - `단위` px, em, rem 등 단위 지정
- `background-size`
  - `auto` 이미지의 실제 크기
  - `단위` px, em ,rem..
  - `cover` 비율을 유지, 요소의 더 넓은 너비에 맞춤
  - `contain` 비율을 유지, 요소의 더 짧은 너비에 맞춤
- `background-attachment` 요소의 배경 이미지 스크롤 특성
  - `scroll` 이미지가 요소를 따라서 같이 스크롤
  - `fixed` 이미지가 뷰포트에 고정, 스크롤 x
  - `local` 요소 내 스크롤 시 이미지가 같이 스크롤

## position

- `position` 요소의 위치 지정 기준
  - `static` 기준 없음
  - `relative` 요소 자신을 기준
  - `absolute` 위치상 부모 요소를 기준
  - `fixed` 뷰포트(브라우저) 를 기준
  - `sticky` 스크롤 영역 기준
- `top, bottom, left, right, z-index` position과 같이 사용하는 속성들  
  모두 음수를 사용 가능

  - `auto` 브라우저가 계산
  - 단위 - px, em, rem ...

- ### Stack order (요소 쌓임 순서)
  - 어떤 요소가 사용자와 더 가깝게 있는지(위에 쌓이는지) 결정

1. 요소에 position 속성의 값이 있는 경우 위에 쌓임.(기본값 static 제외)
2. 1번 조건이 같은 경우, `z-index` 속성의 숫자 값이 높을 수록 위에 쌓임.
3. 1번과 2번 조건까지 같은 경우, HTML의 다음 구조일 수록 위에 쌓임.

- `z-index` 요소 쌓임 정도를 지정(position이 없다면 그 다음 조건)

  - `auto` 부모 요소와 동일한 쌓임 정도 === `0`
  - `숫자` 숫자가 높을 수록 위에 쌓임

- ### 요소의 `dispaly`가 변경됨
- `position` 속성의 값으로 `absolute, fixed`가 지정된 요소는,  
  `display` 속성이 `block` 으로 변경됨.

```css
span {
  display: block;
  width: 100px;
  height: 100px;
  position: absolute;
}
```

```css
span {
  position: absolute;
  width: 100px;
  height: 100px;
}
```

- 위 두 코드는 같다.
- `in-line` 상태에서는 가로 세로 넓이를 지정해줄 수 없지만 `block` 에서는 가능,  
  `span` 태그는 대표적인 인라인 엘리먼트

## Flex(정렬)

- 1차원의 레이아웃을 그리는 개념
- `display: flex`로 지정
- Flex가 지정된 요소는 Flex Container가 된다.
- 자식 요소는 Flex items라 부른다.
- flex와 관련된 속성은 container와 items 부분이 나뉘어있다.
- `Container`에 관련된 속성들
  - `display`, `flex-flow`, `flex-direction`, `flex-wrap`,  
    `justify-content`, `align-content`, `align-items`
- `Items`에 관련된 속성들

  - `order`, `flex`, `flex-grow`, `flex-shrink`,  
    `flex-basis`, `align-self`

- ### display
- Flex Container의 화면 출력(보여짐) 특성
- `flex`: 블럭 요소와 같이 Flex Container 정의
- `inline-flex`: 인라인 요소와 같이 Flex Container 정의

- ### flex-direction
- 주 축을 설정
- `row`: 행 축(좌 => 우) 수평
- `row-reverse`: 행 축 (우 => 좌)
- `column`: 열 축(위 => 아래) 수직
- `column-reverse`: 열 축(아래 => 위)

- ### flex-wrap
- Flex items 묶음(줄 바꿈) 여부
- `nowrap`: 묶음(줄 바꿈) 없음
- `wrap`: 여러 줄로 묶음
- `wrap-reverse`: wrap의 반대 방향으로 묶음

- ### fustify-content
- 주 축의 정렬 방법
- `flex-start`: Flex items를 시작점으로 정렬
- `flex-end`: Flex items를 끝점으로 정렬
- `center`: Flex items를 가운데 정렬
- `space-between`: 각 Flex item 사이를 균등하게 정렬
- `space-around` : 각 Flex item의 외부 여백을 균등하게 정렬

- ### align-content
- 교차 축의 여러 줄 정렬 방법
- `flex-wrap`이 있어야 한다. (한 줄이 아닌 여러 줄이 있어야 적용이 된다.)
- `stretch`: Flex Items를 시작점으로 정렬
- `flex-start`: Flex Items를 시작점으로 정렬
- `flex-end`: Flex Items를 끝점으로 정렬
- `center`: Flex Items를 가운데 정렬
- `space-between`: 각 Flex Item 사이를 균등하게 정렬
- `space-around` : 각 Flex item의 외부 여백을 균등하게 정렬

- ### align-items
- 교차 축의 한 줄 정렬 방법
- `stretch`: Flex Items를 교차 축으로 늘림
- `flex-start`: Flex Items를 시작점으로 정렬
- `flex-end`: Flex Items를 끝점으로 정렬
- `center`: Flex Items를 가운데 정렬
- `baseline`: Flex Items를 각 줄의 문자 기준선에 정렬

## Flex Item

- ### order
- Flex Item의 순서
- `0`: 순서 없음
- `숫자`: 숫자가 작을 수록 먼저

- ### flex-grow
- Flex Item의 증가 너비 비율
- `0`: 증가 비율 없음
- `숫자`: 증가 비율

- ### flex-shrink
- Flex Item의 감소 너비 비율
- `1`: Flex Container 너비에 따라 감소 비율 적용
- `숫자`: 감소 비율

- ### flex-basis
- Flex Item의 공간 배분 전 기본 너비
- `auto`: 요소의 Content 너비
- `단위`: px, em, rem 등 단위로 지정

## 전환

- ### transition
- 요소의 전환(시작과 끝) 효과를 지정하는 단축속성
- `transition`: 속성명, 지속시간, 타이밍함수, 대기시간
- 지속시간은 필수 포함속성
- `transition-property`, `transition-duration`,  
  `transition-timing-function`, `transition-delay`
- ### transition-property
- 전환 효과를 사용할 속성 이름을 지정
- `all`: 모든 속성에 적용
- `속성 이름`: 전환 효과를 사용할 속성 이름 명시
- ### transition-duration
- 전환 효과의 지속시간을 지정
- `0s`: 전환 효과 없음
- `시간`; 지속시간(s)을 지정
- ### transition-timing-function
- 전환 효과의 타이밍(Easing) 함수를 지정
- `ease`: 느리게 - 빠르게 - 느리게
- `linear`: 일정하게
- `ease-in`: 느리게 - 빠르게
- `ease-out`: 빠르게 - 느리게
- `ease-in-out`: 느리게 - 빠르게 - 느리게
- `cubic-bezier(n,n,n,n)`: 자신만의 값을 정의(0~1)
- `steps(n)`: n번 분할된 애니메이션
- `[Easing Functions]("www.easings.net/ko")`
- easing functions mdn을 검색하면 여러 정보를 확인할 수 있다.
- `[tweenmax easing]("www.greensock.com/docs/Easing")`
- ### transition-delay
- 전환 효과가 몇 초 뒤에 시작할지 대기시간을 지정
- `0s`: 대기시간 없음
- `시간`: 대기시간(s)을 지정
