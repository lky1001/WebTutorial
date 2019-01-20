# CSS

CSS(Cascading Style Sheets)는 HTML 요소의 스타일을 정의하는 역할을 한다. [W3C 표준](https://www.w3.org/Style/CSS/#specs)이며, HTML 뿐만아니라 XHTML, XML에도 사용한다고 한다.

HTML5 이전 HTML에는 style을 컨트롤할 수 있는 태그(font, center)가 존재하여 CSS가 없이도 어느 정도의 스타일 표현이 가능하였으나 

HTML5에서는 HTML는 문서의 정의, 구조화를 담당하고, CSS는 styling의 정의 각자의 역할에 충실하기 위해 분리되었다고 한다.

## 버전
- CSS 1 : 1996년, 더 이상 사용하지 않음
- CSS 2 : 1998년
- CSS 3 : 2005년

## CSS 검사도구 : https://jigsaw.w3.org/css-validator/

## 1. CSS에서 사용되는 용어

### 1.1 셀렉터 (Selector, 선택자)

HTML 요소에 스타일을 적용하기 위해서는 먼저 **어떤 요소에 스타일을 적용할지 선택**할 수 있어야 한다.
셀렉터는 CSS에서 제공하는 HTML 요소를 선택하는 방법이다.

예: body에 배경색 주기

```
body {
  background: red;
}
```

위의 예제에서 body 부분이 셀렉터이다. 셀럭터 안의 선언 블록 { } 내부에 스타일 속성과 값을 지정한다.
