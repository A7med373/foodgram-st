# Foodgram

Foodgram - веб-приложение для публикации рецептов, избранного, подписок и формирования списка покупок. Проект состоит из Django backend API, React frontend и инфраструктуры для запуска через Docker.

## Возможности

- Регистрация и аутентификация пользователей.
- Создание, редактирование и удаление рецептов.
- Работа с ингредиентами и тегами.
- Добавление рецептов в избранное.
- Подписки на авторов.
- Формирование и скачивание списка покупок.
- API-документация через OpenAPI/Redoc.
- Docker-инфраструктура для backend, frontend, PostgreSQL и Nginx.

## Стек

- Python
- Django
- Django REST Framework
- PostgreSQL
- React
- Docker, Docker Compose
- Nginx
- Gunicorn

## Запуск через Docker

Создайте `.env` в корне проекта или в директории `infra` в зависимости от способа запуска:

```env
SECRET_KEY=change-me
DEBUG=False
POSTGRES_DB=foodgram
POSTGRES_USER=foodgram
POSTGRES_PASSWORD=foodgram
DB_HOST=db
DB_PORT=5432
```

Запуск инфраструктуры:

```bash
cd infra
docker compose up --build
```

После запуска:

```text
Frontend: http://localhost
API docs: http://localhost/api/docs/
```

## Backend локально

```bash
cd backend
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
```

## Загрузка ингредиентов

В проекте есть данные ингредиентов:

```text
data/ingredients.json
data/ingredients.csv
backend/ingredients.json
backend/ingredients.csv
```

Команда загрузки находится в:

```text
backend/recipes/management/commands/load_ingredients.py
```

## Структура

```text
backend/       - Django API
frontend/      - React-приложение
infra/         - Docker Compose и Nginx
docs/          - OpenAPI/Redoc документация
data/          - исходные данные ингредиентов
```

## Что демонстрирует проект

- Разработку REST API на Django REST Framework.
- Связанные модели пользователей, рецептов, ингредиентов, тегов и подписок.
- Контейнеризацию fullstack-приложения.
- Подготовку проекта к запуску за Nginx.
