
## 줄넘김과 배치 방향 동시 설정 (flex-flow)

```css
.container {
    flex-flow: row wrap;
}

row wrap: 왼쪽에서 오른쪽 정렬과 동시에 줄바꿈 처리
```

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




