# Действия

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
            "is_blocked": false,
        }
    ]
}
```

### 2) Получить список переменных компании
`GET /v1/variables/company

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
            "is_blocked": false,
        }
    ]
}
```

### 2) Получить список глобальных переменных
`GET /v1/variables/global

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
            "is_blocked": false,
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
            "is_blocked": false,
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
      "is_blocked": false,
    }
}
```