# 문제

```html
Uncaught SyntaxError: Unexpected token '<'
```



---



# 원인

- 웹팩 오류, `chunkFile을 HTML구문으로 인식함`



---



# 해결방법

- 많은 방법이 있지만 `pakage.json`에 `homepage`를 변경하여 해결함

  ```react
  {
      ...
      "homepage" : ".",
      ...
  }
  ```



---



# 참고

[참고](https://yoon-dumbo.tistory.com/entry/Error-%EC%A0%95%EB%A6%AC-React-Uncaught-SyntaxError-Unexpected-token)