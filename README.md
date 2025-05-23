# Образовательная платформа

Проект представляет собой API для образовательной платформы, где пользователи могут создавать и проходить курсы.

## Технологии

- Python 3.12
- Django 5.1
- Django REST Framework
- PostgreSQL
- Docker
- JWT Authentication

## Требования


- Docker
- Docker Compose

## Установка и запуск

1. Клонируйте репозиторий:
```bash
git clone <url-репозитория>
cd <название-директории>
```

2. Создайте файл `.env` в корневой директории проекта со следующими переменными:
```
SECRET_KEY='ваш-секретный-ключ'
DEBUG=True

POSTGRES_DB='rom'
POSTGRES_USER='postgres'
POSTGRES_PASSWORD='12345'
POSTGRES_HOST='db'
POSTGRES_PORT='5432'

TIME_ZONE='Europe/Moscow'
```

3. Запустите проект с помощью Docker Compose:
```bash
docker-compose up --build
```

После запуска проект будет доступен по адресу: http://localhost:8000

## API Endpoints

### Аутентификация
- `POST /api/token/` - получение JWT токенов
- `POST /api/token/refresh/` - обновление access токена
- `POST /api/token/verify/` - проверка токена

### Курсы
- `GET /courses/` - список курсов
- `POST /courses/` - создание курса
- `GET /courses/{id}/` - детали курса
- `PUT /courses/{id}/` - обновление курса
- `DELETE /courses/{id}/` - удаление курса
- `POST /courses/{id}/subscribe` - подписка на курс

### Уроки
- `GET /lessons/` - список уроков
- `POST /lessons/` - создание урока
- `GET /lessons/{id}/` - детали урока
- `PUT /lessons/{id}/` - обновление урока
- `DELETE /lessons/{id}/` - удаление урока

### Пользователи
- `GET /users/` - список пользователей
- `POST /users/` - регистрация пользователя
- `GET /users/{id}/` - профиль пользователя
- `PUT /users/{id}/` - обновление профиля
- `DELETE /users/{id}/` - удаление пользователя

## Документация API

- Swagger UI: http://localhost:8000/swagger/
- ReDoc: http://localhost:8000/redoc/

## Разработка

1. Создайте виртуальное окружение:
```bash
python -m venv venv
source venv/bin/activate  # для Linux/Mac
venv\Scripts\activate     # для Windows
```

2. Установите зависимости:
```bash
pip install -r requirements.txt
```

3. Примените миграции:
```bash
python manage.py migrate
```

4. Создайте суперпользователя:
```bash
python manage.py createsuperuser
```

5. Запустите сервер разработки:
```bash
python manage.py runserver
``` 