### 도구 -> manage.py 작업 실행
>앱
>```angular2html
>startapp 앱_이름
>```
>데이터베이스
>```
>migrate
>```
### 프로젝트/settings.py
>언어, 시간
>```
>LANGUAGE_CODE = 'ko-kr'
>
>TIME_ZONE = 'Asia/Seoul'
>```
>데이터베이스
>```angular2html
>INSTALLED_APPS = [
>    'django.contrib.admin',
>    'django.contrib.auth',
>    'django.contrib.contenttypes',
>    'django.contrib.sessions',
>    'django.contrib.messages',
>    'django.contrib.staticfiles',
>    '앱_이름.apps.앱_이름(첫글자 대문자)Config',
>]
>```
>스타일
>```angular2html
>STATIC_URL = '/static/'
>STATICFILES_DIRS = [BASE_DIR / 'static']
>```
### 프로젝트/urls.py
```angular2html
from django.contrib import admin
from django.urls import include, path

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('home.urls')),     # 홈 URL 연결
    path('앱_이름/', include('앱_이름.urls')),   # 앱_이름 URL 연결
]
```
---
### home/urls.py ( 생성 )
```angular2html
from django.urls import path
from . import views

urlpatterns = [
    path('', views.HomeView.as_view(), name='home'),    # 홈 VIEW 연결
]
```

### home/views.py
```angular2html
from django.shortcuts import render
from django.views import View

class HomeView(View):
    def get(self, request):
        return render(request, 'home.html')

    def post(self, request):
        pass
```

### templates/home.html ( 생성 )

---

### 앱_이름/urls.py ( 생성 )
```angular2html
from django.urls import path
from . import views

urlpatterns = [
    path('HTML_이름/', views.HTML_이름View.as_view(), name='HTML_이름'),    # 앱_이름 VIEW 연결, name='별칭'
]
```

### 앱_이름/views.py
```angular2html
from django.shortcuts import render
from django.views import View

class HTML_이름View(View):
    def get(self, request):
        return render(request, '앱_이름/HTML_이름.html')

    def post(self, request):
        pass
```

### templates/layout/base.html ( 생성 )
```angular2html
<!DOCTYPE html>
<html lang="ko">
<head>
    {% load static %}
    <meta charset="UTF-8">
    <link rel="stylesheet" href="{% static '/css/스타일_이름.css' %}">
                            ...
    
    <title>{% block title %}제목{% endblock %}</title>
    
    <style>
        {% block style %}
            CSS 코드
        {% endblock %}
    </style>
    
</head>

<body>

    {% include 'layout/header.html' %}   <!-- 헤더 불러오기 -->
    
    {% block 레이아웃_태그 %}
        HTML 코드
    {% endblock %}
    
    {% include 'layout/footer.html' %}   <!-- 푸터 불러오기 -->
    
    {% block script %}
        자바스크립트 코드
    {% endblock %}

</body>
</html>
```

### templates/layout/header.html ( 생성 )
```angular2html
<header>
    HTML 코드
</header>
```

### templates/layout/footer.html ( 생성 )
```angular2html
<footer>
    HTML 코드
</footer>
```

### templates/앱_이름/HTML_이름.html ( 생성 )
```angular2html
{% extends 'layout/base.html' %}

{% block title %}제목{% endblock %}

{% block style %}
<style>
    CSS 코드
</style>    
{% endblock %}

{% block 레이아웃_태그 %}
    HTML 코드
{% endblock %}

{% block script %}
<script>
    자바스크립트 코드
</script>
{% endblock %}
```

### 앱_이름/models.py
```
from django.db import models

class 테이블(models.Model):
    (속성)변수1 = models.속성_타입(옵션)
    (속성)변수2 = models.속성_타입(옵션)
            ...
    (속성)변수n = models.속성_타입(옵션)

    class Meta:
       db_table = 'db_테이블'    # 데이터베이스 테이블 생성
       ordering = ['(속성)변수'/'-(속성)변수']     # 정렬 오름차순/내림차순         

    # def __str__(self):      # (클래스)변수 -> 문자열
    #     return f'{self.(속성)변수1} ... {self.(속성)변수n}'
```
