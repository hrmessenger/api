# Получение списка проектов

`POST api.hrmessenger.com/v1/projects/{project_id}/responses` вернёт список респондентов по проекту с ID `{project_id}`

Принимаемые параметры:

* status - фильтр по статусу кандидата. Если не передается, то по умолчанию все статусы
* `page`, `pageSize` - параметры постраничного вывода

Статус | Описание
--- | ---
nowhatsapp | Респонденты, которые не зарегистрированы в WhatsApp
delivered | Респонденты, которые получили сообщение, но пока не ответили
rejected | Респонденты, которые отказались на каком то этапе либо не прошли
inproccess | Респонденты, которые в процессе переписки и не дошли до какого то конечного результата
finished | Респонденты, которые дошли до финального действия. Например, если сценарий подразумевает запись на собеседование, то на этом статусе будут те кандидаты, которые записались на собеседование
stucked | Респонденты, которые начали переписку, но так ее и не завершили спустя 48 часов


```
{
	"status": "success",
	"code": 200,
	"message": "OK",
	"data": {
		"vacancyId": "your vacancy ID",
		"total": 2,
		"responses":[
			{
				"response_id": 111,
				"source": "Source Name",
				"status": {
				  "time": 1591164053,
				  "title": "status_delivered",
				  "step": "Первый этап"
				},
				"personal_data": {
				  "name": "Иван",
				  "last_name": "Иванов",
				  "phones": [
				    "77055554433"
				  ]
				},
				"additional_data": {
				  "incoming_import": false,
				  "responseId": "your response ID",
				  "some_key": "some_value"
				}
			},
		]
	}
}
```


Имя | Тип | Описание
--- | --- | ---
response_id | number | ID респондента
source | string | Название источника отклика или импорта
status.time | number | Timestamp когда произошла смена статуса
status.title | string | Название статуса
status.step | string | Название этапа на котором кандидат
personal_data.name | string | Имя респондента
personal_data.last_name | string | Фамилия респондента
personal_data.phones | array | Массив с известными номерами телефонов респондента
additional_data.{} | object | Объект с дополнительными данными респондента. В этом же объекте будут данные, которые при импорте были в массиве `info`
additional_data.incoming_import | bolean | Флаг отклика. True - если кандидат откликнулся сам. False - кандидат был импортирован
additional_data.responseId | string | Присутствует, если импорт был посредством API и содержит vacancyId, который был указан при запросе
