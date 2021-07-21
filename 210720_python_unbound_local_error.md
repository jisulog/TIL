# 문제

```powershell
UnboundLocalError: local variable 'msg' referenced before assignment
```



---



# 원인

- `local -> nonlocal -> global` 순으로 변수를 확인
-  하지만 `읽기는 가능하지만 쓰기는 불가능`
- local scope안에 msg 변수를 찾을 수 없음

---



# 해결방법

```python
# 1. global scope
def outer_send_message(msg):
    # 2. nonlocal scope
    def inner_send_message():
        # 3. local scope
        ### nonlocal 명시 추가
        nonlocal msg
        if 'nonlocal' in msg:
            msg = msg.replace('nonlocal', 'local')
        return msg

    return inner_send_message()

# nonlocal scope
print(outer_send_message("nonlocal scope!"))
```



---



# 참고

[참고](https://velog.io/@jaebig/Python-%ED%81%B4%EB%A1%9C%EC%A0%80-%EC%9D%B4%ED%95%B4%ED%95%98%EA%B8%B0)

