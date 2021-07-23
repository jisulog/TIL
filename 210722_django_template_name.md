# 문제

```html
ImproperlyConfigured at /
TemplateResponseMixin requires either a definition of 'template_name' or an implementation of 'get_template_names()'
```



---



# 원인

- TemplateView를 `template_name 없이 정의`함



---



# 해결방법

- views.py에 template_name을 정의

```python
class HomeView(TemplateView):
    template_name = 'home.html' # 추가

    def get_context_data(self, **kwargs):
        context = super().get_context_data(**kwargs)
        context['app_list'] = ['polls', 'books']
        return context
```





---



# 참고

[참고](https://github.com/Tivix/django-rest-auth/issues/20)