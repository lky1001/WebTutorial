# CSS

CSS(Cascading Style Sheets)는 HTML 요소의 스타일을 정의하는 역할을 한다. [W3C 표준](https://www.w3.org/Style/CSS/#specs)이며, HTML 뿐만아니라 XHTML, XML에도 사용한다고 한다.

HTML5 이전 HTML에는 style을 컨트롤할 수 있는 태그(font, center)가 존재하여 CSS가 없이도 어느 정도의 스타일 표현이 가능하였으나

HTML5에서는 HTML는 문서의 정의, 구조화를 담당하고, CSS는 styling의 정의 각자의 역할에 충실하기 위해 분리되었다고 한다.

## 버전

- CSS 1 : 1996년, 더 이상 사용하지 않음
- CSS 2 : 1998년
- CSS 3 : 2005년

### CSS 검사도구 : https://jigsaw.w3.org/css-validator/

## 1. CSS에서 사용되는 용어

### 1.1 룰셋 (Rule Set)

<img src="http://www.nextree.co.kr/content/images/2016/09/yrkim-140327-selector-04.png"/>

(출처 : http://www.nextree.co.kr/p8468/)

위와 같은 것을 Rule Set(또는 Rule)이라 하며 셀렉터에 의해 선택된 특정 HTML 요소를 어떻게 렌더링(Rendering)할 것인지 브라우저에 지시하는 역할을 한다. 위의 CSS Rule set은 HTML 문서에 속해 있는 셀렉터를 통해 모든 p 요소를 선택한 후 선택된 p 요소의 스타일을 선언 블록에서 정의하고 있다.

이와 같은 Rule Set의 모아 놓을 것을(집합) 스타일시트(Style Sheet)라 한다.

### 1.2 셀렉터 (Selector, 선택자)

HTML 요소에 스타일을 적용하기 위해서는 먼저 **어떤 요소에 스타일을 적용할지 선택**할 수 있어야 한다.
셀렉터는 CSS에서 제공하는 HTML 요소를 선택하는 방법이다.

예: body에 배경색 주기

```
body {
  background: red;
}
```

위의 예제에서 body 부분이 셀렉터이다. 셀럭터 안의 선언 블록 `{ }` 내부에 스타일 속성과 값을 지정한다.

### 1.3 프로퍼티(Property, 속성)

셀럭터로 스타일을 적용 원하는 HTML 요소를 선택한 후 `{ }` 내부에 `프로퍼티: 밸류` 형식으로 원하는 스타일을 지정한다.
프로퍼티는 여러 개를 적용할 수 있으며 `;`으로 각 프로퍼티를 구분해 준다.

```
body {
  background: red;
  color: blue;
}
```

### 1.4 밸류(Value, 속성값)

스타일을 적용하기 위해서 프로퍼티에 지정된 값을 정해줘야 한다. 값은 특정한 단어나 색상 값 또는 크기 단위 등으로 표현된다. 자세한 단위 [참고](https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Values_and_units)

```
body {
  background: #e9e9e9;
  color: blue;
  font-size: 19pt;
}
```

## 2 html에 css 적용 방법

### 2.1 html 페이지 내장(embedded)

HTML 문서 내에 css를 내장한다.

```
<!DOCTYPE html>
<html>
  <head>
    <style>
      h1 { color: red; }
      p  { background: aqua; }
    </style>
  </head>
  <body>
    <h1>덕덕월드</h1>
    <p>안늉</p>
  </body>
</html>
```

### 2.2 link

HTML 문서에서 외부에 작성된 css 파일을 링크한다.

index.html

```
<!DOCTYPE html>
<html>
  <head>
    <link rel="stylesheet" href="css/style.css">
  </head>
  <body>
    <h1>덕덕월드</h1>
    <p>안늉</p>
  </body>
</html>
```

style.css

```
h1 { color: red; }
p  { background: blue; }
```

### 3.3 inline style

HTML 요소의 style 속성에 css를 작성한다.

```
<!DOCTYPE html>
<html>
  <body>
    <h1 style="color: red">덕덕월드</h1>
    <p style="background: aqua">안늉</p>
  </body>
</html>
```

## 3. 선택자 (Selector)

CSS 선택자는 HTML 요소의 name, id, class, 기타 속성 등으로 스타일을 적용할 HTML 요소를 선택하는 역할을 한다. 선택자를 이용해서 HTML 요소를 특정한 후 선택된 요소에 스타일을 적용하게 되는 것이다.

여러 개의 HTML 요소를 한번에 선택할 수도 있으며 콤마(,)로 구분한다.

```
h1, h2, h3 { color: blue; }
```

### 3.1 전체 선택자(Universal Selector)

선택자 패턴 : `*`
설명 : html과 head를 포함하여 HTML 문서의 모든 요소를 선택한다.

```
<!DOCTYPE html>
<html>
<head>
  <style>
    * { color: blue; }
  </style>
</head>
<body>
  <h1>헬로우</h1>
  <div>
    <p>월드 1</p>
    <p>콘 2</p>
  </div>
  <p>덕덕 3</p>
</body>
</html>
```

### 3.2 태그 선택자(Type Selector)

선택자 패턴 : HTML 태그명
설명 : HTML 태그명을 가진 요소를 선택한다.

```
<!DOCTYPE html>
<html>
<head>
  <style>
    p { color: blue; }
  </style>
</head>
<body>
  <h1>헬로우</h1>
  <div>
    <p>우리만</p>
    <p>파랗다</p>
  </div>
  <p>덕덕 3</p>
</body>
</html>
```

### 3.3 클래스 선택자(Class Selector)

선택자 패턴 : `HTML 요소의 class 속성`
설명 : HTML 요소의 class 속성 값을 지정하여 요소를 선택한다. 선택자는 클래스명 앞에 `.` 붙인다. 자식 요소에도 적용된다.

```
<!DOCTYPE html>
<html>
<head>
  <style>
    .test { color: blue; }
  </style>
</head>
<body>
  <h1>누가 변할까요</h1>
  <div class="test">
    aaaa
    <p id="p1">자식이에요</p>
    <p id="p2">나도 변해요</p>
  </div>
  <p>난 안변해요</p>
</body>
</html>
```

HTML 요소의 class 속성은 공백으로 구분하여 여러 개를 지정할 수 있다.
여러가지 룰셋을 미리 만들어 놓으면 재사용에 용의하다.

```
<!DOCTYPE html>
<html>
<head>
  <style>
    /* 가운데 정렬 */
    .text-center { text-align: center; }
    /* 폰트 크게 */
    .text-large  { font-size: 200%; }
    /* 폰트 빨강색 */
    .text-red    { color: red; }
    /* 폰트 파란색 */
    .text-blue   { color: blue; }
  </style>
</head>
<body>
  <p class="text-center">가운데 정렬</p>
  <p class="text-large text-red">크고 빨강색</p>
  <p class="text-center text-large text-blue">가운데 정렬, 크고, 파란색</p>
</body>
</html>
```

### 3.4 ID 선택자(ID Selector)

선택자 패턴 : `HTML 요소의 id 속성`
설명 : HTML 요소의 id 속성 값을을 지정하여 요소를 선택한다. 선택자는 id 속성값 앞에 `#`을 붙인다.

```
<!DOCTYPE html>
<html>
<head>
  <style>
    /* id가 p1인 것 선택 */
    #p1 { color: red; }
  </style>
</head>
<body>
  <div class="test">
    <p id="p1">문단 1</p>
    <p id="p2">문단 2</p>
    <p id="p1">문단 중복 1</p>
  </div>
  <p>문단 3</p>
</body>
</html>
```

### 3.5 복합 선택자(Combinator)

### 3.5.1 자손 셀렉터(Descendant Combinator)

자식의 요소보다 1 단계 상위에 있는 요소를 부모 요소라고하고, 자신의 요소보다 1단계 하위에 있는 요소를 자식 요소라고 한다.
그리고 자신의 요소보다 n단계 하위에 있는 요소를 자손(후손?) 요소라고 한다.
즉 1단계 하위는 자식이자 자손이다. 만약 셀렉터에 의해 자식요소와 자손요소를 동시에 만족하게 되었을 경우 우선순위가 없으므로,
마지막에 정의한게 적용된다.

<img src="https://poiemaweb.com/img/descendant-child.png"/>

(출처 : https://poiemaweb.com/css3-selector)

선택자 패턴 : `셀렉터1 셀렉터2 셀렉터3`
설명 : 셀렉터 패턴을 공백으로 나눠서 연속으로 적으면 된다.

```
<!DOCTYPE html>
<html>
<head>
  <style>
    div p { color: red; }
    div p span { color: blue; }
  </style>
</head>
<body>
  <h1>Heading</h1>
  <div>
    <p>paragraph 1</p>
    <p>paragraph 2</p>
    <span><p>paragraph 3</p></span>
    <p><span>paragraph 4</span></p>
  </div>
  <p>paragraph 5</p>
</body>
</html>
```

### 3.5.2 자식 셀렉터(Child Combinator)

선택자 패턴 : `셀렉터1 > 셀렉터2`
설명 : `>`를 이용해 자식 요소를 표현하며, 셀렉터1의 모든 자식요소중에 셀렉터2를 만족하는 요소를 선택한다.

```
<!DOCTYPE html>
<html>
<head>
  <style>
    div > p { color: blue; }
    div > #name { color: red; }
  </style>
</head>
<body>
  <h1>Heading</h1>
  <div>
    <p>paragraph 1</p>
    <p>paragraph 2</p>
    <span><p>paragraph 3</p></span>
    <p id="name">paragraph 4</p>
  </div>
  <p>paragraph 5</p>
</body>
</html>
```

### 3.5.3 형제(동위) 셀렉터(Sibling Combinator)

형제 셀렉터는 같은 level에 있는 요소들 중에서 뒤에 있는 요소를 선택할 때 사용한다.

<img src="https://poiemaweb.com/img/Sibling_Combinator.png"/>

(출처 : https://poiemaweb.com/css3-selector)

### 3.5.3.1 인접 형제 셀렉터(Adjacent Sibling Combinator)

선택자 패턴 : `셀렉터1 + 셀렉터2`
설명 : 동등한 위치에 있는 요소중에 셀렉터1 **바로 다음에** 나오는 셀렉터2를 선택한다. 둘 사이에 다른 요소가 있으면 안된다.

```
<!DOCTYPE html>
<html>
<head>
  <style>
    /* p 요소의 형제 요소 중에 p 요소 바로 뒤에 위치하는 ul 요소를 선택한다. */
    p + ul { color: red; }
  </style>
</head>
<body>
  <div>A div element.</div>
  <ul>
    <li>Coffee</li>
    <li>Tea</li>
    <li>Milk</li>
  </ul>

  <p>The first paragraph.</p>
  <ul>
    <li>Coffee</li>
    <li>Tea</li>
    <li>Milk</li>
  </ul>

  <h2>Another list</h2>
  <ul>
    <li>Coffee</li>
    <li>Tea</li>
    <li>Milk</li>
  </ul>
</body>
</html>
```

### 3.5.3.2 일반 형제 셀렉터(General Sibling Combinator)

선택자 패턴 : `셀렉터1 ~ 셀렉터2`
설명 : 동등한 위치에 있는 요소중에 셀렉터1 다음에 나오는 모든 셀렉터2를 선택한다.

```
<!DOCTYPE html>
<html>
<head>
  <style>
    /* p 요소의 형제 요소 중에 p 요소 뒤에 위치하는 ul 요소를 모두 선택한다.*/
    p ~ ul { color: red; }
  </style>
</head>
<body>
  <div>A div element.</div>
  <ul>
    <li>Coffee</li>
    <li>Tea</li>
    <li>Milk</li>
  </ul>

  <p>The first paragraph.</p>
  <ul>
    <li>Coffee</li>
    <li>Tea</li>
    <li>Milk</li>
  </ul>

  <h2>Another list</h2>
  <ul>
    <li>Coffee</li>
    <li>Tea</li>
    <li>Milk</li>
  </ul>
</body>
</html>
```

### 3.6 속성 선택자(Attribute Selector)

HTML요소와 특정 속성을 이용하여 요소를 선택한다.

선택자 패턴 : `HTML 요소[속성]`
설명 : HTML 요소와 속성이름을 이용하여 선택한다.

a태그의 target 속성을 갖는 요소를 선택하려면

```
<!DOCTYPE html>
<html>
<head>
  <style>
    a[target] { background: yellow; }
  </style>
</head>
<body>
  <a href="https://www.everyeos.com">everyeos.com</a><br>
  <a href="https://www.eosuite.app" target="_blank">eosuite.app</a><br>
</body>
</html>
```

선택자 패턴 : `HTML 요소[속성=값]`
설명 : HTML 요소와 속성 이름과 속성 값을 이용하여 선택한다.

```
<!DOCTYPE html>
<html>
<head>
  <style>
    a[target="_blank"] { background: yellow; }
  </style>
</head>
<body>
  <a href="https://www.everyeos.com" target="_blank">everyeos.com</a><br>
  <a href="https://www.eosuite.app" target="_self">eosuite.app</a><br>
</body>
</html>
```

선택자 패턴 : `HTML 요소[속성~=값]`
설명 : HTML 요소와 속성에 지정된 값을 공백으로 나누었을때 일치하는 것을 선택한다.

```
<!DOCTYPE html>
<html>
<head>
  <style>
    h1[name~="name"] { color: red; }
  </style>
</head>
<body>
  <h1 name="heading name">Heading 1</h1>
  <h1 name="heading-name">Heading-first</h1>
  <h1 title="headingname">Heading second</h1>
  <h1 title="heading test">Heading third</h1>
</body>
</html>
```

선택자 패턴 : `HTML 요소[속성|=값]`
설명 : HTML 요소와 속성에 지정된 값이 일치하거나 값 뒤에 `-`가 오는 경우 선택

p[name|=kai]일 경우 `<p name="kai">`와 `<p name="kai-">`와 같은 패턴이 선택된다.

```
<!DOCTYPE html>
<html>
<head>
  <style>
    h1[name|="kai"] { color: gray; }
  </style>
</head>
<body>
  <h1 name="kai">kai</h1>
  <h1 name="kai-">kai-</h1>
  <h1 name="kai-1001">kai-1001</h1>
  <h1 name="-kai">-kai</h1>
</body>
</html>
```

선택자 패턴 : `HTML 요소[속성^=값]`
설명 : HTML 요소와 속성에 지정된 값으로 시작하는 요소를 선택한다.

```
<!DOCTYPE html>
<html>
<head>
  <style>
    h1[name^="kai"] { color: gray; }
  </style>
</head>
<body>
  <h1 name="kai">kai</h1>
  <h1 name="kai-">kai-</h1>
  <h1 name="test-kai-1001">test-kai-1001</h1>
  <h1 name="-kai">-kai</h1>
</body>
</html>
```

선택자 패턴 : `HTML 요소[속성$=값]`
설명 : HTML 요소와 속성에 지정된 값으로 끝나는 요소를 선택한다.

```
<!DOCTYPE html>
<html>
<head>
  <style>
    h1[name$="kai"] { color: gray; }
  </style>
</head>
<body>
  <h1 name="kai">kai</h1>
  <h1 name="kai-">kai-</h1>
  <h1 name="test-kai-1001">test-kai-1001</h1>
  <h1 name="-kai">-kai</h1>
</body>
</html>
```

선택자 패턴 : `HTML 요소[속성$=값]`
설명 : HTML 요소와 속성에 지정된 값을 포함하는 모든 요소를 선택한다.

```
<!DOCTYPE html>
<html>
<head>
  <style>
    h1[name*="kai"] { color: gray; }
  </style>
</head>
<body>
  <h1 name="kai">kai</h1>
  <h1 name="kai-">kai-</h1>
  <h1 name="test-kai-1001">test-kai-1001</h1>
  <h1 name="-kai">-kai</h1>
  <h1 name="-kia">-kia</h1>
</body>
</html>
```

### 3.7 가상 클래스 셀렉터(Pseudo-Class Selector)

가상 클래스는 실제 존재하지는 않지만 요소의 상태에 따라 스타일을 지정하기 위해 선택하는 방법ㅇ이다.
상태의 예는 다음과 같다.

- 마우스가 올라 갔을때
- 링크에 이미 방문한 경우
- 링크에 아직 방문하지 않은 경우

가상클래스는 `셀렉터:상태`와 같이 `:`으로 구분하여 사용한다.
CSS 표준에 의해 이미 정해진 이름이 있기 때문에 임의로 지정할 수는 없다

```
셀렉터:presudo-class {
  속성: 값;
}
```

```
<!DOCTYPE html>
<html>
<head>
  <style>
    /* a 요소가 hover 상태일 때 */
    a:hover { color: red; }
  </style>
</head>
<body>
  <a href="#">올려봐~</a><br><br>
</body>
</html>
```

[모든 가상 클래스](https://developer.mozilla.org/ko/docs/Web/CSS/Pseudo-classes)

### 3.7.1 링크 셀렉터(Link pseudo-classes), 동적 셀렉터(User action pseudo-classes)

- `:link` 선택된 요소가 아직 방문하지 않은 링크
- `:visited` 선택된 요소가 이미 방문한 링크
- `:hover` 선택된 요소가 링크에 마우스가 올라와 있을때
- `:active` 선택된 요소가 클릭된 상태일때(클릭에서 뗄때까지)
- `:focus` 선택된 요소에 포커스가 되어 있을 때

```
<!DOCTYPE html>
<html>
<head>
  <style>
    /* a 요소가 방문하지 않은 링크일 때 */
    a:link { color: orange; }

    /* a 요소가 방문한 링크일 때 */
    a:visited { color: green; }

    /* a 요소에 마우스가 올라와 있을 때 */
    a:hover { font-weight: bold; }

    /* a 요소가 클릭된 상태일 때 */
    a:active { color: blue; }

    /* text input 요소와 password input 요소에 포커스가 들어와 있을 때 */
    input[type=text]:focus,
    input[type=password]:focus {
      color: red;
    }
    </style>
  </head>
<body>
  <a href="#" target="_blank">This is a link</a><br>
  <input type="text" value="I'll be red when focused"><br>
  <input type="password" value="I'll be red when focused">
</body>
</html>
```

### 3.7.2 UI 요소 상태 셀렉터(UI element states pseudo-classes)

- `:checked` 선택된 요소가 체크(선택) 상태일 때
- `:enabled` 선택된 요소가 사용 가능한 상태일 때
- `:disabled` 선택된 요소가 사용 불가능한 상태일 때

```
<!DOCTYPE html>
<html>
<head>
  <style>
    /* input 요소가 사용 가능한 상태일 때,
       input 요소 바로 뒤에 위치하는 인접 형제 span 요소를 선택 */
    input:enabled + span {
      color: blue;
    }
    /* input 요소가 사용 불가능한 상태일 때,
       input 요소 바로 뒤에 위치하는 인접 형제 span 요소를 선택 */
    input:disabled + span {
      color: gray;
      text-decoration: line-through;
    }
    /* input 요소가 체크 상태일 때,
       input 요소 바로 뒤에 위치하는 인접 형제 span 요소를 선택 */
    input:checked + span {
      color: red;
    }
  </style>
</head>
<body>
  <input type="radio" checked="checked" value="male" name="gender"> <span>Male</span><br>
  <input type="radio" value="female" name="gender"> <span>Female</span><br>
  <input type="radio" value="neuter" name="gender" disabled> <span>Neuter</span><hr>

  <input type="checkbox" checked="checked" value="bicycle"> <span>I have a bicycle</span><br>
  <input type="checkbox" value="car"> <span>I have a car</span><br>
  <input type="checkbox" value="motorcycle" disabled> <span>I have a motorcycle</span>
</body>
</html>
```

### 3.7.3 구조 가상 클래스 셀렉터(Structural pseudo-classes)

### 3.7.4 부정 셀렉터(Negation pseudo-class)

### 3.8 가상 요소 셀렉터(Pseudo-Element Selector)
