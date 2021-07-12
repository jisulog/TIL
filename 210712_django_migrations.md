# 문제

- Django의 마이그레이션은 `모델`에 생긴 변화를 자동으로 반영하는 방식
- 하지만 너무 많아 불필요한 문제나 부작용이 나타날 수 있음



---



# 해결방안

- `마이그레이션 파일은 모두 지우고, 데이터베이스 데이터는 유지`하는 방법



##### 1. 현재 반영 안 된 마이그레이션이 없는지 확인한다.

```bash
python manage.py makemigrations
```

* 만약 추가로 마이그레이션 파일이 만들어진다면,

```bash
python manage.py migrate
```



##### 2. 프로젝트 앱 마이그레이션 히스토리 삭제

```bash
python manage.py showmigrations
```



##### 3. 앱의 마이그레이션 파일을 초기화

```bash
python manage.py migrate --fake 프로젝트_앱 zero
```



##### 4. 마이그레이션 파일 삭제

- 앱의 마이그레이션 디렉토리 안에 `__init__.py` 파일을 빼고 모두 삭제
- `python manage.py showmigrations`으로 확인



##### 5. 초기 마이그레이션 파일 생성

```bash
python manage.py makemigrations
```

- 최초 마이그레이션 파일 `0001_initial.py`이 생성



##### 6. 페이크 마이그레이션

- 데이터베이스 테이블이 이미 존재하기 때문에 초기 마이그레이션 파일을 적용할 수 없음
- 마치 마이그레이션한 것 처럼 명령

```bash
python manage.py migrate --fake-initial
```

- `python manage.py showmigrations`으로 확인



---



# 참고

[참고](https://wikidocs.net/9926)

