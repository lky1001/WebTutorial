## 3.3 pre 태그 (Preformatted text)

pre 태그 내부에 있는 컨텐츠는 작성한 그대로 화면에 보이게 된다.

```
<!DOCTYPE html>
<html>
  <body>
    <pre>
      나는 프리하다.

      나는 마크업에 작성하는 그래도 화면에 보여진다.
      공       백이나


      줄바꿈도 마찬가지다.
    </pre>

  </body>
</html>
```

[jsfiddle](https://jsfiddle.net/q3adb1g8/)

## 3.4 hr 태그

hr태그는 수평줄을 추가한다.

```
<!DOCTYPE html>
<html>
  <body>
    <h1>다음</h1>
    <p>다음에</p>
    <hr>
    <h1>네이버</h1>
    <p>네버</p>
  </body>
</html>
```

[jsfiddle](https://jsfiddle.net/L5g7f389/)

## 3.5 q 태그

인용구를 지정할 때 사용한다. 큰따옴표로 감싸진다.

```
<!DOCTYPE html>
<html>
  <body>
    <p>인용구: <q>인용구입니다.</q></p>
  </body>
</html>
```

[jsfiddle](https://jsfiddle.net/zorLjmgp/)

## 3.6 blockquote 태그

```
<!DOCTYPE html>
<html>
  <body>
    <p>인용구</p>
    <blockquote>
      나는 들여쓴다
    </blockquote>
  </body>
</html>
```

[jsfiddle](https://jsfiddle.net/4uh0s2tc/)

## 4.1 하이퍼링크 (Hyperlink)

하이퍼텍스트는(Hypertext)는 참조(하이퍼링크)를 통해 독자가 한 문서에서 다른 문서로 접근할 수 있는 텍스트이다.[위키피디아](https://ko.wikipedia.org/wiki/%ED%95%98%EC%9D%B4%ED%8D%BC%ED%85%8D%EC%8A%A4%ED%8A%B8)
하이퍼링크는 하이퍼텍스트 문서 안에서 모든 형식의 자료를 가르킬 수 있는 참조 연결 고리이다.
줄여서 링크(link)라고도 부르며 HTML에서는 a(anchor) 태그가 담당한다.

```
<!DOCTYPE html>
<html>
  <body>
    <a href="https://www.everyeos.com">에브리이오스 가즈아ㅏㅏ</a>
  </body>
</html>
```

[jsfiddle](https://jsfiddle.net/nw4015z3/)

## 4.2 a 태그의 href 속성

href 속성은 이동하고자 하는 파일의 경로(위치)를 설정한다. 경로는 절대경로와 상대결로로 구분된다.

- 디렉토리(Directory) : 파일이나 다른 디렉토리 그룹을 갖고 있는 파일 시스템 안의 존재물. 폴더 또는 카탈로그라고도 한다.

1. 루트 디렉토리 : 파일 시스템 계층 구조에서 최상위의 디렉토리이다.

- Unix,Linux,OSX : /
- Windows : C:\

2. 작업 디렉토리 : 현재 작업중인 위치를 표현한다

- ./

3. 부모 디렉토리 : 현재 작업 디렉토리의 상위(부모) 디렉토리이다.

- ../

## 4.2.1 파일 경로

파일 경로는 파일 시스템 상에서 파일의 위치를 표현하는 방법이다.

- 절대경로 : 현재 위치와 상관 없이 최상위(루트)) 디렉토리로부터 경로지정한다.
- 상대경로 : 현재 위치로부터 경로를 지정한다.

```
절대 경로(Absolute path)
/index.html
http://www.everyeos.com/index.html
/Users/kai.1001/index.html

상대 경로(Relative path)
./index.html
../../home/index.html
index.html
html/index.html
```

## 4.2.2 href 속성

- 절대 URL : 웹사이트의 URL
- `<a href="http://www.everyeos.com/index.html">aaa</a>`
- 상대 URL : 자신의 현재 위치를 기준으로 한 URL
- `<a href="aaa.html">aaa</a>`
- fragment identifier : 현재 페이지 내의 특정 요소(엘리먼트)의 ID값
- `<a href="#bottom">아래로</a>`
- 이메일 주소
- `<a href="mailto:aaa@google.com">메일보내기</a>`
- 스크립트(script)
- `<a href="javascript:alert('good')">안녕</a>`

```
<!DOCTYPE html>
<html>
  <body>
    <a href="http://www.everyeos.com" target="_blank">EVERYEOS URL</a><br>
    <a href="html/mycom.html">상대경로</a><br>
    <a href="file/mycom.pdf">파일 링크</a><br>
    <a href="#">fragment identifier</a><br>
    <a href="mailto:aaa@gmail.com">메일보내기</a><br>
    <a href="javascript:alert('안늉');">인사</a>
  </body>
</html>
```

[jsfiddle](https://jsfiddle.net/4thq2snz/)

페이지 내에서 이동하기 (fragment identified)

```
<!DOCTYPE html>
<html>
<body>

<h2 id="top">Top of page!</h2>

<p>In my younger and more vulnerable years my father gave me some advice that I've been turning over in my mind ever since.</p>
<p>"Whenever you feel like criticizing any one," he told me, "just remember that all the people in this world haven't had the advantages that you've had."</p>
<p>He didn't say any more, but we've always been unusually communicative in a reserved way, and I understood that he meant a great deal more than that. In consequence, I'm inclined to reserve all judgments, a habit that has opened up many curious natures to me and also made me the victim of not a few veteran bores. The abnormal mind is quick to detect and attach itself to this quality when it appears in a normal person, and so it came about that in college I was unjustly accused of being a politician, because I was privy to the secret griefs of wild, unknown men. Most of the confidences were unsought-frequently I have feigned sleep, preoccupation, or a hostile levity when I realized by some unmistakable sign that an intimate revelation was quivering on the horizon; for the intimate revelations of young men, or at least the terms in which they express them, are usually plagiaristic and marred by obvious suppressions. Reserving judgments is a matter of infinite hope. I am still a little afraid of missing something if I forget that, as my father snobbishly suggested, and I snobbishly repeat, a sense of the fundamental decencies is parcelled out unequally at birth.</p>
<p>And, after boasting this way of my tolerance, I come to the admission that it has a limit. Conduct may be founded on the hard rock or the wet marshes, but after a certain point I don't care what it's founded on. When I came back from the East last autumn I felt that I wanted the world to be in uniform and at a sort of moral attention forever; I wanted no more riotous excursions with privileged glimpses into the human heart. Only Gatsby, the man who gives his name to this book, was exempt from my reaction-Gatsby, who represented everything for which I have an unaffected scorn. If personality is an unbroken series of successful gestures, then there was something gorgeous about him, some heightened sensitivity to the promises of life, as if he were related to one of those intricate machines that register earthquakes ten thousand miles away. This responsiveness had nothing to do with that flabby impressionability which is dignified under the name of the "creative temperament"-it was an extraordinary gift for hope, a romantic readiness such as I have never found in any other person and which it is not likely I shall ever find again. No-Gatsby turned out all right at the end; it is what preyed on Gatsby, what foul dust floated in the wake of his dreams that temporarily closed out my interest in the abortive sorrows and short-winded elations of men.</p>

<a href="#top">Go to top</a>
</body>
</html>
```

[jsfiddle](https://jsfiddle.net/sfpwe5hv/)

## 4.2.3 target 속성

target 속성은 링크를 클릭했을 때 연결될 타겟을 지정한다.

- \_self : 기본값, 현재 윈도우에 링크를 연결한다.
- \_blank : 새로운 윈도우나, 탭에 링크를 연결한다.

```
<!DOCTYPE html>
<html>
  <body>
    <a href="http://www.google.com" target="_blank">나는 새창에</a><br/>
    <a href="http://www.google.com" target="_self">나는 현재창에</a>
  </body>
</html>
```

[jsfiddle](https://jsfiddle.net/jndwe04v/)

## 5. 목록 (List)

목록을 나타내는 태그

## 5.1 ul 순서가 없는 목록 (Unordered List)

- type 속성 값

```
disc : 기본값, 채워진 검정 원
circle : 채워지지 않은 원
square : 채워진 사각형

<ul type="disc|circle|square"></ul>
```

```
<!DOCTYPE html>
<html>
  <body>
    <ul>
      <li>Coffee</li>
      <li>Tea</li>
      <li>Milk</li>
    </ul>

    <ul type="disc">
      <li>Coffee</li>
      <li>Tea</li>
      <li>Milk</li>
    </ul>

    <ul type="square">
      <li>Coffee</li>
      <li>Tea</li>
      <li>Milk</li>
    </ul>

    <ul type="circle">
      <li>Coffee</li>
      <li>Tea</li>
      <li>Milk</li>
    </ul>

    <p>The type attribute is not supported in HTML5. Use CSS instead.</p>
  </body>
</html>
```

[jsfiddle](https://jsfiddle.net/v5h2sxy9/)

## 5.2 ol 순서가 있는 목록 (Ordered List)

- type 속성 값

```
1 : 기본값, 숫자
A : 대문자 알파벳
a : 소문자 알파벳
I : 대문자 로마숫자
i : 소문자 로마숫자

<ol type="1|A|a|I]i"></ol>
```

- start 속성 : 리스트의 시작 값을 지정할 수 있다.
- reversed 속성을 지정하면 순서 값을 거꾸로 표현한다.
- li태그에 value 값을 지정하면 숫자를 명시할 수 있다.

```
<!DOCTYPE html>
<html>
  <body>
    <ol>
      <li>Coffee</li>
      <li>Tea</li>
      <li>Milk</li>
    </ol>

    <ol start="10">
      <li>Coffee</li>
      <li>Tea</li>
      <li>Milk</li>
    </ol>

    <ol type="I">
      <li>Coffee</li>
      <li>Tea</li>
      <li>Milk</li>
    </ol>

    <ol type="i" reversed>
      <li>Coffee</li>
      <li>Tea</li>
      <li>Milk</li>
    </ol>

    <ol>
      <li>Coffee</li>
      <li>Cream</li>
      <li value="5">Tea</li>
      <li>Milk</li>
    </ol>

  </body>
</html>
```

[jsfiddle](https://jsfiddle.net/7djkc8qv/)

## 5.3 중첩 목록

중첩 목록은 네비게이션 메뉴를 만들때 등에 주로 사용된다.
참고 : https://ant.design/docs/react/i18n 좌측 사이드 메뉴

```
<!DOCTYPE html>
<html>
  <body>
    <h2>중첩 목록</h2>
    <ul>
      <li>Coffee</li>
      <li>Tea
        <ol>
          <li>Chamomile</li>
          <li>Lemon Tea</li>
        </ol>
      </li>
      <li>Milk</li>
    </ul>
  </body>
</html>
```

[jsfiddle](https://jsfiddle.net/hg0b2epL/)

## 6 표(Table) tag (https://www.w3schools.com/html/html_tables.asp)

표를 그릴때 사용하는 태그. 예전에는 표의 테두리를 투명하게 하여 홈페이지의 레이아웃 구성을 많이 하였다. 하지만 지금은 div를 많이 이용.

- <table> : 표를 정의하는 태그
- <tr> : 표의 각 행을 정의하는 태그. 테이블의 헤더는 <th> 태그를 이용한다. <th> 태그는 기본적으로 굵은 글씨와 가운데 정렬로 표시된다.
- <td> : 테이블의 데이터나 셀을 정의한다. <td> 태그는 text, images, lists, 다른 table 등 모든 html 엘리먼트를 포함할 수 있다.
- <caption> : 테이블의 캡션을 정의한다.
- <colgroup> : 한개 이상의 컬럼의 서식을 정의한다.
- <col> : colgroup의 각 컬럼에 대한 속성을 정의한다.
- <thead> : 테이블의 헤더 컨텐츠 그룹을 정의한다.
- <tbody> : 테이블의 body 컨텐츠 그룹을 정의한다.
- <tfoot> : 테이블의 footer 컨텐츠 그룹을 정의한다.

```
<table style="width:100%">
  <tr>
    <th>Firstname</th>
    <th>Lastname</th>
    <th>Age</th>
  </tr>
  <tr>
    <td>Jill</td>
    <td>Smith</td>
    <td>50</td>
  </tr>
  <tr>
    <td>Eve</td>
    <td>Jackson</td>
    <td>94</td>
  </tr>
</table>
```

```
<table style="width:100%">
  <caption>Monthly savings</caption>
  <tr>
    <th>Month</th>
    <th>Savings</th>
  </tr>
  <tr>
    <td>January</td>
    <td>$100</td>
  </tr>
  <tr>
    <td>February</td>
    <td>$50</td>
  </tr>
</table>
```

[jsfiddle](https://jsfiddle.net/xvjsu2zf/)

## 6.1 Table 태그의 속성

- rowspan : 행 병합
- colspan : 셀 병합

```
<table style="width:100%">
  <tr>
    <th>Name</th>
    <th colspan="2">Telephone</th>
  </tr>
  <tr>
    <td>Bill Gates</td>
    <td>55577854</td>
    <td>55577855</td>
  </tr>
</table>
```

```
<table style="width:100%">
  <tr>
    <th>Name:</th>
    <td>Bill Gates</td>
  </tr>
  <tr>
    <th rowspan="2">Telephone:</th>
    <td>55577854</td>
  </tr>
  <tr>
    <td>55577855</td>
  </tr>
</table>
```

[jsfiddle](https://jsfiddle.net/o8vyhamb/)
