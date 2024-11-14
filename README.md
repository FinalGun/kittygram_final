![example branch parameter](https://github.com/github/docs/actions/workflows/main.yml/badge.svg?branch=main)


#  kittygram_final

## Использованные технологии

- Django: Основной фреймворк для создания веб-приложений. [Документация Django](https://www.djangoproject.com/)
- Django REST Framework: Библиотека для создания RESTful API на Django. [Документация DRF](https://www.django-rest-framework.org/)
- Pillow: Библиотека для обработки изображений. [Документация Pillow](https://pillow.readthedocs.io/en/stable/)
- Junicorn: [Документация](https://docs.gunicorn.org/en/stable/settings.html)
- Docker: Платформа контейнеризации [Документация](https://docs.docker.com/)

## Необходимые переменные для файла .env:

- POSTGRES_USER
- POSTGRES_PASSWORD
- POSTGRES_DB
- DB_HOST
- DB_PORT
- SECRET_KEY
- HOST
- DNS

## Установка

Перейти в директорию с файлом docker-compose.production.yml и развернуть контейнеры:
```
    docker compose -f docker-compose.production.yml up -d
```    
Установить миграции:    
```
    docker compose -f docker-compose.production.yml exec backend python manage.py migrate
```
Собрать статику:
```
    docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic
```
Копировать статику:    
```
    docker compose -f docker-compose.production.yml exec backend cp -r /app/collected_static/. /backend_static/static/
```
### Разработчик.
[FinalGun](https://github.com/FinalGun)
