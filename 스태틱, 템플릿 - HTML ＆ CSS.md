## Static
스타일
+ ### 생성
    >도구 -> manage.py 작업 실행
    >```
    >mkdir static
    >```
    >---
    >``config/settings.py``
    >```angular2html
    >STATIC_URL = '/static/'
    >STATICFILES_DIRS = [
    >    BASE_DIR / 'static',
    >]
    >```
    >---
    >``static/css/스타일_이름.css`` ( 추가 )<br>
    ``static/css/vendor/bs5/스타일_이름.css`` ( 추가 )
  
+ ### 적용
    ``templates/앱_이름/HTML_이름.html``
    ```angular2html
    {% load static %}
    <link rel="stylesheet" href="{% static /css/'스타일_이름.css' %}">
    ```
---

## 템플릿
파이썬 HTML 파일
+ ### 생성
    >도구 -> manage.py 작업 실행
    >```
    >mkdir templates
    >```
    >---
    >``config/settings.py``
    >```
    >TEMPLATES = [
    >    {
    >        'BACKEND': 'django.template.backends.django.DjangoTemplates',
    >        'DIRS': [BASE_DIR / 'templates'],  # <--
    >        'APP_DIRS': True,
    >             ...
    >```
    >---
    >``templates/앱_이름/HTML_이름.html`` ( 생성 )
  
+ ### 상속
    >``templates/layout/base.html`` ( 생성 )
    >```angular2html
    ><!DOCTYPE html>
    ><html lang="ko">
    ><head>
    >    {% load static %}
    >    <meta charset="UTF-8">
    >    <link rel="stylesheet" href="{% static '/css/스타일_이름.css' %}">
    >                            ...
    >    
    >    <title>{% block title %}제목{% endblock %}</title>
    >    
    >    <style>
    >        {% block style %}
    >            CSS 코드
    >        {% endblock %}
    >    </style>
    >    
    ></head>
    >
    ><body>
    >
    >    {% include 'layout/header.html' %}   <!-- 헤더 불러오기 -->
    >    
    >    {% block 레이아웃_태그 %}
    >        HTML 코드
    >    {% endblock %}
    >    
    >    {% include 'layout/footer.html' %}   <!-- 푸터 불러오기 -->
    >    
    >    {% block script %}
    >        자바스크립트 코드
    >    {% endblock %}
    >
    ></body>
    ></html>
    >```
    >``templates/layout/header.html`` ( 생성 )
    >```angular2html
    ><header>
    >    HTML 코드
    ></header>
    >```
    >``templates/layout/footer.html`` ( 생성 )
    >```angular2html
    ><footer>
    >    HTML 코드
    ></footer>
    >```
    >---
    >``templates/앱_이름/HTML_이름.html`` ( 생성 )
    >```angular2html
    >{% extends 'layout/base.html' %}
    >
    >{% block title %}제목{% endblock %}
    >
    >{% block style %}
    ><style>
    >    CSS 코드
    ></style>
    >{% endblock %}
    >
    >{% block 레이아웃_태그 %}
    >    HTML 코드
    >{% endblock %}
    >
    >{% block script %}
    ><script>
    >    자바스크립트 코드
    ></script>
    >{% endblock %}
    >```

+ ### 코드
    >조건문
    >```
    >{% if 조건식1 %}
    >   실행문
    >{% elif 조건식2 %}
    >   실행문
    >    ...
    >{% else %}
    >   실행문
    >{% endif %}
    >```
    >반복문
    >```
    >{% for 변수 in (순서)자료구조 %}
    >    실행문
    >{% endfor %}
    >```
    >변수/객체
    >```
    >{{ 변수 / 객체[.속성] }}
    >```
    >링크
    >```
    ><a href = {% url '별칭' %}></a>
    >```
    >필터?
    >```
    >{{ 변수 | 필터 }}
    >```
    >여러줄 주석
    >```
    >{% comment %} 주석 {% endcomment %}
    >```
    >한줄 주석
    >```
    >{# 주석 #}
    >```

+ ### 보안
    ``templates/앱_이름/HTML_이름.html``
    ```angular2html
    <form>
        {% csrf_token %}
            폼 요소
    </form>
    ```