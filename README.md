# Yatube project
Учебный проект по созданию социальной сети: регистрация, авторизация, создание постов, добавление групп, комментарии постов, подписки на авторов.

## Как запустить проект:
Клонировать репозиторий и перейти в него в командной строке:
```
git clone git@github.com:{github_username}/api_final_yatube.git
```
```
cd api_final_yatube
```
Cоздать и активировать виртуальное окружение:
```
python3 -m venv venv
```
```
source venv/bin/activate
```
Установить зависимости из файла requirements.txt:
```
python3 -m pip install --upgrade pip
```
```
pip install -r requirements.txt
```
Выполнить миграции:
```
python3 manage.py migrate
```
Запустить проект:
```
python3 manage.py runserver
```

## Примеры запросов к API
`GET` /api/v1/posts/
```
{
  "count": 123,
  "next": "http://api.example.org/accounts/?offset=400&limit=100",
  "previous": "http://api.example.org/accounts/?offset=200&limit=100",
  "results": [
    {
      "id": 0,
      "author": "string",
      "text": "string",
      "pub_date": "2021-10-14T20:41:29.648Z",
      "image": "string",
      "group": 0
    }
  ]
}
```
`GET` /api/v1/posts/{id}
```
{
  "id": 0,
  "author": "string",
  "text": "string",
  "pub_date": "2019-08-24T14:15:22Z",
  "image": "string",
  "group": 0
}
```
`GET` /api/v1/posts/{post_id}/comments/
```
[
  {
    "id": 0,
    "author": "string",
    "text": "string",
    "created": "2019-08-24T14:15:22Z",
    "post": 0
  }
]
```
`POST` /api/v1/posts/{post_id}/comments/

Request samples
```
{
  "text": "string"
}
```
Response samples
```
{
  "id": 0,
  "author": "string",
  "text": "string",
  "created": "2019-08-24T14:15:22Z",
  "post": 0
}
```
`POST` /api/v1/follow/

Request samples
```
{
  "following": "string"
}
```
Response samples
```
{
  "user": "string",
  "following": "string"
}
```
`POST` /api/v1/jwt/create/

Request samples
```
{
  "username": "string",
  "password": "string"
}
```
Response samples
```
{
  "refresh": "string",
  "access": "string"
}
```
