# Получение списка проектов

`GET /v1/projects` вернёт список проектов компании.

Принимаемые параметры:

* `mine` - логическое поле. Если передается, то вернутся только проекты, над которыми работает текущий пользователь.

* `page`, `pageSize` - параметры постраничного вывода

```
{
	"items":[
		{
	      "id": 6459,
	      "title": "Кассир-продавец 21",
	      "user_name": "service.candidates",
	      "user_email": "service.candidates",
	      "company": "Almat inc.",
	      "city_title": "Алматы",
	      "city_timezone": "Asia/Almaty"
	    },
	    {
	      "id": 6458,
	      "title": "Кассир-продавец 21",
	      "user_name": "service.candidates",
	      "user_email": "service.candidates",
	      "company": "Almat inc.",
	      "city_title": "Алматы",
	      "city_timezone": "Asia/Almaty"
	    },
	    {
	      "id": 6457,
	      "title": "Кассир-продавец 21",
	      "user_name": "service.candidates",
	      "user_email": "service.candidates",
	      "company": "Almat inc.",
	      "city_title": "Алматы",
	      "city_timezone": "Asia/Almaty"
	    }
	]
}
```


Имя | Тип | Описание
--- | --- | ---
id | number | ID проекта
title | string | Название проекта
user_name | string | Имя менеджера проекта
user_email | string | E-mail менеджера проекта
company | string | Название компании
city_title | string | Название города проекта
city_timezone | string | Таймзона проекта



