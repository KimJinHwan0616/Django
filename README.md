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
>```
>LANGUAGE_CODE = 'ko-kr'
>
>TIME_ZONE = 'Asia/Seoul'
>```
>�����ͺ��̽�
>```angular2html
>INSTALLED_APPS = [
>    'django.contrib.admin',
>    'django.contrib.auth',
>    'django.contrib.contenttypes',
>    'django.contrib.sessions',
>    'django.contrib.messages',
>    'django.contrib.staticfiles',
>    '��_�̸�.apps.��_�̸�(ù���� �빮��)Config',
>]
>```
>��Ÿ��
>```angular2html
>STATIC_URL = '/static/'
>STATICFILES_DIRS = [BASE_DIR / 'static']
>```
### ������Ʈ/urls.py
```angular2html
from django.contrib import admin
from django.urls import include, path

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('home.urls')),     # Ȩ URL ����
    path('��_�̸�/', include('��_�̸�.urls')),   # ��_�̸� URL ����
]
```
---
### home/urls.py ( ���� )
```angular2html
from django.urls import path
from . import views

urlpatterns = [
    path('', views.HomeView.as_view(), name='home'),    # Ȩ VIEW ����
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

### templates/home.html ( ���� )

---

### ��_�̸�/urls.py ( ���� )
```angular2html
from django.urls import path
from . import views

urlpatterns = [
    path('HTML_�̸�/', views.HTML_�̸�View.as_view(), name='HTML_�̸�'),    # ��_�̸� VIEW ����, name='��Ī'
]
```

### ��_�̸�/views.py
```angular2html
from django.shortcuts import render
from django.views import View

class HTML_�̸�View(View):
    def get(self, request):
        return render(request, '��_�̸�/HTML_�̸�.html')

    def post(self, request):
        pass
```

### templates/layout/base.html ( ���� )
```angular2html
<!DOCTYPE html>
<html lang="ko">
<head>
    {% load static %}
    <meta charset="UTF-8">
    <link rel="stylesheet" href="{% static '/css/��Ÿ��_�̸�.css' %}">
                            ...
    
    <title>{% block title %}����{% endblock %}</title>
    
    <style>
        {% block style %}
            CSS �ڵ�
        {% endblock %}
    </style>
    
</head>

<body>

    {% include 'layout/header.html' %}   <!-- ��� �ҷ����� -->
    
    {% block ���̾ƿ�_�±� %}
        HTML �ڵ�
    {% endblock %}
    
    {% include 'layout/footer.html' %}   <!-- Ǫ�� �ҷ����� -->
    
    {% block script %}
        �ڹٽ�ũ��Ʈ �ڵ�
    {% endblock %}

</body>
</html>
```

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
{% endblock %}

{% block script %}
<script>
    �ڹٽ�ũ��Ʈ �ڵ�
</script>
{% endblock %}
```

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
```
