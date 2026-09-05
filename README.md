# Yatube API

REST API for the Yatube social network: posts, comments, groups and subscriptions. Authentication with JWT.

Built during the *Python Developer* course at Yandex Practicum (2025–2026). Every project was reviewed and accepted by a course mentor.

## Tech stack

Python 3 · Django 5 · Django REST Framework · Simple JWT · SQLite

## Endpoints

| Method | Path | Purpose |
|---|---|---|
| `POST` | `/api/v1/jwt/create/` | obtain access/refresh tokens |
| `GET/POST` | `/api/v1/posts/` | list (paginated) / create posts |
| `GET/PUT/PATCH/DELETE` | `/api/v1/posts/<id>/` | single post — write access for the author only |
| `GET/POST` | `/api/v1/posts/<id>/comments/` | comments of a post |
| `GET` | `/api/v1/groups/` | groups |
| `GET/POST` | `/api/v1/follow/` | subscriptions of the current user, `?search=<username>` |

Interactive documentation: `http://127.0.0.1:8000/redoc/`.

## Run locally

```bash
python -m venv venv
source venv/bin/activate          # Windows: venv\Scripts\activate
pip install -r requirements.txt
cd yatube_api
python manage.py migrate
python manage.py runserver
```

Optional: set `DJANGO_SECRET_KEY` in the environment; a development default is used otherwise.

## Example

```http
POST /api/v1/posts/
Authorization: Bearer <access-token>

{"text": "Hello, Yatube", "group": 1}
```

## Tests

```bash
pytest          # 55 tests
```

## Author

Roman Tanashkin — [github.com/RomanTanashkin](https://github.com/RomanTanashkin)
