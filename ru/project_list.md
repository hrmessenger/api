# Получение списка проектов

`GET /v1/projects` вернёт список проектов компании.

Принимаемые параметры:

* `page`, `pageSize` - параметры постраничного вывода

```
{
	"status": "success",
	"code": 200,
	"message": "OK",
	"data": {
		"page": 1,
		"pageSize": 20,
		"items":[
			{
		      "id": 111,
		      "title": "Project 1 Title",
		      "status": 0,
		      "user": {
		        "name": "User Name",
		        "lastName": "User Last Name",
		        "username": "example@example.com"
		      },
		      "city": {
		        "id": 222,
		        "title": "Алматы",
		        "timezone": "Asia/Almaty"
		      },
		      "binded": true,
		      "vacancy": {
		      	"id": "ID of your vacancy",
		      	"vacancy": "Title of vacancy",
		      	"link": "Link to vacancy",
		      	"details": ["detail1", "detail2", "detail3"]
		      }
		    },
		    {
		      "id": 112,
		      "title": "Project 2 Title",
		      "status": 0,
		      "user": {
		        "name": "User Name",
		        "lastName": "User Last Name",
		        "username": "example@example.com"
		      },
		      "city": {
		        "id": 222,
		        "title": "Алматы",
		        "timezone": "Asia/Almaty"
		      },
		      "binded": false,
		      "vacancy": {}
		    }
		]
	}
}
```


Имя | Тип | Описание
--- | --- | ---
id | number | ID проекта
title | string | Название проекта
user.name | string | Имя менеджера проекта
user.lastName | string | Фамилия менеджера проекта
user.email | string | Аккаунт менеджера проекта
city.id | number | ID города в справочнике
city.title | string | Название города проекта
city.timezone | string | Таймзона города
binded | boolean | Создана ли связь с вакансией
vacancy.id | number | ID вакансии в вашей системе, с которой связан проект
vacancy.vacancy | string | Название вакансии
vacancy.link | string | Ссылка на вакансию
vacancy.details | array | Массив из 3 (макс) элементов с дополнительныи данными


Данные объекта vacancy формулируются при создании связи проект-вакансия и полностью дублируют ту же информацию.



