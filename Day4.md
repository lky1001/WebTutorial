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

- `:first-child` 선택된 모든 요소들 중 자신의 부모의 첫번째 자식 요소인 것을 선택한다.
- `:last-child` 선택된 모든 요소들 중 자신의 부모의 마지막 자식 요소를 선택한다.

```
<!DOCTYPE html>
<html>
<head>
  <style>
    /* p 요소 중에서 첫번째 자식을 선택 */
    p:first-child { color: red; }

    /* p 요소 중에서 마지막 자식을 선택 */
    /* body 요소의 두번째 p 요소는 마지막 자식 요소가 아니다.
       body 요소의 마지막 자식 요소는 div 요소이다. */
    p:last-child { color: blue; }
  </style>
</head>
<body>
  <p>This paragraph is the first child of its parent (body).</p>

  <h1>Welcome to My Homepage</h1>
  <p>This paragraph is not the first child of its parent.</p>

  <div>
    <p>This paragraph is the first child of its parent (div).</p>
    <p>This paragraph is not the first child of its parent.</p>
  </div>
</body>
</html>
```

- `nth-child(n)` 선택된 모든 요소들 중 자신의 부모의 n번째 자식 요소인 것을 선택한다.
- `:nth-last-child(n)` 선택된 모든 요소들 중 자신의 부모의 마지막으로부터 n번째 자식 요소를 선택한다.

```
<!DOCTYPE html>
<html>
<head>
  <style>
    /* ol 요소의 자식 요소인 li 요소 중에서 짝수번째 요소만을 선택 */
    ol > li:nth-child(2n)   { color: orange; }
    /* ol 요소의 자식 요소인 li 요소 중에서 홀수번째 요소만을 선택 */
    ol > li:nth-child(2n+1) { color: green; }

    /* ol 요소의 자식 요소인 li 요소 중에서 첫번쨰 요소만을 선택 */
    ol > li:first-child     { color: red; }
    /* ol 요소의 자식 요소인 li 요소 중에서 마지막 요소만을 선택 */
    ol > li:last-child      { color: blue; }

    /* ol 요소의 자식 요소인 li 요소 중에서 4번째 요소 요소만을 선택 */
    ol > li:nth-child(4)    { background: brown; }

    /* ul 요소의 모든 자식 요소 중에서 뒤에서부터 시작하여 홀수번째 요소만을 선택 */
    ul > :nth-last-child(2n+1) { color: red; }
    /* ul 요소의 모든 자식 요소 중에서 뒤에서부터 시작하여 짝수번째 요소만을 선택 */
    ul > :nth-last-child(2n)   { color: blue; }
  </style>
</head>
<body>
  <ol>
    <li>Espresso</li>
    <li>Americano</li>
    <li>Caffe Latte</li>
    <li>Caffe Mocha</li>
    <li>Caramel Latte</li>
    <li>Cappuccino</li>
  </ol>

  <ul>
    <li>Espresso</li>
    <li>Americano</li>
    <li>Caffe Latte</li>
    <li>Caffe Mocha</li>
    <li>Caramel Latte</li>
    <li>Cappuccino</li>
  </ul>
</body>
</html>
```

- `:first-of-type` 선택된 요소의 부모 요소의 자식 요소중 첫번째 요소를 선택
- `:last-of-type` 선택된 요소의 부모 요소의 자식 요소중 마지막 요소를 선택
- `:nth-of-type(n)` 선택된 요소의 부모 요소의 자식 요소 중 앞에서 n번째 요소를 선택
- `:nth-last-of-type(n)` 선택된 요소의 부모 요소의 자식 요소 중 뒤에서 n번째 요소를 선택

```
<!DOCTYPE html>
<html>
<head>
  <style>
    /* p 요소의 부모 요소의 자식 요소 중 첫번째 등장하는 p 요소 */
    p:first-of-type  { color: red; }
    /* p 요소의 부모 요소의 자식 요소 중 마지막 등장하는 p 요소 */
    p:last-of-type   { color: blue; }
    /* p 요소의 부모 요소의 자식 요소 중 앞에서 2번째에 등장하는 p 요소 */
    p:nth-of-type(2) { color: green; }
    /* p 요소의 부모 요소의 자식 요소 중 뒤에서 2번째에 등장하는 p 요소 */
    p:nth-last-of-type(2) { color: orange;}

    /* p 요소 중에서 첫번째 자식을 선택 */
    p:first-child { background: brown;}
  </style>
</head>
<body>
  <h1>This is a heading</h1>
  <p>The first paragraph.</p>
  <p>The second paragraph.</p>
  <p>The third paragraph.</p>
  <p>The fourth paragraph.</p>
  <div>
    <h1>This is a heading</h1>
    <p>The first paragraph.</p>
    <p>The second paragraph.</p>
    <p>The third paragraph.</p>
    <p>The fourth paragraph.</p>
  </div>
</body>
</html>
```

### 3.7.4 부정 셀렉터(Negation pseudo-class)

- `:not` 셀렉터에 해당하지 않는 모든 요소를 선택

```
<!DOCTYPE html>
<html>
<head>
  <style>
    /* input 요소 중에서 type 어트리뷰트의 값이 password가 아닌 요소를 선택 */
    input:not([type=password]) {
      background: yellow;
    }
  </style>
</head>
<body>
  <input type="text" value="Text input">
  <input type="email" value="email input">
  <input type="password" value="Password input">
</body>
</html>
```

### 3.8 가상 요소 셀렉터(Pseudo-Element Selector)

요소의 특정 부분에 스타일을 적용하기 위해 사용한다.

- 요소 컨텐츠의 첫글자 또는 첫줄
- 요소 컨텐츠의 앞 또는 뒤

가상 요소는 `::` 을 사용한다.

- `::first-letter` 컨텐츠의 첫 번째 글자를 선택
- `::first-line` 컨텐츠의 첫줄 선택, 블록 요소에만 적용 가능
- `::before` 컨텐츠의 앞에 위치하는 공간을 선택, 주로 content 속성과 함께 사용
- `::after` 컨텐츠의 뒤에 위치하는 공간을 선택, 주로 content 속성과 함께 사용
- `::selection` 드래그한 컨텐츠를 선택, 사파리나 ios에서 동작하지 않음

```
<!DOCTYPE html>
<html>
<head>
  <style>
    /* p 요소 콘텐츠의 첫글자를 선택 */
    p::first-letter { font-size: 3em; }
    /* p 요소 콘텐츠의 첫줄을 선택 */
    p::first-line   { color: red; }

    /* h1 요소 콘텐츠의 앞 공간에 content 어트리뷰트 값을 삽입한다 */
    h1::before {
      content: " HTML!!! ";
      color: blue;
    }
    /* h1 요소 콘텐츠의 뒷 공간에 content 어트리뷰트 값을 삽입한다 */
    h1::after {
      content: " CSS3!!!";
      color: red;
    }

    /* 드래그한 콘텐츠를 선택한다 */
    ::selection {
      color: red;
      background: yellow;
    }
  </style>
</head>
<body>
  <h1>This is a heading</h1>
  <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Explicabo illum sunt distinctio sed, tempore, repellat rerum et ea laborum voluptatum! Quisquam error fugiat debitis maiores officiis, tenetur ullam amet in!</p>
</body>
</html>
```

## 4. css 속성 값

## 4.1 속성 값 키워드

각각의 속성은 속성에 따라서 사용할 수 있는 키워드가 정해져 있다. 예를 들어 `text-align` 속성 값으로는 `center`, `left`, `right` 와 같은 미리 정해진 키워드가 있다.

## 4.2 크기의 단위

css에서 사용하는 대표적인 크기의 단위는 px, em, %이다. px는 절대값이고 em, %는 상대값이다.

대부분의 브라우저의 폰트 사이즈는 기본값으로 16px, 1em, 100%이다.

속성 값이 0인 경우 단위를 생략할 수 있다.

### 4.2.1 px (픽셀)

px는 픽셀(화소)라고 부르며 1px는 화소 1개의 크기를 나타낸다. 풀HD의 해상도가 1920 \* 1080인데 이는 가로 1920개의 픽셀 세로 1080개의 픽셀을 갖고 있다는 의미이다.

각각의 픽셀들은 빨강, 녹색, 파랑(RGB) 요소를 갖고 있다.

픽셀의 디바이스의 해상도(resolution)에 따라 상대적인 크기를 갖는다.

같은 인치의 크기의 디바이스지만 픽셀의 개수가 다를 수 있다.

<img src="https://poiemaweb.com/img/resolution.jpg">
[출처: http://news.samsungdisplay.com/]

디바이스의 크기와 픽셀은 제각각이기 때문에 픽셀을 기준으로 하는 단위는 화면에 얼마의 크기로 보일지는 명확하지 않다.

따라서 대부분의 브라우저는 1px를 1/96 인치의(즉 1인치의 크기에 픽셀이 96개 있다는 얘기) 절대 단위로 인식한다고 한다.

px는 요소나 이미지의 크기 지정에 주로 사용된다.

```

<!DOCTYPE html>
<html>
<head>
  <style>
    body {
      text-align: center;
    }
    div {
      font-size: 20px;
    }
  </style>
</head>
<body>
  <div>글자 크기: 20px</div>
</body>
</html>
```

### 4.2.2 % (퍼센트)

% 단위는 백분률로 상대 단위로 계산된다. 요소에 지정된 사이즈(부모의 사이즈나 없으면 기본 사이즈) 에 상대적인 크기로 설정된다.

```
<!DOCTYPE html>
<html>
<head>
  <style>
    body {
      font-size: 14px;
      text-align: center;
    }
    div {
      font-size: 120%; /* body의 폰트 사이즈인 14px * 1.2 = 16.8px */
    }
  </style>
</head>
<body>
  <div>글자 크기: 14px * 120% → 16.8px</div>
</body>
</html>
```

### 4.2.3 em

em은 상대 단위 요소이다. 요소에 지정된 사이즈(부모의 사이즈나 기본 사이즈)에 상대적인 사이즈를 설정하게 되고 배수로 지정된다. 예를 들어 부모 사이즈가 14px인 경우 1em은 14px이고 2em은 28px가 된다.

폰트 사이즈나 컨테이너의 크기에 주로 설정한다.

```
<!DOCTYPE html>
<html>
<head>
  <style>
    body {
      font-size: 14px;
      text-align: center;
    }
    div {
      font-size: 1.2em; /* 14px * 1.2 = 16.8px */
    }
  </style>
</head>
<body>
  <div>글자 크기: 1.2em → 14px * 1.2 = 16.8px</div>
</body>
</html>
```

**em은 모든 자식 요소에 영향을 주기 때문에 주의해야 한다.**

```
<!DOCTYPE html>
<html>
<head>
  <style>
    body {
      font-size: 14px;
      text-align: center;
    }
    div {
      font-size: 1.2em; /* 14px * 1.2 = 16.8px */
      font-weight: bold;
      padding: 2em;
    }
    .box1 { background-color: rgba(255, 0, 0, 0.2); }
    .box2 { background-color: rgba(255, 0, 0, 0.6); }
    .box3 { background-color: rgba(255, 0, 0, 0.8); }
  </style>
</head>
<body>
  <div class='box1'>
    Font size: 1.2em ⇒ 14px * 1.2 = 16.8px
    <div class='box2'>
      Font size: 1.2em ⇒ 16.8px * 1.2 = 20.16px
      <div class='box3'>
        Font size: 1.2em ⇒ 20.16px * 1.2 = 24.192px
      </div>
    </div>
  </div>
</body>
</html>
```

### 4.2.4 rem

em은 상속 때기 때문에 상황에 따라 값이 바뀔 수 있다. 같은 1.5em이여도 값이 다를 수 있다.

rem은 최상위 요소(html)의 사이즈를 기준으로 한다. rem의 r은 root를 의미한다.

```
<!DOCTYPE html>
<html>
<head>
  <style>
    html {
      font-size: 14px;
      /* font-size 미지정 시에는 16px */
    }
    div {
      font-size: 1.2rem; /* html font-size: 14px * 1.2 = 16.8px */
      font-weight: bold;
      padding: 2em;
      text-align: center;
    }
    .box1 { background-color: rgba(255, 0, 0, 0.2); }
    .box2 { background-color: rgba(255, 0, 0, 0.6); }
    .box3 { background-color: rgba(255, 0, 0, 0.8); }
  </style>
</head>
<body>
  <div class='box1'>
    Font size: 1.2rem ⇒ 14px * 1.2 = 16.8px
    <div class='box2'>
      Font size: 1.2rem ⇒ 14px * 1.2 = 16.8px
      <div class='box3'>
        Font size: 1.2rem ⇒ 14px * 1.2 = 16.8px
      </div>
    </div>
  </div>
</body>
</html>
```

### 4.2.5 viewport

웹페이지가 화면(Display)에 표시 되는 영역을 뜻한다. viewport는 웹 표준은 아니지만

애플의 모바일 사파리가 viwport라는 meta 태그를 도입해 웹 개발자들이 viewport의 크기와 스케일을 조장할 수 있게 했고,

현재는 대부분의 모바일 브라우저들이 이를 지원한다.

PC의 viewport와 모바일의 viewport는 다른 점이 있다. PC의 viewport는 브라우저의 창에 보이는 영역과 같다.

즉 사용자가 브라우저 창의 크기를 조절하면 viewport의 크기도 조절된다.

웹페이지가 viewport보다 크면 스크롤을 할 수 있다.

하지만 모바일 viewport는 브라우저 창보다 작을 수도 있고, 클수도 있다. 여러가지 터치 동작으로 viewport 배율을 변경할 수 도있다. (크기를 조절하는 것은 아님)

viewport에 대한 자세한 내용은 반응형웹에서 다루고 여기서는 사이즈 단위만 다룬다.

viewport의 단위는 방금 설명한 viewport를 기준으로 한 상대적 사이즈를 의미한다.

- vw : viewport width의 100분의 1
- vh : viewport height의 100분의 1
- vmin : viewport의 width와 height 중 작은 쪽의 100분의 1
- vmax : viewport의 width와 height 중 큰 쪽의 100분의 1

viewport width가 1000px, height가 600px인 경우 사이즈는 아래와 같이 계산된다.

1vw : viewport width 1000px의 1%인 10px
1vh : viewport height 600px의 1%인 6px
vmin : viewport height 600px의 1%인 6px
vmax : viewport width 1000px의 1%인 10px

### 4.2.6 색상

색상을 표현하는 단위에는 미리 지정된 키워드(black, red 등등)가 몇 가지 있으며 미리 지정된 색상은 [https://www.w3.org/TR/css-color-3/](https://www.w3.org/TR/css-color-3/) 에서 확인할 수 있다.

더 다양한 색상을 표현하기 위해서는 다음을 사용할 수 있다.

- `16진수 코드 값` : #00ffff 와 같은 형태를 이루며 2자리씩 R,G,B 값을 나타내며 각각의 자리는 0~FF(10진수로 255)의 범위이다.
- `RGB(Red값, Green값, Blue값)` : rgb(255, 0, 0) 와 같이 쓰며 0~255까지 값을 쓸 수 있다.
- `RGBA(Red값, Green값, Blue값, Alpha/투명도)` : rgb 색상에 투명도를 조절할 수 있다. rgb(255, 0, 0, 0.1), 여기서 알파는 0 ~ 1의 실수 범위이다.
- `HSL(Hue/색상, Saturation/채도, Lightness/명도)` : hsl(0, 100%, 0%) 와 같이 나타내며 Hue는 0~360의 숫자, 나머지는 0% ~ 100%로 백분률로 나태낸다. 참고 https://www.w3schools.com/colors/colors_hsl.asp
- `HSLA(Hue, Saturation, Lightness, Alpha)` : 투명도까지 조절할 수 있다. 여기서 알파는 0 ~ 1의 실수 범위이다. https://www.w3schools.com/cssref/func_hsla.asp

# 5. 박스 모델

모든 HTML 요소는 박스 형태의 영역을 갖고 있다. 이 박스는 컨텐츠(Content), 패딩(Padding), 테두리(Border), 마진(Margin)로 구성된다.

<img src="https://poiemaweb.com/img/box-model.png"/>
출처 : https://poiemaweb.com/css3-box-model

브라우저는 요소를 화면에 그릴때(렌더링) 속성(배경, 색상 등)과 위치를 근거로 한다.

컨텐츠(Content) : HTML 요소의 텍스트나 이미지 등 실제 화면에 보여지는 내용이 위치하는 영역. width, height 속성을 갖음
패딩(Padding) : 테두리(Border) 안쪽에 위치하는 요소의 내부 여백 영역이다. padding의 속성 값은 패딩의 두께를 나타내며 기본색은 투명(transparent)이다. HTML 요소에 배경색이나 배경 이미지를 지정하면 패딩까지 적용이 된다.
테두리(Border) : 테두리(Border) 영역으로 border의 속성 값은 테두리의 두께를 나타낸다.
마진(Margin) : 테두리(Border) 밖의 영역으로 HTML 요소의 외부 여백 영역이다. 마진 속성 값은 마진 영역의 두께를 나타내며 투명색으로 배경색을 지정할 수 없다.

```
<html>
<head>
  <style>
    div {
      /* 배경색의 지정: 콘텐츠 영역과 패딩 영역에 적용된다. */
      background-color: lightgrey;
      /* 콘텐츠 영역의 너비 */
      width: 300px;
      /* 패딩 영역의 두께 */
      padding: 25px;
      /* 테두리: 두께 형태 색상 */
      border: 25px solid navy;
      /* 마진 영역의 두께 */
      margin: 25px;
    }
  </style>
</head>
<body>
  <h2>Box Model</h2>

  <div>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</div>
</body>
</html>
```

# 5.1 width, height 속성

width와 height 속성은 HTML 요소의 가로와 세로 크기를 지정한다. 컨텐츠 영역에 적용된다.
`box-sizing` 속성의 기본값이 `content-box`이기 떄문에 컨텐츠 영역에 적용되는 것이며, `box-sizing` 속성에 `border-box` 값을 석용하면 `padding`, `border`가 포함된 영역을 지정할 수 있다.

만약 width와 height로 지정한 컨텐츠 영역보다 컨텐츠의 크기가 클 경우 영역을 넘치게 된다.
`overflow: hidden` 속성을 지정하면 컨텐츠 영역을 넘치는 컨텐츠를 감출 수 있다.

```
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <style>
    div {
      width: 300px;
      height: 100px;
      background-color: cornsilk;
      border: 5px solid navy;
    }
  </style>
</head>
<body>
  <div>
    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
  </div>
</body>
</html>
```

# 5.2 margin, padding 속성

margin, padding 속성은 컨텐츠의 4개 방향(top, right, left, bottom)에 대해 지정이 가능하다.

<img src="https://poiemaweb.com/img/box-model-detail.png">
출처 : https://poiemaweb.com/css3-box-model

```
<!DOCTYPE html>
<html>
  <head>
    <style>
      div {
        border: 5px solid red;

        margin-top: 40px;
        margin-right: 30px;
        margin-bottom: 20px;
        margin-left: 10px;

        padding-top: 10px;
        padding-right: 20px;
        padding-bottom: 30px;
        padding-left: 40px;
      }
    </style>
  </head>
  <body>
    <div>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</div>
  </body>
</html>
```

margin이나 padding은 한쪽 면씩 각각 지정할 수도 있지만, 한꺼번에 지정할 수도 있다.

4개의 값을 지정하면 아래의 의미와 같다.

```
margin: 10px 20px 30px 40px;

margin-top: 10px;
margin-right: 20px;
margin-bottom: 30px;
margin-left: 40px;
```

3개의 값을 지정하면 가운데 값은 right, left 값이 된다.

```
margin: 10px 20px 40px;

margin-top: 10px;
margin-right: 20px;
margin-left: 20px;
margin-bottom: 30px;
```

2개의 값을 지정하면 top/bottom, right/left로 값이 적용 된다.

```
margin: 10px 20px;

margin-top: 10px;
margin-bottom: 10px;
margin-right: 20px;
margin-left: 20px;
```

1개의 값을 지정하면 4곳에 모두 적용된다.

```
margin: 10px;

margin-top: 10px;
margin-bottom: 10px;
margin-right: 10px;
margin-left: 10px;
```

마진 속성에 auto 값을 지정하면 가운데 정렬 효과를 낼 수 있다.

```
margin: 0 auto;
```

```
<!DOCTYPE html>
<html>
  <head>
    <style>
      div {
        border: 5px solid red;
        width: 600px;
        margin: 0 auto;
      }
    </style>
  </head>
  <body>
    <div>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</div>
  </body>
</html>
```

# 5.3 border 속성

border 속성은 컨텐츠의 테두리를 지정한다.

## 5.3.1 border-style

`border-style` 속성은 테두리의 선 스타일을 지정한다.

선 종류는 [여기](https://developer.mozilla.org/ko/docs/Web/CSS/border-style)를 참고한다.

`border-style`은 마진, 패딩과 마찬가지로 4개의 방향(top, right, left, bottom)에 대해 각각 지정이 가능하다.

```html
<!DOCTYPE html>
<html>
  <head>
    <style>
      p {
        background: palegreen;
        padding: 10px;
      }
      p.d1 {
        /* four sides */
        border-style: dashed;
      }
      p.d2 {
        /* horizontal | vertical */
        border-style: dotted solid;
      }
      p.d3 {
        /* top | horizontal | bottom */
        border-style: hidden double dashed;
      }
      p.d4 {
        /* top | right | bottom | left */
        border-style: none solid dotted dashed;
      }
    </style>
  </head>
  <body>
    <p class="d1">border-style: dashed;</p>
    <p class="d2">border-style: dotted solid;</p>
    <p class="d3">border-style: hidden double dashed;</p>
    <p class="d4">border-style: none solid dotted dashed;</p>
  </body>
</html>
```

## 5.3.2 border-width

`border-width` 속성은 테두리의 두께를 지정한다. 이전과 마찬가지로 마찬가지로 4개의 방향(top, right, left, bottom)에 대해 각각 지정이 가능하다.

_border-width 속성은 border-style과 함께 사용하지 않으면 적용되지 않는다._

[예제](https://developer.mozilla.org/ko/docs/Web/CSS/border-width)

## 5.3.3 border-color 속성

`border-color` 속성은 테두리의 색상을 지정한다. 이전과 마찬가지로 마찬가지로 4개의 방향(top, right, left, bottom)에 대해 각각 지정이 가능하다.

_border-color 속성은 border-style과 함께 사용하지 않으면 적용되지 않는다._

[예제](https://developer.mozilla.org/ko/docs/Web/CSS/border-color)

```
<!DOCTYPE html>
<html>
  <head>
    <style>
      p {
        background: palegreen;
        padding: 10px;
        border-style: solid;
      }
      p.one {
        border-color: red;
      }
      p.two {
        border-color: green;
      }
      p.three {
        border-color: red green blue yellow;
      }

    </style>
  </head>
  <body>
    <h2>border-color Property</h2>

    <p class="one">border-color: red</p>
    <p class="two">border-color: green</p>
    <p class="three">border-color: red green blue yellow</p>
  </body>
</html>
```

## 3.5.4 border-radius

`border-radius` 속성은 테두리의 모서리를 둥글게 표현한다. 속성 값은 px, em같은 단위와 %를 사용한다. 이전과 마찬가지로 마찬가지로 4개의 방향(top, right, left, bottom)에 대해 각각 지정이 가능하다.

## 3.5.4 border
