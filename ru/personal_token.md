# Авторизация & персональный токен

Персональный токен служит для упрощения интеграции с HRMessenger API и не требует дополнительного процесса авторизации.

Для получения персонального токена:
* авторизуйтесь в системе [crm.hrmessenger.com](https://crm.hrmessenger.com)
* передите в раздел интеграции через соответсвующий пункт меню
* в списке доступных интеграций выберите ```HRMessenger API```
* персональный токен будет доступен после подключения в поле ```Персональный токен```

Токен будет ассоциирован с этим пользователем. Это значит, что все действия, совершенные с использованием токена, будут выполнены от лица ассоциированного пользователя. Кроме того, действия, недоуступные для ассоциированного пользователя будут недоступны и для токена.

**Внимание!** Использование персонального токена требует более высокого уровня безопасности в вопросах его хранения и несанкционированного доступа.

### Использование персонального токена

Приложение должно использовать полученный токен при запросах, передавая его в заголовке в формате:

```Authorization: Bearer <personal_token>```


```http
GET /me HTTP/1.1
User-Agent: App/1.0 (in_case_of_fire@example.com)
Host: api.hrmessenger.com
Accept: */*
Authorization: Bearer <personal_token>
```
