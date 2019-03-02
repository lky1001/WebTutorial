## 5 display 속성

`display` 속성은 레이아웃 정의에 자주 사용하는 속성이다.

block : block 속성 지정
inline : inline 속성 지정
inline-block : inline-block 속성 지정
none : 화면에 나오지 않는다.

자세한 속성 표시는 실습.

HTML 요소는 디스플레이 속성이 없어도 기본적으로 block 또는 inline의 속성을 갖고 있다.

### 5.1 block 값을 갖는 HTML 요소

`block` 값을 갖는 요소는 아래의 특징을 갖고 있다.

- 언제나 새로운 라인에서 시작
- 가로폭 전체를 차지 (항상 width: 100%)
- width, height, margin, padding 속성 지정 가능
- block 속성 값을 갖는 요소 내에 inline 속성 값을 갖는 요소를 갖을 수 있다.
- block 속성 값을 갖는 요소 예
  - div
  - h1 ~ h6
  - p
  - ol
  - ul
  - li
  - hr
  - table
  - form

개발자 도구로 아래 예제의 요소 크기 확인해 보기

```
<!DOCTYPE html>
<html>
<head>
  <style>
    div:nth-of-type(1) {
      background-color: #FFA07A;
      padding: 20px;
    }
    div:nth-of-type(2) {
      background-color: #FF7F50;
      padding: 20px;
      width: 300px;
    }
  </style>
</head>
<body>
  <div>
    <h2>블록 레벨 요소</h2>
    <p>width, height 미지정 → width: 100%; height: auto;</p>
  </div>
  <div>
    <h2>블록 레벨 요소</h2>
    <p>width: 300px → width: 300px; height: auto;</p>
  </div>
</body>
</html>
```
