---
description: Команда; авторизует веб-пользователя.
---

# LoginCommand

## Шаблон LoginCommand <a href="#template_login_command" id="template_login_command"></a>

```xml
<Command Name="" Type="LoginCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд, отсутствуют-->
  <!--Тэги, специфичные для LoginCommand-->
  <UserName></UserName>
  <Password></Password>
</Command>
```

## Описание LoginCommand <a href="#description_login_command" id="description_login_command"></a>

```xml
<Command Name="LoginCommandName" Type="LoginCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <!--Тэги, специфичные для LoginCommand-->
</Command>
```

### Результат выполнения LoginCommand <a href="#result_login_command" id="result_login_command"></a>

#### Value <a href="#result_value" id="result_value"></a>

Результат выполнения команды: "Ok" - если авторизация пройдена успешно, иначе - "Fail".

## Тэги, специфичные для LoginCommand <a href="#tags_login_command" id="tags_login_command"></a>

### UserName <a href="#user_name" id="user_name"></a>

Системное имя пользователя.

Обязательный тэг. Любое значение преобразуется в текстовое.

```xml
<UserName>False</UserName>
```

### Password <a href="#password" id="password"></a>

Пароль пользователя.

Обязательный тэг. Любое значение преобразуется в текстовое.

```xml
<Password>False</Password>
```
