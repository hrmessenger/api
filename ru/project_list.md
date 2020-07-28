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
	      "title": "Кассир-продовец",
	      "user_name": "Иван Иванович",
	      "user_email": "user@example.com",
	      "company": "Example inc.",
	      "city_title": "Москва",
	      "city_timezone": "Europe/Moscow"
	    },
	    {
	      "id": 6460,
	      "title": "Менеджер по продажам",
	      "user_name": "Иван Иванович",
	      "user_email": "user@example.com",
	      "company": "Example inc.",
	      "city_title": "Москва",
	      "city_timezone": "Europe/Moscow"
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



