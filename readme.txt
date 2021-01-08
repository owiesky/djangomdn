https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/development_environment

directory djangomdn
> python -m venv venv
> venv\Scripts\activate }} masuk ke virtual env venv
> python -m pip install Django }} install django 3.1.5 latest
> python -m django --version }} cek hasil instalasi django
> django-admin startproject perpus }} buat directory perpus beserta boilerplate project django didalamnya
> cd perpus }} pindah directory perpus
> python manage.py runserver }} menjalankan service webserver development di http://127.0.0.1:8000/
> python manage.py startapp catalog }} buat directory catalog beserta boilerplat app django didalamnya
>- register catalog app di settings.py -> 'catalog.apps.CatalogConfig',
>- register database di settings.py -> sqlite3 }} default
>- setting time_zone di settings.py -> prefer UTC
>- setting debug False for production mode
>- urls.py -> setting url }} add path to catalog, create catalog\urls.py, add views.py def-> index
	}} path('', views.index, name='index'),
	}} def index(request):
    		return HttpResponse("Hello, world. You're at the Catalog index.")

>- create models.py
> python manage.py makemigrations catalog		(models to 0001_initial.py) }} cek di folder migrations
> python manage.py sqlmigrate polls 0001		(0001 to sql)
> python manage.py migrate				(sql to db)

>- register model to admin page
>- edit catalog\models.py
	{from .models import Author, Genre, Book, BookInstance, Language
	admin.site.register(Author)}

>- create superuser
> python manage.py createsuperuser


