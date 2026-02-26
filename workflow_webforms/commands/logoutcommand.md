---
description: Команда; деавторизует веб-пользователя.
---

# LogoutCommand

## Шаблон LogoutCommand <a href="#template_login_command" id="template_login_command"></a>

```xml
<Command Name="" Type="LogoutCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <Condition Name="" />
  <Lock Value="" />
  <!--Тэги, специфичные для LogoutCommand, отсутствуют-->
</Command>
```

## Описание LogoutCommand <a href="#description_login_command" id="description_login_command"></a>

```xml
<Command Name="LogoutCommandName" Type="LogoutCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <!--Тэги, специфичные для LoginCommand-->
</Command>
```

### Результат выполнения LogoutCommand <a href="#result_login_command" id="result_login_command"></a>

#### Value <a href="#result_value" id="result_value"></a>

Результат выполнения команды: "Ok" - если деавторизация успешно завершена, иначе - "Fail".
