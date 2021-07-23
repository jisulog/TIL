# 문제

```html
NoReverseMatch at /polls/ 
'polls' is not a registered namespace
```

- Debug를 보면,

```html
<li><a href="{% url 'polls:detail' question.id %}">{{ question.question_text }}</a></li>
```

- 위 부분에 error가 생겼다고 함



---



# 원인

1. 'polls'를 `urls.py`에 `namespace를 등록하지 않음`

2. 애플리케이션인 `polls `에 `polls/urls.py` 안 만들어줌



---



# 해결방안

- 두가지를 모두 해결해줌



> 1. 프로젝트 밑에 urls.py: `mysitr/urls`

```python
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('polls/', include('polls.urls')), # include('애플리케이션/urls')
]
```



---



> 2. 애플리케이션 밑에 urls.py: `polls/urls`

```python
from . import views
from django.urls import path

app_name = 'polls' # app_name이 namespace 역할

urlpatterns = [
    # ex: /polls/
    path('', views.index, name='index'),
    # ex: /polls/5/
    path('<int:question_id>/', views.detail, name='detail'),
    # ex: /polls/5/results/
    path('<int:question_id>/results/', views.results, name='results'),
    # ex: /polls/5/vote/
    path('<int:question_id>/vote/', views.vote, name='vote'),
]
```

