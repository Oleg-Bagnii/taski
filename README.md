# Taski - твой планировщик дел.
## Описание проекта.
Приложение для планирования своих дел. С помощью него вы можете добавлять задачи и менять их статут.
## Стек использованных технологий:
- Python 3.9. 10
- Django 3.2.3
- djangorestframework==3.12.4
- PostgreSQL 13.10
- Docker
- Nginx
## Развертывание проекта через Docker:
1. Установите Docker, используя инструкции с официального сайта.
2. Клонируйте репозиторий с проектом на свой компьютер:
```sh
git clone https://github.com/Oleg-Bagnii/taski.git
```
3. Установить и активировать виртуальное окружение:
```sh
python -m venv venv
source venv/Scripts/activate
```
4. Переименуйте файл ".env.example" в ".env" в корне проекта.
5. Выполните команду сборки docker-compose:
```sh
docker-compose up -d --build
```
6. Выполните миграции:
```sh
docker-compose exec backend python manage.py migrate
```
7. Создайте суперпользователя:
```sh
docker-compose exec backend python manage.py createsuperuser
```
8. Соберите файлы статики:
```sh
docker-compose exec backend python manage.py collectstatic
```
9. Скопируйте файлы статики в /backend_static/static/ backend-контейнера :
```sh
docker compose exec backend cp -r /app/collected_static/. /backend_static/static/
# При выполнении команды на Windows может возникнуть ошибка "The system cannot find the file specified"
# В таком случае выполните команду "cp -r /app/collected_static/. /backend_static/static/"
# через терменал backend-контейнера в десктоп-приложении Docker
```
## Над проектом работал:
Багний Олег
