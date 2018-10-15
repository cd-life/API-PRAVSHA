## Получение информации по ремонту

### POST /Searches/

Для авторизации используются ваши текущие логин(**login**):пароль(**password**) на сайте.

### Параметры запроса

|Параметр|Тип|Обязательный|Описание|
|---|---|---|---|
| terms.id | string | нет | номер заказа наряда на ремонт |
| terms.partner | string | нет | фио заказчика или наименование компании (полностью) |
| terms.phone | string | нет | номер телефона указанный в заказ наряде на ремонт |
| terms.product | string | нет | марка устройства |
| terms.imei | string | нет | imei |
| terms.uin | string | нет | uin |
| terms.sn | string | нет | серийный номер |

### Пример запроса

```http
POST /Requests/
Authorization: Basic
Content-Type: application/json
```
```json
{
    "terms": {
        "id": "СЦ-240487",
        "partner": "Иванов Иван Иванович",
        "phone": "+375331004500",
        "product": "K53U",
        "imei": "862374038999",
        "uin": "25-0000739101",
        "sn": "B9N0CJ024818159"
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
    "data": [
        {
            "id": "СЦ-240487",
            "partner": "Иванов Иван Иванович",
            "phone": "+375336016157",
            "product": "K53U",
            "imei": "862374038999",
            "uin": "25-0000739101",
            "sn": "B9N0CJ024818159",
            "status": "Ремонт выполнен"
        }
    ],
    "code": "ok"
}
```

### Описание полей ответа

|Параметр|Тип|Описание|
|---|---|---|
| terms.id | string | номер заказа наряда на ремонт |
| terms.partner | string | фио заказчика или наименование компании (полностью) |
| terms.phone | string | номер телефона указанный в заказ наряде на ремонт |
| terms.product | string | марка устройства |
| terms.imei | string | imei |
| terms.uin | string | uin |
| terms.sn | string | серийный номер |
| terms.status | string | Состояние заявки |

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
