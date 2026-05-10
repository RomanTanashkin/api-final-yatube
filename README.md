# api_final

REST API для социальной сети Yatube: публикации, комментарии, сообщества, подписки. Аутентификация по JWT-токену.

## Стек

Python 3.x, Django 5, Django REST Framework, Simple JWT, SQLite.

## Установка

Клонировать репозиторий и перейти в него:

```
git clone <url>
cd api_final_yatube
```

Создать и активировать виртуальное окружение:

```
python -m venv venv
source venv/bin/activate    # Linux/macOS
venv\Scripts\activate       # Windows
```

Установить зависимости:

```
pip install -r requirements.txt
```

Выполнить миграции и запустить сервер:

```
cd yatube_api
python manage.py migrate
python manage.py runserver
```

Документация API доступна по адресу `http://127.0.0.1:8000/redoc/`.

## Примеры запросов

Получить JWT-токен:

```
POST /api/v1/jwt/create/
{
    "username": "user",
    "password": "pass"
}
```

Получить список постов:

```
GET /api/v1/posts/
```

Создать пост (требуется заголовок `Authorization: Bearer <access-token>`):

```
POST /api/v1/posts/
{
    "text": "Текст поста",
    "group": 1
}
```

Подписаться на пользователя:

```
POST /api/v1/follow/
{
    "following": "username"
}
```

Поиск по подпискам:

```
GET /api/v1/follow/?search=username
```

## Автор

Roman Tanashkin
