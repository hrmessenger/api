# Общая информация

+ API работает по протоколу HTTPS
+ Авторизация осуществляется по персональному токену
+ Все данные доступны только в формате JSON
+ Базовый URL — `https://api.hrmessenger.com`
+ Даты форматируются в соответствии с 
[ISO 8601](http://en.wikipedia.org/wiki/ISO_8601): `YYYY-MM-DDThh:mm:ss±hh:mm`

<a name="request_requirements"></a>
### Требования к запросам

В запросе необходимо передавать заголовок `User-Agent`, в противном случае
ответом будет `400 Bad Request`. Указание в заголовке названия приложения и
контактной почты разработчика позволит нам оперативно с вами связаться в случае
необходимости.

```
User-Agent: App/1.0 (incaseoffire@example.com)
```

<a name="request_body"></a>
### Формат тела запроса при отправке JSON

Данные, передающиеся в теле запроса, должны удовлетворять требованиям:

* Валидный JSON (допускается передача как минифицированного варианта, так и
  pretty print варианта с дополнительными пробелами и сбросами строк).
* Рекомендуется использование кодировки UTF-8 без дополнительного экранирования
  (`{"name": "Иванов Иван"}`).
* Также возможно использовать ascii кодировку с экранированием
  (`{"name": "\u0418\u0432\u0430\u043d\u043e\u0432 \u0418\u0432\u0430\u043d"}`).
* К типам данных в определённым полях накладываются дополнительные условия,
  описанные в каждом конкретном методе. В JSON типами данных являются `string`,
  `number`, `boolean`, `null`, `object`, `array`.



<a name="errors-and-codes"></a>
### Ошибки и коды ответов

API широко использует информирование при помощи кодов ответов.
Приложение должно корректно их обрабатывать.

В случае неполадок и сбоев, возможны ответы с кодом `503` и `500`.

При каждой ошибке, помимо кода ответа, в теле ответа может быть выдана
дополнительная информация, позволяющая разработчику понять
причину соответствующего ответа.

[Более подробно про возможные ошибки](ru/errors.md).


<a name="pagination"></a>
### Постраничный вывод

К запросам, подразумевающим выдачу списка объектов, можно в параметрах
указать `page=N&pageSize=M`. Нумерация идёт с единицы, по умолчанию выдаётся
первая страница с 10 объектами на странице. Во всех ответах, где
доступен постраничный вывод, единообразный корневой объект:

```json
{
  "page": 1,
  "pageSize": 1,
  "total": 1,
  "items": [{}]
}
```

<a name="links"></a>
## Полезные ссылки

* [HTTP/1.1](http://tools.ietf.org/html/rfc2616)
* [JSON](http://json.org/)
* [URI Template](http://tools.ietf.org/html/rfc6570)
* [OAuth 2.0](http://tools.ietf.org/html/rfc6749)
* [REST](http://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm)
* [ISO 8601](http://en.wikipedia.org/wiki/ISO_8601)