# 문제

```bash
ImportError: attempted relative import with no known parent package
```



---



# 원인

- 파이썬의 인터프리터는 `상대경로로 import`할 때 `모듈 위치를 __name__`속성에 의해 결정함

- 터미널에서 python파일을 실행시키면 `__name__== __main__`이기 때문에 출발점이 되는 `모듈의 위치를 알 수 없음`

- 즉, `암묵적인 상대경로 import가 불가능`



---



# 해결방법

- `main 모듈에서는 절대경로`를, `하위 모듈에서는 상대경로`를 사용하자



---



# 참고

[참고](https://blog.potados.com/dev/python3-import/)

