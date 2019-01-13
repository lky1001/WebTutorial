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

# 4.1.1 a 태그의 href 속성

href 속성은 이동하고자 하는 파일의 경로(위치)를 설정한다. 경로는 절대경로와 상대결로로 구분된다.

- 절대경로 : 최상위 디렉토리로부터 경로지정한다.
- 상대경로 : 현재 위치로부터 경로를 지정한다.

- 디렉토리(Directory) : 파일이나 다른 디렉토리 그룹을 갖고 있는 파일 시스템 안의 존재물. 폴더 또는 카탈로그라고도 한다.

1. 루트 디렉토리 : 파일 시스템 계층 구조에서 최상위의 디렉토리이다.

- Unix,Linux,OSX : /
- Windows : C:\

2. 작업 디렉토리 : 현재 작업중인 위치를 표현한다

- ./

3. 부모 디렉토리 : 현재 작업 디렉토리의 상위(부모) 디렉토리이다.

- ../
