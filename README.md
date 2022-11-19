<<<<<<< HEAD
### µµ±¸ -> manage.py ÀÛ¾÷ ½ÇÇà
>¾Û
>```angular2html
>startapp ¾Û_ÀÌ¸§
>```
>µ¥ÀÌÅÍº£ÀÌ½º
>```
>migrate
>```
### ÇÁ·ÎÁ§Æ®/settings.py
>¾ğ¾î, ½Ã°£
=======
# Django

### ë„êµ¬ -> manage.py ì‘ì—… ì‹¤í–‰
>ì•±
>```angular2html
>startapp ì•±_ì´ë¦„
>```
>ë°ì´í„°ë² ì´ìŠ¤
>```
>migrate
>```
### í”„ë¡œì íŠ¸/settings.py
>ì–¸ì–´, ì‹œê°„
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f
>```
>LANGUAGE_CODE = 'ko-kr'
>
>TIME_ZONE = 'Asia/Seoul'
>```
<<<<<<< HEAD
>µ¥ÀÌÅÍº£ÀÌ½º
=======
>ë°ì´í„°ë² ì´ìŠ¤
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
>    '¾Û_ÀÌ¸§.apps.¾Û_ÀÌ¸§(Ã¹±ÛÀÚ ´ë¹®ÀÚ)Config',
>]
>```
>½ºÅ¸ÀÏ
=======
>    'ì•±_ì´ë¦„.apps.ì•±_ì´ë¦„(ì²«ê¸€ì ëŒ€ë¬¸ì)Config',
>]
>```
>ìŠ¤íƒ€ì¼
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f
>```angular2html
>STATIC_URL = '/static/'
>STATICFILES_DIRS = [BASE_DIR / 'static']
>```
<<<<<<< HEAD
### ÇÁ·ÎÁ§Æ®/urls.py
=======
### í”„ë¡œì íŠ¸/urls.py
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f
```angular2html
from django.contrib import admin
from django.urls import include, path

urlpatterns = [
    path('admin/', admin.site.urls),
<<<<<<< HEAD
    path('', include('home.urls')),     # È¨ URL ¿¬°á
    path('¾Û_ÀÌ¸§/', include('¾Û_ÀÌ¸§.urls')),   # ¾Û_ÀÌ¸§ URL ¿¬°á
]
```
---
### home/urls.py ( »ı¼º )
=======
    path('', include('home.urls')),     # í™ˆ URL ì—°ê²°
    path('ì•±_ì´ë¦„/', include('ì•±_ì´ë¦„.urls')),   # ì•±_ì´ë¦„ URL ì—°ê²°
]
```
---
### home/urls.py ( ìƒì„± )
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f
```angular2html
from django.urls import path
from . import views

urlpatterns = [
<<<<<<< HEAD
    path('', views.HomeView.as_view(), name='home'),    # È¨ VIEW ¿¬°á
=======
    path('', views.HomeView.as_view(), name='home'),    # í™ˆ VIEW ì—°ê²°
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
### templates/home.html ( »ı¼º )

---

### ¾Û_ÀÌ¸§/urls.py ( »ı¼º )
=======
### templates/home.html ( ìƒì„± )

---

### ì•±_ì´ë¦„/urls.py ( ìƒì„± )
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f
```angular2html
from django.urls import path
from . import views

urlpatterns = [
<<<<<<< HEAD
    path('HTML_ÀÌ¸§/', views.HTML_ÀÌ¸§View.as_view(), name='HTML_ÀÌ¸§'),    # ¾Û_ÀÌ¸§ VIEW ¿¬°á, name='º°Äª'
]
```

### ¾Û_ÀÌ¸§/views.py
=======
    path('HTML_ì´ë¦„/', views.HTML_ì´ë¦„View.as_view(), name='HTML_ì´ë¦„'),    # ì•±_ì´ë¦„ VIEW ì—°ê²°, name='ë³„ì¹­'
]
```

### ì•±_ì´ë¦„/views.py
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f
```angular2html
from django.shortcuts import render
from django.views import View

<<<<<<< HEAD
class HTML_ÀÌ¸§View(View):
    def get(self, request):
        return render(request, '¾Û_ÀÌ¸§/HTML_ÀÌ¸§.html')
=======
class HTML_ì´ë¦„View(View):
    def get(self, request):
        return render(request, 'ì•±_ì´ë¦„/HTML_ì´ë¦„.html')
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f

    def post(self, request):
        pass
```

<<<<<<< HEAD
### templates/layout/base.html ( »ı¼º )
=======
### templates/layout/base.html ( ìƒì„± )
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f
```angular2html
<!DOCTYPE html>
<html lang="ko">
<head>
    {% load static %}
    <meta charset="UTF-8">
<<<<<<< HEAD
    <link rel="stylesheet" href="{% static '/css/½ºÅ¸ÀÏ_ÀÌ¸§.css' %}">
                            ...
    
    <title>{% block title %}Á¦¸ñ{% endblock %}</title>
    
    <style>
        {% block style %}
            CSS ÄÚµå
=======
    <link rel="stylesheet" href="{% static '/css/ìŠ¤íƒ€ì¼_ì´ë¦„.css' %}">
                            ...
    
    <title>{% block title %}ì œëª©{% endblock %}</title>
    
    <style>
        {% block style %}
            CSS ì½”ë“œ
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f
        {% endblock %}
    </style>
    
</head>

<body>

<<<<<<< HEAD
    {% include 'layout/header.html' %}   <!-- Çì´õ ºÒ·¯¿À±â -->
    
    {% block ·¹ÀÌ¾Æ¿ô_ÅÂ±× %}
        HTML ÄÚµå
    {% endblock %}
    
    {% include 'layout/footer.html' %}   <!-- ÇªÅÍ ºÒ·¯¿À±â -->
    
    {% block script %}
        ÀÚ¹Ù½ºÅ©¸³Æ® ÄÚµå
=======
    {% include 'layout/header.html' %}   <!-- í—¤ë” ë¶ˆëŸ¬ì˜¤ê¸° -->
    
    {% block ë ˆì´ì•„ì›ƒ_íƒœê·¸ %}
        HTML ì½”ë“œ
    {% endblock %}
    
    {% include 'layout/footer.html' %}   <!-- í‘¸í„° ë¶ˆëŸ¬ì˜¤ê¸° -->
    
    {% block script %}
        ìë°”ìŠ¤í¬ë¦½íŠ¸ ì½”ë“œ
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f
    {% endblock %}

</body>
</html>
```

<<<<<<< HEAD
### templates/layout/header.html ( »ı¼º )
```angular2html
<header>
    HTML ÄÚµå
</header>
```

### templates/layout/footer.html ( »ı¼º )
```angular2html
<footer>
    HTML ÄÚµå
</footer>
```

### templates/¾Û_ÀÌ¸§/HTML_ÀÌ¸§.html ( »ı¼º )
```angular2html
{% extends 'layout/base.html' %}

{% block title %}Á¦¸ñ{% endblock %}

{% block style %}
<style>
    CSS ÄÚµå
</style>    
{% endblock %}

{% block ·¹ÀÌ¾Æ¿ô_ÅÂ±× %}
    HTML ÄÚµå
=======
### templates/layout/header.html ( ìƒì„± )
```angular2html
<header>
    HTML ì½”ë“œ
</header>
```

### templates/layout/footer.html ( ìƒì„± )
```angular2html
<footer>
    HTML ì½”ë“œ
</footer>
```

### templates/ì•±_ì´ë¦„/HTML_ì´ë¦„.html ( ìƒì„± )
```angular2html
{% extends 'layout/base.html' %}

{% block title %}ì œëª©{% endblock %}

{% block style %}
<style>
    CSS ì½”ë“œ
</style>    
{% endblock %}

{% block ë ˆì´ì•„ì›ƒ_íƒœê·¸ %}
    HTML ì½”ë“œ
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f
{% endblock %}

{% block script %}
<script>
<<<<<<< HEAD
    ÀÚ¹Ù½ºÅ©¸³Æ® ÄÚµå
=======
    ìë°”ìŠ¤í¬ë¦½íŠ¸ ì½”ë“œ
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f
</script>
{% endblock %}
```

<<<<<<< HEAD
### ¾Û_ÀÌ¸§/models.py
```
from django.db import models

class Å×ÀÌºí(models.Model):
    (¼Ó¼º)º¯¼ö1 = models.¼Ó¼º_Å¸ÀÔ(¿É¼Ç)
    (¼Ó¼º)º¯¼ö2 = models.¼Ó¼º_Å¸ÀÔ(¿É¼Ç)
            ...
    (¼Ó¼º)º¯¼ön = models.¼Ó¼º_Å¸ÀÔ(¿É¼Ç)

    class Meta:
       db_table = 'db_Å×ÀÌºí'    # µ¥ÀÌÅÍº£ÀÌ½º Å×ÀÌºí »ı¼º
       ordering = ['(¼Ó¼º)º¯¼ö'/'-(¼Ó¼º)º¯¼ö']     # Á¤·Ä ¿À¸§Â÷¼ø/³»¸²Â÷¼ø         

    # def __str__(self):      # (Å¬·¡½º)º¯¼ö -> ¹®ÀÚ¿­
    #     return f'{self.(¼Ó¼º)º¯¼ö1} ... {self.(¼Ó¼º)º¯¼ön}'
=======
### ì•±_ì´ë¦„/models.py
```
from django.db import models

class í…Œì´ë¸”(models.Model):
    (ì†ì„±)ë³€ìˆ˜1 = models.ì†ì„±_íƒ€ì…(ì˜µì…˜)
    (ì†ì„±)ë³€ìˆ˜2 = models.ì†ì„±_íƒ€ì…(ì˜µì…˜)
            ...
    (ì†ì„±)ë³€ìˆ˜n = models.ì†ì„±_íƒ€ì…(ì˜µì…˜)

    class Meta:
       db_table = 'db_í…Œì´ë¸”'    # ë°ì´í„°ë² ì´ìŠ¤ í…Œì´ë¸” ìƒì„±
       ordering = ['(ì†ì„±)ë³€ìˆ˜'/'-(ì†ì„±)ë³€ìˆ˜']     # ì •ë ¬ ì˜¤ë¦„ì°¨ìˆœ/ë‚´ë¦¼ì°¨ìˆœ         

    # def __str__(self):      # (í´ë˜ìŠ¤)ë³€ìˆ˜ -> ë¬¸ìì—´
    #     return f'{self.(ì†ì„±)ë³€ìˆ˜1} ... {self.(ì†ì„±)ë³€ìˆ˜n}'
>>>>>>> f0632a745fc786b2bd7ba5a0674e8f47e44fe45f
```
