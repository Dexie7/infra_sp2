# api_yamdb


### Для чего этот проект:
Проект **YaMDb** собирает отзывы пользователей на различные произведения (музыка, кино, книги и т.д.).

API проекта YaMDb дает возможность просматривать описания произведений, читать отзывы и комментарии.

После регистрации доступно написание отзывов и выставление оценок для произведений. 
### Технологии:
- Python 3.7
- Django 2.2.16
- Django rest framework 3.12.4
- Djoser 2.1.0
- Docker 20.10.17
- Docker-compose 3.8

### Как запустить проект через Docker:
Запустите docker-compose командой:
```
docker-compose up -d --build
```
Теперь в контейнере web нужно выполнить миграции, создать суперпользователя и собрать статику:
```
docker-compose exec web python manage.py migrate
docker-compose exec web python manage.py createsuperuser
docker-compose exec web python manage.py collectstatic --no-input 
```
Команды для заполнения базы данными (копирование фикстур в запущенный контейнер):
```
/infra_sp2$ cd infra
docker-compose exec web python manage.py dumpdata > fixtures.json
```
