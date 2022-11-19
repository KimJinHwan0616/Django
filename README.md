<<<<<<< HEAD
### ���� -> manage.py �۾� ����
>��
>```angular2html
>startapp ��_�̸�
>```
>�����ͺ��̽�
>```
>migrate
>```
### ������Ʈ/settings.py
>���, �ð�
=======
# Django

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
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f
>```
>LANGUAGE_CODE = 'ko-kr'
>
>TIME_ZONE = 'Asia/Seoul'
>```
<<<<<<< HEAD
>�����ͺ��̽�
=======
>데이터베이스
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
>    '��_�̸�.apps.��_�̸�(ù���� �빮��)Config',
>]
>```
>��Ÿ��
=======
>    '앱_이름.apps.앱_이름(첫글자 대문자)Config',
>]
>```
>스타일
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f
>```angular2html
>STATIC_URL = '/static/'
>STATICFILES_DIRS = [BASE_DIR / 'static']
>```
<<<<<<< HEAD
### ������Ʈ/urls.py
=======
### 프로젝트/urls.py
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f
```angular2html
from django.contrib import admin
from django.urls import include, path

urlpatterns = [
    path('admin/', admin.site.urls),
<<<<<<< HEAD
    path('', include('home.urls')),     # Ȩ URL ����
    path('��_�̸�/', include('��_�̸�.urls')),   # ��_�̸� URL ����
]
```
---
### home/urls.py ( ���� )
=======
    path('', include('home.urls')),     # 홈 URL 연결
    path('앱_이름/', include('앱_이름.urls')),   # 앱_이름 URL 연결
]
```
---
### home/urls.py ( 생성 )
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f
```angular2html
from django.urls import path
from . import views

urlpatterns = [
<<<<<<< HEAD
    path('', views.HomeView.as_view(), name='home'),    # Ȩ VIEW ����
=======
    path('', views.HomeView.as_view(), name='home'),    # 홈 VIEW 연결
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
### templates/home.html ( ���� )

---

### ��_�̸�/urls.py ( ���� )
=======
### templates/home.html ( 생성 )

---

### 앱_이름/urls.py ( 생성 )
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f
```angular2html
from django.urls import path
from . import views

urlpatterns = [
<<<<<<< HEAD
    path('HTML_�̸�/', views.HTML_�̸�View.as_view(), name='HTML_�̸�'),    # ��_�̸� VIEW ����, name='��Ī'
]
```

### ��_�̸�/views.py
=======
    path('HTML_이름/', views.HTML_이름View.as_view(), name='HTML_이름'),    # 앱_이름 VIEW 연결, name='별칭'
]
```

### 앱_이름/views.py
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f
```angular2html
from django.shortcuts import render
from django.views import View

<<<<<<< HEAD
class HTML_�̸�View(View):
    def get(self, request):
        return render(request, '��_�̸�/HTML_�̸�.html')
=======
class HTML_이름View(View):
    def get(self, request):
        return render(request, '앱_이름/HTML_이름.html')
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f

    def post(self, request):
        pass
```

<<<<<<< HEAD
### templates/layout/base.html ( ���� )
=======
### templates/layout/base.html ( 생성 )
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f
```angular2html
<!DOCTYPE html>
<html lang="ko">
<head>
    {% load static %}
    <meta charset="UTF-8">
<<<<<<< HEAD
    <link rel="stylesheet" href="{% static '/css/��Ÿ��_�̸�.css' %}">
                            ...
    
    <title>{% block title %}����{% endblock %}</title>
    
    <style>
        {% block style %}
            CSS �ڵ�
=======
    <link rel="stylesheet" href="{% static '/css/스타일_이름.css' %}">
                            ...
    
    <title>{% block title %}제목{% endblock %}</title>
    
    <style>
        {% block style %}
            CSS 코드
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f
        {% endblock %}
    </style>
    
</head>

<body>

<<<<<<< HEAD
    {% include 'layout/header.html' %}   <!-- ��� �ҷ����� -->
    
    {% block ���̾ƿ�_�±� %}
        HTML �ڵ�
    {% endblock %}
    
    {% include 'layout/footer.html' %}   <!-- Ǫ�� �ҷ����� -->
    
    {% block script %}
        �ڹٽ�ũ��Ʈ �ڵ�
=======
    {% include 'layout/header.html' %}   <!-- 헤더 불러오기 -->
    
    {% block 레이아웃_태그 %}
        HTML 코드
    {% endblock %}
    
    {% include 'layout/footer.html' %}   <!-- 푸터 불러오기 -->
    
    {% block script %}
        자바스크립트 코드
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f
    {% endblock %}

</body>
</html>
```

<<<<<<< HEAD
### templates/layout/header.html ( ���� )
```angular2html
<header>
    HTML �ڵ�
</header>
```

### templates/layout/footer.html ( ���� )
```angular2html
<footer>
    HTML �ڵ�
</footer>
```

### templates/��_�̸�/HTML_�̸�.html ( ���� )
```angular2html
{% extends 'layout/base.html' %}

{% block title %}����{% endblock %}

{% block style %}
<style>
    CSS �ڵ�
</style>    
{% endblock %}

{% block ���̾ƿ�_�±� %}
    HTML �ڵ�
=======
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
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f
{% endblock %}

{% block script %}
<script>
<<<<<<< HEAD
    �ڹٽ�ũ��Ʈ �ڵ�
=======
    자바스크립트 코드
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f
</script>
{% endblock %}
```

<<<<<<< HEAD
### ��_�̸�/models.py
```
from django.db import models

class ���̺�(models.Model):
    (�Ӽ�)����1 = models.�Ӽ�_Ÿ��(�ɼ�)
    (�Ӽ�)����2 = models.�Ӽ�_Ÿ��(�ɼ�)
            ...
    (�Ӽ�)����n = models.�Ӽ�_Ÿ��(�ɼ�)

    class Meta:
       db_table = 'db_���̺�'    # �����ͺ��̽� ���̺� ����
       ordering = ['(�Ӽ�)����'/'-(�Ӽ�)����']     # ���� ��������/��������         

    # def __str__(self):      # (Ŭ����)���� -> ���ڿ�
    #     return f'{self.(�Ӽ�)����1} ... {self.(�Ӽ�)����n}'
=======
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
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f
```
