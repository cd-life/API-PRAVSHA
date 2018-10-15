## Добавление заявки

### POST /Requests/

Для авторизации используются ваши текущие логин(**login**):пароль(**password**) на сайте.

### Параметры запроса

|Параметр|Тип|Обязательный|Описание|
|---|---|---|---|
| fields.request | string | да | текстовое описание заявки |

### Пример запроса

```http
POST /Requests/
Authorization: Basic
```
```json
{
    "fields": {
        "request": "Текст запроса"
    }
}
```

### Ответ в случае успеха

```http
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8
```
```json
{
    "data": "Номер запроса: 1659651",
    "code": "ok"
}
```

### Описание полей ответа

|Параметр|Тип|Описание|
|---|---|---|
| data | string | Номер созданного запроса |

### Ответ при ошибке авторизации

```http
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8
```
```json
{
    "data": "Login incorrect",
    "code": "error"
}
```
