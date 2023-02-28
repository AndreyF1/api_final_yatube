# Yatube project
Educational project on creating a social network: registration, authorization, creation of posts, adding groups, comments on posts, subscriptions to authors.

## How to launch a project:
Clone the repository and go to it on the command line:
```
git clone git@github.com:{github_username}/api_final_yatube.git
```
```
cd api_final_yatube
```
Create and activate a virtual environment:
```
python3 -m venv venv
```
```
source venv/bin/activate
```
Install dependencies from a file requirements.txt:
```
python3 -m pip install --upgrade pip
```
```
pip install -r requirements.txt
```
Migrate:
```
python3 manage.py migrate
```
Launch a project:
```
python3 manage.py runserver
```

## Examples of API requests
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
