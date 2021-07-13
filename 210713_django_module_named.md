# 문제

```bash
No module named 'polls.apps.PollsConfigdjango'
```



---



# 원인

- INSTALLED_APPS에 `모듈 이름을 잘못 추가함`



---



# 해결방안

- settings.py의 `INSTALLED_APPS`에 모듈 이름을 알맞게 추가해줌

```python
INSTALLED_APPS = [
    ...
    'polls.apps.PollsConfig',  # 0
    'PollsConfig', # x
]
```

