## 앱
+ ### 생성 ( 도구 -> manage.py 작업 실행 )
    ```angular2html
    startapp 앱_이름
    ```
+ ### urls.py
    >``프로젝트/urls.py``
    >```angular2html
    >from django.contrib import admin
    >from django.urls import include, path
    >
    >urlpatterns = [
    >    path('admin/', admin.site.urls),
    >    path('', include('앱_이름.urls')),   # 앱_이름 URL 연결
    >]
    >```
    >``앱_이름/urls.py`` ( 생성 )
    >```angular2html
    >from django.urls import path
    >from . import views
    >
    >urlpatterns = [
    >    path('HTML_이름/', views.HTML_이름View.as_view(), name='HTML_이름'),    # 앱_이름 VIEW 연결, name='별칭'
    >]
    >```
    >
    >---
    >```
    >config/urls.py +  앱_이름/urls.py  =   최종 URL
    >
    >     ''        +   'django/'      =   'django/'
    >  'django/'    +   'python/'      =   'django/python/'
    >```   

+ ### 앱_이름/views.py
    >모델
    >```angular2html
    >from django.shortcuts import render
    >from django.views import View
    >from .models import 테이블
    >
    >class HTML_이름View(View):
    >    def get(self, request):
    >
    >        (테이블)변수 = 테이블.objects.속성
    >
    >        context = {'(테이블)변수' : (테이블)변수}       # (HTML)변수 <- (파이썬)변수
    >        return render(request, '앱_이름/HTML_이름.html', context)
    >
    >    def post(self, request):
    >        pass
    >```
    >URL
    >```
    >from django.shortcuts import render
    >from django.views import View
    >
    >class HTML_이름View(View):
    >    def get(self, request):
    >
    >        # URL(../?파라미터1=값1&파라미터2=값2) 사전 형식 저장 #
    >        form = request.GET.dict()    
    >
    >        # {'파라미터1': '값1', '파라미터2': 값2}   
    >        # form['파라미터1'] = 값1, form['파라미터2'] = 값2
    >
    >        return render(request, '앱_이름/HTML_이름.html')
    >
    >    def post(self, request):
    >        pass
    >```