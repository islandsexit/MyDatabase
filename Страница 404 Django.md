Добавляем страницу [[404]] в [[Django]] 


## Views.py
	Нужно добавить метод вызываемый при обработке ошибки 404 
```python
def page_not_found(request, exception):
    content = loader.render_to_string('./upload_app/custom_40x.html', {}, request)
    return HttpResponseNotFound(content)
```


### Urls.py (Главный модуль)
	И добавить этот метод в файл путей
```python
from django.contrib import admin
from django.urls import path
from django.urls import include, path
from django.conf import settings
from django.conf.urls.static import static

urlpatterns = [

    # path('admin/', admin.site.urls),
    path('', include('upload_app.urls')),

  
  

] + static(settings.MEDIA_URL, document_root=settings.MEDIA_ROOT) + static(settings.STATIC_URL, document_root=settings.STATIC_ROOT)

  

handler404 = "upload_app.views.page_not_found" ///Этот моментик
```