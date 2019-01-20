## 8. form 관련 태그들

사용자와 상호작용을 하기 위해 필수적인 요소, 사용자로부터 입력을 받을 수 있는 방법을 제공하며, input, textarea, button 등이 있다.

## 8.1 form 태그

입력을 받을 수 있는 양식(form)을 제공한다. input, textarea, button, submit button 등을 포함할 수 있다.

## 8.1.1 속성

- action : 입력된 내용이 전송될 URL을 지정한다.
- method : http 메소드를 지정한다. get, post 등이 있으며 자세한 내용은 [모질라](https://developer.mozilla.org/ko/docs/Web/HTTP/Methods)

아래 예제의 전송을 클릭하면 action 주소인 https://www.everyeos.com/users으로 id와 password가 body에 담겨서 전송된다.

```
<!DOCTYPE html>
<html>
  <body>
    <form action="https://www.everyeos.com/users" method="post">
      아이디: <input type="text" name="id" value=""><br>
      비밀번호: <input type="text" name="password" value=""><br>
      <input type="submit" value="전송">
    </form>
  </body>
</html>
```

[jsfiddle](https://jsfiddle.net/2sjkh7px/)

## 8.2 input 태그

사용자로부터 입력을 받기 위해 가장 중요한 태그이다. input태그에는 다양한 종류가 있는데 `type` 속성을 통해서 구분된다. form 태그 안에 있어야 전송할 수 있지만 javascript를 이용하여 전송하면 form 태그에 있지 않아도 된다.
전송되는 데이터는 name 속성의 키, value 속성이 값으로 하여 key=value 형태로 전송된다.

- **text** : 텍스트 입력
- **button** : 버튼
- **checkbox** : 체크 박스
- **file** : 파일 선택
- **hidden** : 화면에 표시되지 않는 입력, action으로는 전송된다.
- **password** : 비밀번호 입력
- **radio** : 라디오 버튼, name을 같은 것으로 주면 여러 라디오버튼 중 1개만 선택됨
- **submit** : from 제출 버튼
- color : 컬러 선택, HTML5
- date : 년월일 선택, HTML5
- datetime-local : 타임존 없이 년월일시분초 선택. 파이어폭스, 사파리, ie12 이전 버전에선 지원하지 않는다, HTML5
- email : 이메일 입력, submit시 이메일 형식을 검증한다, HTML5
- image : 이미지를 넣을 수 있는 submit 버튼 생성
- month : 월 선택, HTML5
- number : 숫자 입력, HTML5
- range : 범위 선택
- reset : form 데이터 초기화
- search : 검색어 입력, HTML5
- tel : 전화번호 입력, HTML5
- time : 시간 선택, HTML5
- url : url 입력, HTML5
- week : 주 선택, HTML5

```
<!DOCTYPE html>
<html>
  <body>
    <h3>button</h3>
    <input type="button" value="클릭" onclick="alert('덕덕월드 하이')">
    <hr>

    <h3>체크 박스</h3>
    <input type="checkbox" name="fruit1" value="apple" checked> 사과<br>
    <input type="checkbox" name="fruit2" value="grape"> 포도<br>
    <input type="checkbox" name="fruit3" value="peach"> 복숭아<br>
    <hr>

    <h3>색상</h3>
    <input type="color" name="c">
    <hr>

    <h3>날짜</h3>
    <input type="date" name="birthday">
    <hr>

    <h3>datetime-local</h3>
    <input type="datetime-local" name="now">
    <hr>

    <h3>이메일</h3>
    <input type="email" name="email">
    <hr>

    <h3>파일</h3>
    <input type="file" name="file1">
    <hr>

    <h3>hidden</h3>
    <input type="hidden" name="country" value="Norway">
    hidden은 나오지 않음
    <hr>

    <h3>이미지 submit</h3>
    <input type="image" src="img/img_submit.gif" alt="submit" width="48" height="48">
    <hr>

    <h3>년/월 선택</h3>
    <input type="month" name="yearmonth">
    <hr>

    <h3>숫자</h3>
    <input type="number" name="qty" min="2" max="10" step="2" value="2">
    <hr>

    <h3>비밀번호</h3>
    <input type="password" name="password">
    <hr>

    <h3>선택</h3>
    <input type="radio" name="gender" value="male" checked> 남자<br>
    <input type="radio" name="gender" value="female"> 여자<br>
    <hr>

    <h3>범위</h3>
    <input type="range" name="points" min="0" max="10" step="1" value="5">
    <hr>

    <h3>초기화</h3>
    <input type="reset">
    <hr>

    <h3>검색</h3>
    <input type="search" name="daum">
    <hr>

    <h3>submit</h3>
    <input type="submit" value="Submit">
    <hr>

    <h3>전화</h3>
    <input type="tel" name="tel">
    <hr>

    <h3>텍스트</h3>
    <input type="text" name="addr">
    <hr>

    <h3>시간</h3>
    <input type="time" name="time">
    <hr>

    <h3>URL</h3>
    <input type="url" name="url">
    <hr>

    <h3>주 선택</h3>
    <input type="week" name="week">
  </body>
</html>
```

[jsfiddle](https://jsfiddle.net/2sjkh7px/2/)

## 8.3 select 태그

드롭다운 목록으로 여러개 중에 1개를 선택할 때 사용된다.

```
<!DOCTYPE html>
<html>
  <body>
    <select name="cars1">
      <option value="volvo" selected>Volvo</option>
      <option value="saab" disabled>Saab</option>
      <option value="fiat">Fiat</option>
      <option value="audi">Audi</option>
    </select>

    <select name="cars2" size="4" multiple>
      <option value="volvo">Volvo</option>
      <option value="saab">Saab</option>
      <option value="fiat">Fiat</option>
      <option value="audi" selected>Audi</option>
    </select>

    <select name="cars3">
      <optgroup label="Swedish Cars">
        <option value="volvo">Volvo</option>
        <option value="saab">Saab</option>
      </optgroup>
      <optgroup label="German Cars" disabled>
        <option value="mercedes">Mercedes</option>
        <option value="audi">Audi</option>
      </optgroup>
    </select>
  </body>
</html>
```

[jsfiddle](https://jsfiddle.net/z025ed8o/1/)

## 8.4 textarea 태그

여러 줄의 글자를 입력할 수 있다.

```
<!DOCTYPE html>
<html>
  <body>
    <textarea name="txt" rows="10" cols="30">여러줄을 입력할 수 있습니다</textarea>
  </body>
</html>
```

[jsfiddle](https://jsfiddle.net/0qhfw7nd/)

## 8.5 button 태그

button 태그는 버튼을 생성한다. 동작은 `<input type="button">`과 동일하지만 input는 자식이 없는 태그인 반면에 button 태그는 글자나 이미지 같은 content를 넣을 수 있다.

- type : 버튼 타입을 정의하며 button, reset, submit가 있다.

```
<!DOCTYPE html>
<html>
  <body>
    <button type="button" onclick="alert('하이!')">
      <span style="color: red;">클릭</span>
    </button>

    <input type="button" value="클릭" onclick="alert('하이!')">
  </body>
</html>
```

[jsfiddle](https://jsfiddle.net/d3u1g860/)

## 8.6 fieldset / legend 태그

fieldset 태그는 입력양식들을 그룹화할 때 사용한다. legend 태그는 fieldset 자식으로 있어야 하며, fieldset의 제목을 정의한다.

```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
  </head>
  <body>
      <fieldset>
        <legend>로그인</legend>
        아이디 <input type="text" name="username">
        비밀번호 <input type="text" name="password">
      </fieldset>
  </body>
</html>
```

[jsfiddle](https://jsfiddle.net/znaurw6x/)

## 9 레이아웃 구성

참고 : https://poiemaweb.com/html5-tag-structure

레이아웃을 구성하는 태그에는 ```<div>```와 ```<span>```이 있다. 둘의 차이는 ```<span>```태그는 display가 inline속성이라는 점이다.
div는 박스 형태로 레이아웃이 형성되지만 span은 줄 단위로 레이아웃이 형성되기 때문에 아래의 예제와 같이 결과가 다르다.
div는 width와 height의 크기를 갖을 수 있지만 span은 inline 속성이기 때문에 크기를 갖을 수 없다.

```
<!DOCTYPE HTML>
<html>
<head>
<style type="text/css">
    #div1 {
        background-color: yellow;
        padding: 10px;
        border: 1px solid;
    }
    #span1 {
        background-color: cyan;
        border: 1px solid;
    }
</style>
</head>
<body>
    <div id="div1">
지금의 약세장을 극복할 수 있는 종목에 관심을 갖으라고 덧붙였다.', '부모에게 아이와 신뢰를 쌓을 수 있도록 특별한 대화 시간을 갖으라고 권한다.'에서 '갖으라고'라고 썼는데, 이것이 맞는 표현인지요? '가지라고'라고 쓰는 것이 맞는 것이 아닌지요?
    </div><br/>
    <span id="span1">
표준어 규정-표준어 사정 원칙' 제16항에서는 준말의 활용형에 제한을 가하는 규정을 제시하고 있습니다. '가지다'의 준말 '갖다'는 어간 '갖' 뒤에 모음으로 시작하는 어미가 붙어 '갖아, 갖아라, 갖았다, 갖으라고'와 같이 활용하지 못합니다. 제시하신 문장에는 '갖다'의 본말인 '가지다'의 어간 '가지-' 뒤에 어미 '-라고'가 붙은 활용형 '가지라고'를 쓰는 것이 알맞습니다.
    </span>
</body>
</html>
```

[jsfiddle](https://jsfiddle.net/2c3u7y8p/)

div와 span의 배치

```
<!DOCTYPE HTML>
<html>
<head>
<style type="text/css">
    div {
        width: 300px; height: 20px;
        border: 1px solid; padding: 5px;
        margin: 10px;
    }
    #div1 {background-color: red;}
    #div2 {background-color: yellow;}
    #div3 {background-color: blue;}
     
    span {
        width: 300px; height: 20px;
        border: 1px solid; padding: 5px;
        margin: 10px;
    }
    #span1 {background-color: red; padding: 5px;}
    #span2 {background-color: yellow;}
    #span3 {background-color: blue;}
</style>
</head>
<body>
    <div id="div1">div 1</div>
    <div id="div2">div 2</div>
    <div id="div3">div 3</div>
    <span id="span1">span 1</span>
    <span id="span2">span 2</span>
    <span id="span3">span 3</span>
</body>
</html>
```

[jsfiddle](https://jsfiddle.net/hdx9bvea/)
