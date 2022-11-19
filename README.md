<<<<<<< HEAD
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
=======
# Django

### �룄援� -> manage.py �옉�뾽 �떎�뻾
>�빋
>```angular2html
>startapp �빋_�씠由�
>```
>�뜲�씠�꽣踰좎씠�뒪
>```
>migrate
>```
### �봽濡쒖젥�듃/settings.py
>�뼵�뼱, �떆媛�
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f
>```
>LANGUAGE_CODE = 'ko-kr'
>
>TIME_ZONE = 'Asia/Seoul'
>```
<<<<<<< HEAD
>데이터베이스
=======
>�뜲�씠�꽣踰좎씠�뒪
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f
>```angular2html
>INSTALLED_APPS = [
>    'django.contrib.admin',
>    'django.contrib.auth',
>    'django.contrib.contenttypes',
>    'django.contrib.sessions',
>    'django.contrib.messages',
>    'django.contrib.staticfiles',
<<<<<<< HEAD
>    '앱_이름.apps.앱_이름(첫글자 대문자)Config',
>]
>```
>스타일
=======
>    '�빋_�씠由�.apps.�빋_�씠由�(泥リ���옄 ���臾몄옄)Config',
>]
>```
>�뒪����씪
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f
>```angular2html
>STATIC_URL = '/static/'
>STATICFILES_DIRS = [BASE_DIR / 'static']
>```
<<<<<<< HEAD
### 프로젝트/urls.py
=======
### �봽濡쒖젥�듃/urls.py
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f
```angular2html
from django.contrib import admin
from django.urls import include, path

urlpatterns = [
    path('admin/', admin.site.urls),
<<<<<<< HEAD
    path('', include('home.urls')),     # 홈 URL 연결
    path('앱_이름/', include('앱_이름.urls')),   # 앱_이름 URL 연결
]
```
---
### home/urls.py ( 생성 )
=======
    path('', include('home.urls')),     # �솃 URL �뿰寃�
    path('�빋_�씠由�/', include('�빋_�씠由�.urls')),   # �빋_�씠由� URL �뿰寃�
]
```
---
### home/urls.py ( �깮�꽦 )
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f
```angular2html
from django.urls import path
from . import views

urlpatterns = [
<<<<<<< HEAD
    path('', views.HomeView.as_view(), name='home'),    # 홈 VIEW 연결
=======
    path('', views.HomeView.as_view(), name='home'),    # �솃 VIEW �뿰寃�
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f
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

<<<<<<< HEAD
### templates/home.html ( 생성 )

---

### 앱_이름/urls.py ( 생성 )
=======
### templates/home.html ( �깮�꽦 )

---

### �빋_�씠由�/urls.py ( �깮�꽦 )
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f
```angular2html
from django.urls import path
from . import views

urlpatterns = [
<<<<<<< HEAD
    path('HTML_이름/', views.HTML_이름View.as_view(), name='HTML_이름'),    # 앱_이름 VIEW 연결, name='별칭'
]
```

### 앱_이름/views.py
=======
    path('HTML_�씠由�/', views.HTML_�씠由꼁iew.as_view(), name='HTML_�씠由�'),    # �빋_�씠由� VIEW �뿰寃�, name='蹂꾩묶'
]
```

### �빋_�씠由�/views.py
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f
```angular2html
from django.shortcuts import render
from django.views import View

<<<<<<< HEAD
class HTML_이름View(View):
    def get(self, request):
        return render(request, '앱_이름/HTML_이름.html')
=======
class HTML_�씠由꼁iew(View):
    def get(self, request):
        return render(request, '�빋_�씠由�/HTML_�씠由�.html')
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f

    def post(self, request):
        pass
```

<<<<<<< HEAD
### templates/layout/base.html ( 생성 )
=======
### templates/layout/base.html ( �깮�꽦 )
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f
```angular2html
<!DOCTYPE html>
<html lang="ko">
<head>
    {% load static %}
    <meta charset="UTF-8">
<<<<<<< HEAD
    <link rel="stylesheet" href="{% static '/css/스타일_이름.css' %}">
                            ...
    
    <title>{% block title %}제목{% endblock %}</title>
    
    <style>
        {% block style %}
            CSS 코드
=======
    <link rel="stylesheet" href="{% static '/css/�뒪����씪_�씠由�.css' %}">
                            ...
    
    <title>{% block title %}�젣紐�{% endblock %}</title>
    
    <style>
        {% block style %}
            CSS 肄붾뱶
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f
        {% endblock %}
    </style>
    
</head>

<body>

<<<<<<< HEAD
    {% include 'layout/header.html' %}   <!-- 헤더 불러오기 -->
    
    {% block 레이아웃_태그 %}
        HTML 코드
    {% endblock %}
    
    {% include 'layout/footer.html' %}   <!-- 푸터 불러오기 -->
    
    {% block script %}
        자바스크립트 코드
=======
    {% include 'layout/header.html' %}   <!-- �뿤�뜑 遺덈윭�삤湲� -->
    
    {% block �젅�씠�븘�썐_�깭洹� %}
        HTML 肄붾뱶
    {% endblock %}
    
    {% include 'layout/footer.html' %}   <!-- �뫖�꽣 遺덈윭�삤湲� -->
    
    {% block script %}
        �옄諛붿뒪�겕由쏀듃 肄붾뱶
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f
    {% endblock %}

</body>
</html>
```

<<<<<<< HEAD
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
=======
### templates/layout/header.html ( �깮�꽦 )
```angular2html
<header>
    HTML 肄붾뱶
</header>
```

### templates/layout/footer.html ( �깮�꽦 )
```angular2html
<footer>
    HTML 肄붾뱶
</footer>
```

### templates/�빋_�씠由�/HTML_�씠由�.html ( �깮�꽦 )
```angular2html
{% extends 'layout/base.html' %}

{% block title %}�젣紐�{% endblock %}

{% block style %}
<style>
    CSS 肄붾뱶
</style>    
{% endblock %}

{% block �젅�씠�븘�썐_�깭洹� %}
    HTML 肄붾뱶
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f
{% endblock %}

{% block script %}
<script>
<<<<<<< HEAD
    자바스크립트 코드
=======
    �옄諛붿뒪�겕由쏀듃 肄붾뱶
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f
</script>
{% endblock %}
```

<<<<<<< HEAD
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
=======
### �빋_�씠由�/models.py
```
from django.db import models

class �뀒�씠釉�(models.Model):
    (�냽�꽦)蹂��닔1 = models.�냽�꽦_����엯(�샃�뀡)
    (�냽�꽦)蹂��닔2 = models.�냽�꽦_����엯(�샃�뀡)
            ...
    (�냽�꽦)蹂��닔n = models.�냽�꽦_����엯(�샃�뀡)

    class Meta:
       db_table = 'db_�뀒�씠釉�'    # �뜲�씠�꽣踰좎씠�뒪 �뀒�씠釉� �깮�꽦
       ordering = ['(�냽�꽦)蹂��닔'/'-(�냽�꽦)蹂��닔']     # �젙�젹 �삤由꾩감�닚/�궡由쇱감�닚         

    # def __str__(self):      # (�겢�옒�뒪)蹂��닔 -> 臾몄옄�뿴
    #     return f'{self.(�냽�꽦)蹂��닔1} ... {self.(�냽�꽦)蹂��닔n}'
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f
```
