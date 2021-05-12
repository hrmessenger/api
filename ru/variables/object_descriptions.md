# Переменные

Используются в качестве хранения валидаций замене в сценарии ввиде
{{variable}}

<a name="variable_object"></a>
### Объект переменной

```json
 {
  "id": 18,
  "name": "var_name",
  "type": "string",
  "settings": {},
  "owner_type": "project",
  "owner_id": 11712,
  "priority": 30,
  "is_blocked": false
}
```

Имя | Тип | Описание
--- | --- | ---
id | integer | ID переменной
name | string | Имя переменной
type | string | Тип переменной (string, integer) при запросе значений перменных форматирует ответ в заданный тип
settings | object | Объект настроек переменной
owner_type | string | Тип объекта которому принадлежит переменная (project, company, global)
owner_id | integer | ID объекта которому принадлежит переменная
priority | integer |Приоритет (учитывается при замене переменных при одинаковых названиях будет взята та которая имеет больший) По умолчанию проект - 30, company - 20, global - 10
is_blocked | boolean | Маркер блокировки (если значение true значит переменная была создана из сценария и может изменяться только из сценария)

<a name="variable_settings_object"></a>
### Объект настроек (settings)

```json
{
  "title": "Заголовок переменной",
  "validation": [
    {
      "rule": "integer",
      "options" : {
        "message" : "Введите пожалуйста цифру",
        "min": 1,
        "tooSmall" : "Минимальное значение должно быть больше 1",
        "max": 10,
        "tooBig": "Максимальное значение не может быть выше 10"
      }
    }
  ]
}
```

Имя | Тип | Описание
--- | --- | ---
title | string | Заголовок переменной
validation | array | Массив правил валидаций (состоит из объектов правил валидаций)

<a name="variable_settings_validation_rule_object"></a>
### Объекты правила валидации 
<a name="variable_settings_validation_rule_object_integer"></a>
Целое число
```json
{
  "rule": "integer",
  "options" : {
    "message" : "Введите пожалуйста цифру",
    "min": 1,
    "tooSmall" : "Минимальное значение должно быть больше 1",
    "max": 10,
    "tooBig": "Максимальное значение не может быть выше 10"
  }
}
```
<a name="variable_settings_validation_rule_object_string"></a>
Строка
```json
{
  "rule": "string",
  "options" : {
    "message" : "Введите строку пожалуйста",
    "min": 1,
    "tooShort" : "Длина строки должна быть выше 1",
    "max": 10,
    "tooLong": "Длина строки должна быть меньше 10"
  }
}
```
<a name="variable_settings_validation_rule_object_date"></a>
Дата
```json
{
  "rule": "date",
  "options" : {
    "message" : "Не подходит формат",
    "format": "dd.ММ.yyyy", //ICU format or 'php:d.m.Y'
    "min": "11.05.2021",
    "tooShort" : "Дата должна быть после 11.05.2021",
    "max": "15.05.2021",
    "tooLong": "Но не больше 15.05.2021"
  }
}
```

<a name="variable_settings_validation_rule_object_match"></a>
Соответствие регулярному выражению (Regex match)
```json
{
  "rule": "match",
  "options" : {
    "message" : "Не соответствует регулярному выражению",
    "pattern": "/^[a-z]\w*$/i"
  }
}
```

<a name="variable_settings_validation_rule_object_boolean"></a>
Выбор из двух значений (boolean)
```json
{
  "rule": "boolean",
  "options" : {
    "message" : "Напишите да/нет",
    "trueValue": "да",
    "falseValue": "нет"
  }
}
```

<a name="variable_settings_validation_rule_object_email"></a>
Электронная почта (email)
```json
{
  "rule": "email",
  "options" : {
    "message" : "Напишите email"
  }
}
```

### Объект-значение переменной

```json
{
  "id": 62,
  "variable_id": 7,
  "owner_type": "respondent",
  "owner_id": 123,
  "priority": 10,
  "value": "value"
}
```

Имя | Тип | Описание
--- | --- | ---
id | integer | ID значения
variable_id | integer | ID переменной которому относится значение
owner_type | string | Тип объекта которому принадлежит значение (respondent) 
owner_id | integer | ID объекта которому принадлежит переменная
priority | integer | Приоритет наследуется от переменной
value | mixed | Непосредственно значение


