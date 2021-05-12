# Действия со значениями переменных

### 1) Получить значения переменных для определенной переменной

`GET /v1/variables/{variable_id}/values`

Принимаемые параметры:

* `variable_id` - ID переменной

Ответ массив [объектов-значений переменных](object_descriptions.md):

```json
{
  "status": "success",
  "code": 200,
  "message": "OK",
  "data": [
    {
      "id": 62,
      "variable_id": 7,
      "owner_type": "respondent",
      "owner_id": 123,
      "priority": 10,
      "value": "значение"
    }
  ]
}
```

### 2) Получить значения переменных для определенного респондента

`GET /v1/variables/values/of/respondent/{resp_id}`

Принимаемые параметры:

* `resp_id` - ID респондента (core_resp_id)

Ответ массив [объектов-значений переменных](object_descriptions.md):

```json
{
  "status": "success",
  "code": 200,
  "message": "OK",
  "data": [
    {
      "id": 62,
      "variable_id": 7,
      "owner_type": "respondent",
      "owner_id": 123,
      "priority": 10,
      "value": "значение"
    }
  ]
}
```

### 3) Получить значение переменной по ID

`GET /v1/variables/values/{variable_value_id}`

Принимаемые параметры:

* `variable_value_id` - ID значения переменной

Ответ [объект-значение переменной](object_descriptions.md):

```json
{
  "status": "success",
  "code": 200,
  "message": "OK",
  "data": {
    "id": 62,
    "variable_id": 7,
    "owner_type": "respondent",
    "owner_id": 123,
    "priority": 10,
    "value": "значение"
  }
}
```

### 4) Установить значение переменной для респондента 

`POST /v1/variables/{variable_id}/set-value`

Принимаемые параметры:

* `variable_id` - (url param) ID переменной
* `owner_type` - (body param) тип объекта которому относится значение обычно respondent
* `owner_id` - ID респондента (если тип respondent)
* `value` - непосредственно значение

Ответ [объект-значение переменной](object_descriptions.md):

```json
{
  "status": "success",
  "code": 201,
  "message": "OK",
  "data": {
    "id": 62,
    "variable_id": 7,
    "owner_type": "respondent",
    "owner_id": 123,
    "priority": 10,
    "value": "значение"
  }
}
```

### 5) Удаление значения переменной
`DELETE /v1/variables/values/{variable_value_id}`

Принимаемые параметры:
* `variable_value_id` - (url param) ID значения переменной

Ответ:
```json
{
  "status": "success",
  "code": 200,
  "message": "OK",
  "data": {
    "id": 62,
    "variable_id": 7,
    "owner_type": "respondent",
    "owner_id": 123,
    "priority": 10,
    "value": "значение"
  }
}
```

