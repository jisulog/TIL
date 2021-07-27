# 문제

```html
TemplateSyntaxError at /pybo/
'pybo_filter' is not a registered tag library. Must be one of:
admin_list
admin_modify
admin_urls
cache
i18n
l10n
log
static
tz
```



---



# 원인

- 장고문서를 보면,

  > **Development server won’t automatically restart** after adding the templatetags module, you will need to restart your server before you can use the tags or filters in templates.

- 개발서버가 `자동으로 재시작 되지 않음`



---



# 해결방법

- 서버 종료 후, runserver을 다시 해줌



---



# 참고

[참고](https://stackoverflow.com/questions/44265564/django-registration-of-tag-library-not-working)