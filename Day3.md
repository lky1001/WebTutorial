## 8. form 관련 태그들
사용자와 상호작용을 하기 위해 필수적인 요소, 사용자로부터 입력을 받을 수 있는 방법을 제공하며, input, textarea, button 등이 있다.

## 8.1 form 태그
입력을 받을 수 있는 양식(form)을 제공한다. input, textarea, button, submit button 등을 포함할 수 있다.

## 8.1.1 속성

- action : 입력된 내용이 전송될 URL을 지정한다.
- method : http 메소드를 지정한다. get, post 등이 있으며 자세한 내용은 [모질라](https://developer.mozilla.org/ko/docs/Web/HTTP/Methods)

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
