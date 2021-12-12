# 문제

```html
unable to import module 'mariadb' no module named 'module_name'
```



---



# 원인

```python
import mariaDB
```

[참고](https://mariadb.com/ko/resources/blog/how-to-connect-python-programs-to-mariadb/)

- AWS Lambda에서 `mariaDB`를 읽지 못함
- 예상: 레이어에 추가한 mariaDB를 읽지 못함



---



# 해결방법

```python
import mysql.connector
```

[참고](https://dev.mysql.com/doc/connector-python/en/connector-python-example-connecting.html)

- 대신 `mysql`을 레이어에 추가함

