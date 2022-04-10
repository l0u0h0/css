### box-sizing

- 요소의 크기 계산 기준을 지정
- `content-box` 요소의 내용(content)으로 크기 계산
- `border-box` 요소의 내용 + padding + border 로 크기 계산
- `padding`, `border` 등 요소의 크기를 크게 하는 요소를 사용하면  
  본래의 의도보다 요소의 크기가 커질 수 있다.  
  그렇기에 `box-sizing`을 이용해 크기를 맞출 수 있다.
- `box-sizing`의 기본 값은 `content-box`이다.
