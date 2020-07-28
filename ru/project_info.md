# Получение данных по проекту

`GET /v1/projects/{project_id}` вернёт данные по проекту с идентификатором `{project_id}`


```
{
    "title": "Менеджер по продажам",
    "status": 0,
    "user_id": 4,
    "city_id": 1,
    "city": "Москва",
    "timezone": "Europe/Moscow",
    "user_name": "Иван Иванович",
	"user_email": "user@example.com",
    "company": "Example inc."
}
```


Имя | Тип | Описание
--- | --- | ---
id | number | ID проекта
title | string | Название проекта
status | string | Статус проекта
user_name | string | Имя менеджера проекта
user_email | string | E-mail менеджера проекта
company | string | Название компании
city_id | string | Идентификатор города
city | string | Название города проекта
timezone | string | Таймзона проекта



