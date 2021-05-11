# Действия с переменными

### 1) Получить список переменных проекта
`GET /v1/variables/project/{project_id}`

Принимаемые параметры:

* `project_id` - ID проекта

Ответ:
```json
{
    "status": "success",
    "code": 200,
    "message": "OK",
    "data": [
        {
            "id": 18,
            "name": "var_name",
            "type": "string",
            "settings": [],
            "owner_type": "project",
            "owner_id": 11712,
            "priority": 30,
            "is_blocked": false
        }
    ]
}
```

### 2) Получить список переменных компании
`GET /v1/variables/company`

Ответ:
```json
{
    "status": "success",
    "code": 200,
    "message": "OK",
    "data": [
        {
            "id": 18,
            "name": "var_name",
            "type": "string",
            "settings": [],
            "owner_type": "company",
            "owner_id": 1,
            "priority": 20,
            "is_blocked": false
        }
    ]
}
```

### 2) Получить список глобальных переменных
`GET /v1/variables/global`

Ответ:
```json
{
    "status": "success",
    "code": 200,
    "message": "OK",
    "data": [
        {
            "id": 18,
            "name": "var_name",
            "type": "string",
            "settings": [],
            "owner_type": "global",
            "owner_id": 1,
            "priority": 20,
            "is_blocked": false
        }
    ]
}
```

### 3) Получить список всех переменных 
#### (проекта, компании и глобальные)


`GET /v1/variables/all/{project_id}`

Принимаемые параметры:

* `project_id` - ID проекта

Ответ:
```json
{
    "status": "success",
    "code": 200,
    "message": "OK",
    "data": [
        {
            "id": 18,
            "name": "var_name",
            "type": "string",
            "settings": [],
            "owner_type": "project",
            "owner_id": 11712,
            "priority": 30,
            "is_blocked": false
        }
    ]
}
```

### 4) Просмотр переменной
`GET /v1/variables/{variable_id}`

Принимаемые параметры:

* `variable_id` - ID переменной

Ответ:
```json
{
    "status": "success",
    "code": 200,
    "message": "OK",
    "data": {
      "id": 18,
      "name": "var_name",
      "type": "string",
      "settings": [],
      "owner_type": "project",
      "owner_id": 11712,
      "priority": 30,
      "is_blocked": false
    }
}
```

### 5) Создание переменной
`POST /v1/variables`

Принимаемые параметры [объект переменной](object_descriptions.md):

* `name` - Имя переменной (без пробелов, регистр учитывается) 
* `type` - Тип переменной (string or integer). при записи значения будет привидено 
* `settings` - [Объект настроек переменной](object_descriptions.md)   
* `owner_type` - Тип объекта которому относится переменная (project or company)
* `owner_id` - ID проекта если owner_type=project, если owner_type=company в этом случае можно не указывать этот параметр (т.к будет взят ID компании которой вы принадлежите)
Ответ:
```json
{
    "status": "success",
    "code": 200,
    "message": "OK",
    "data": {
      "id": 18,
      "name": "var_name",
      "type": "string",
      "settings": [],
      "owner_type": "project",
      "owner_id": 11712,
      "priority": 30,
      "is_blocked": false
    }
}
```

### 5) Создание переменной
`POST /v1/variables`

Принимаемые параметры [объект переменной](object_descriptions.md):

* `name` - Имя переменной (без пробелов, регистр учитывается)
* `type` - Тип переменной (string or integer). при записи значения будет привидено
* `settings` - [Объект настроек переменной](object_descriptions.md)
* `owner_type` - Тип объекта которому относится переменная (project or company)
* `owner_id` - ID проекта если owner_type=project, если owner_type=company в этом случае можно не указывать этот параметр (т.к будет взят ID компании которой вы принадлежите)
  Ответ:
```json
{
    "status": "success",
    "code": 201,
    "message": "OK",
    "data": {
      "id": 18,
      "name": "var_name",
      "type": "string",
      "settings": [],
      "owner_type": "project",
      "owner_id": 11712,
      "priority": 30,
      "is_blocked": false
    }
}
```


### 6) Изменение типа и настроек переменной
`PATCH /v1/variables/{variable_id}`

Принимаемые параметры:
* `variable_id` - (url param) ID переменной 
* `type` - (json body param) Тип переменной (string or integer). 
* `settings` - (json body param) [Объект настроек переменной](object_descriptions.md)
Ответ:
```json
{
    "status": "success",
    "code": 200,
    "message": "OK",
    "data": {
      "id": 18,
      "name": "var_name",
      "type": "string",
      "settings": [],
      "owner_type": "project",
      "owner_id": 11712,
      "priority": 30,
      "is_blocked": false
    }
}
```

### 7) Удаление переменной
##### *при удалении переменной все значения ранее присвоенные респондентам удаляются
`DELETE /v1/variables/{variable_id}`

Принимаемые параметры:
* `variable_id` - (url param) ID переменной 

Ответ:
```json
{
    "status": "success",
    "code": 200,
    "message": "OK",
    "data": {
      "name": "var_name",
      "type": "string",
      "settings": [],
      "owner_type": "project",
      "owner_id": 11712,
      "priority": 30,
      "is_blocked": false
    }
}
```

