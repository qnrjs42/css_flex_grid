## 배치 순서 (order)

- 각 아이템들의 시각적 나열 순서를 결정


```css
.item:nth-child(1) {
    order: 1;
}
```

<br/>

---

## 수직축으로 아이템 정렬 (align-self)

- align-items: 전체 아이템 수직축 방향 정렬
- align-self: 아이템의 수직축 방향 정렬
- 기본값 auto, 기본적으로 align-items 설정 상속 받음
- align-self는 align-items보다 우선권이 있음

```css
.item:nth-child(1) {
    align-self: auto;
    align-self: stretch;
    align-self: flex-start;
    align-self: flex-end;
    align-self: center;
    align-self: baseline;
}
```

<br/>

---

## 컨테이너 가운데 정렬, 마지막 아이템만 우측 정렬

```css
.flex-container {
    display: flex;
    width: 600px;
    margin: 0 auto;
}
.flex-item {
    width: 150px;
}
.flex-item:last-child {
    margin-left: auto;
}
```

<br/>

---

## 반응형 컬럼

```css
.flex-container {
    display: flex;
    min-height: 100vh;
    flex-direction: column;
    border: 10px solid red;
}
.flex-item {
    flex: 1 auto;
}
@media (min-width: 600px) {
    .flex-container {
        flex-direction: row;
        flex-wrap: wrap;
    }
    .flex-item {
        width: 50%;
        /* flex: 0 auto; */
        /* flex-basis: 50%; */
    }
}
@media (min-width: 900px) {
    .flex-container {
        flex-direction: row;
        flex-wrap: wrap;
    }
    .flex-item {
        width: 30%;
    }
}
```

<br />

---

## flex-grow, flex-shrink, flex-basis 한 번에 사용 (flex)

```css
.item {
    flex: 1;
    /* flex-grow: 1; flex-shrink: 1; flex-basis: 0%; */
    flex: 1 1 auto;
    /* flex-grow: 1; flex-shrink: 1; flex-basis: auto; */
    flex: 1 500px;
    /* flex-grow: 1; flex-shrink: 1; flex-basis: 500px; */
}
```

```css
.flex-container {
    display: flex;
    flex-wrap: wrap;
}
.flex-item {
    flex: 1 1 auto;
}
.flex-item:nth-child(1) {
    width: 20;
}
.flex-item:nth-child(2) {
    width: 60%;
}
.flex-item:nth-child(3) {
    width: 20%;
}
```
<br />

---

## 유연하게 줄이기 (flex-shrink)

flex-shrink는 flex-grow와 쌍을 이루는 속성, 아이템이 flex-basis의 값보다 작아질 수 있는지를 결정<br/>
0보다 큰 값이 세팅되면 해당 아이템이 유연한 박스로 변하고 flex-basis보다 작아짐<br/>
기본값이 1, 따로 세팅하지 않아도 아이템이 flex-basis보다 작아질 수 있음


```css
.item {
    flex-basis: 150px;
    flex-shrink: 1;
}
```
<br />

---

## 유연하게 늘리기 (flex-grow)

flex-grow는 아이템이 flex-basis의 값보다 커질 수 있는지 결정하는 속성<br/>
0보다 큰 값이 세팅되면 해당 아이템이 유연한 박스로 변하고 원래의 크기보다 커지며 빈공간을 메움<br/>
기본 값은 0


```css
.item {
    flex-grow: 1;
}
```
<br />

---

## 유연한 박스의 기본 영역 (flex-basis)

- flex 아이템들의 기본 크기를 설정
- flex-direction이 row일 때 너비
- flex-direction이 column일 때 높이

```css
.item {
    flex-basis: auto; /* 기본 값 */
    flex-basis: 0;
    flex-basis: 50%;
    flex-basis: 300px;
    flex-basis: 10rem;
    flex-basis: content;
}

flex-basis: 100px; 
100px이하 아이템들의 width는 100px로 늘어났고,
100px이 넘어갔던 아이템은 그대로 유지

width: 100px; 
컨텐츠 내용이 뭘 들어있던 간에 강제로 너비를 맞춤
```
<br />

---

## 여러 행 정렬 (align-content)

```css
.container {
    flex-wrap: wrap;
    align-content: stretch;
    align-content: flex-start;
    align-content: flex-end;
    align-content: center;
    align-content: space-between;
    align-content: space-around;
    align-content: space-evenly;
}

flex-wrap: wrap;가 설정된 상태이고,
아이템들의 행이 2줄 이상 되었을 때 수직축 방향 정렬

stretch: 아이템의 수직축이 쭉 늘어나면서 정렬
flex-start: 위에서 시작, 왼쪽에서 오른쪽으로 정렬
flex-end: 아래에서 시작, 왼쪽에서 오른쪽으로 정렬
center: 가운데서 시작, 왼쪽에서 오른쪽으로 정렬
space-between: 수직축에서 맨위와 맨아래로 정렬 (wrap 적용 시)
space-around: 수직축에서 각 아이템의 위아래 여백을 가지고 정렬 (wrap 적용 시)
space-evenly: 수직축에서 각 아이템의 위아래 일정한 여백을 가지고 정렬 (wrap 적용 시)
```
<br />

---

## 수직축 방향 정렬 (align-items)
<br />

```css
.container {
    align-items: stretch;
    align-items: flex-start;
    align-items: flex-end;
    align-items: center;
    align-items: baseline;
}

stretch: 아이템들이 수직축 방향으로 끝까지 쭉 늘어남
flex-start: 아이템들을 시작점으로 정렬, flex-direction이 row일 때 위치는 위, column일 때 위치는 왼쪽으로 정렬
flex-end: 아이템들을 끝으로 정렬, flex-direction이 row일 때 위치는 위, column일 때 위치는 왼쪽으로 정렬
center: 아이탬들을 가운데로 정렬
baseline: 아이템들을 텍스트 베이스라인 기준으로 정렬
```

```css
한 가운데 정렬 방법
.container {
    display: flex;
    jusityfy-contenr: center;
    align-item: center;
}

위와 같이 해주면 아이템이 정중앙에 배치된다
```

<br />

---

## 메인축 방향 정렬 (justify-content)
<br />

```css
.container {
    justify-content: flex-start;
    justify-content: flex-end;
    justify-content: center;
    justify-content: space-between;
    justify-content: space-around;
    justify-content: space-evenly;
}

flex-start: 왼쪽에 붙어서 정렬
flex-end: 오른쪽에 붙어서 정렬
center: 가운데 정렬
space-between: 양 끝과 가운데 정렬
space-around: 각 아이템의 양쪽에 여백을 두고 정렬
space-evenly: 각 아이템의 균일하게 여백을 두고 정렬(around보다 좁혀짐)
evenly의 문제점은 IE와 Edge에서 지원이 안됨
```

<br />

---

## 줄넘김과 배치 방향 동시 설정 (flex-flow)

```css
.container {
    flex-flow: row wrap;
}

row wrap: 왼쪽에서 오른쪽 정렬과 동시에 줄바꿈 처리
```
<br />

---

## 줄넘김 처리 설정 (flex-wrap)


```css
.container {
    flex-wrap: nowrap;
    flex-wrap: wrap;
    flex-wrap: wrap-revere;
}

nowrap: 컨테이너의 폭이 아이템의 합보다 작아졌을 때 아이템이 삐져나감
wrap: 컨테이너의 폭이 아이템의 합보다 작아졌을 때 아이템이 아래로 줄바꿈 처리
wrap-reverse: 컨테이너의 폭이 아이템의 합보다 작아졌을 때 아이템이 위로 줄바꿈 처리
```
<br />

---

## 배치 방항 설정 (flex-direction)

```css
.container {
    flex-direction:row;
    flex-direction:column;
    flex-direction:row-reverse;
    flex-direction:column-reverse;
}

row: 왼쪽에서 오른쪽으로 정렬
column: 위에서 아래로 정렬
row-reverse: 오른쪽에서 왼쪽으로 정렬
column-reverse: 아래에서 위로 정렬
```

<br />

---

## flex

```
.container {
    display: flex;
    display: inline-flex;
}

flex: block처럼 동작
inline-flex: 자기가 가진 내용만큼 줄어듬
```
<br />

---


```
Flex: 1차원적, 컨텐츠 중심
Grid: 2차원적, 레이아웃 중심
```
default.css는 여백같은거 없애는 리셋 css

```
부모: 컨테이너 | container
자식: 아이템   | item
```
<br/>

flex 속성은
- 컨테이너에 적용하는 속성
- 아이템에 적용하는 속성

<br/>

파이어폭스 개발자 도구에는 특별한 기능을 가짐<br />
레이아웃에 플렉스, 그리드 영역을 표시해줌<br />
공부할 때만큼은 파이어폭스 사용을 권장




