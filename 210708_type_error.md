# 문제

```
TypeError: get_todos() takes 0 positional arguments but 1 was given
```



---



# 원인

- 함수의 인자가 맞지 않음
- `클래스 내부의 함수(메서드)에 자기 자신을 가리키는 인자`를 사용해야 함
- 파이썬에서 클래스 객체를 생성할 때 만들어지는 객체가 함수(메서드)를 호출할 때 `객체 자기 자신이 인자로 들어가기 때문`



---



# 해결방법

```python
def get_todos() # x
def get_todos(self) # o
```



`클래스 안의 정의된 함수에 self`를 작성하자





# 참고

[참고](https://stackoverflow.com/questions/43839536/typeerror-generatecode-takes-0-positional-arguments-but-1-was-given)

