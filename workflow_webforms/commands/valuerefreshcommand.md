---
description: Команда; выполняет обновление значения.
---

# ValueRefreshCommand

## Шаблон ValueRefreshCommand <a href="#template_value_refresh_command" id="template_value_refresh_command"></a>

```xml
<Command Name="" Type="ValueRefreshCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <Condition Name="" />
  <Lock Value="" />
  <!--Тэги, специфичные для ValueRefreshCommand-->
  <Value />
</Command>
```

## Описание ValueRefreshCommand <a href="#description_value_refresh_command" id="description_value_refresh_command"></a>

```xml
<Command Name="ValueRefreshCommandName" Type="ValueRefreshCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <!--Тэги, специфичные для ValueRefreshCommand-->
</Command>
```

### Результат выполнения ValueRefreshCommand <a href="#result_value_refresh_command" id="result_value_refresh_command"></a>

Команда не имеет результата.

## Тэги, специфичные для ValueRefreshCommand <a href="#tags_value_refresh_command" id="tags_value_refresh_command"></a>

### Value <a href="#value" id="value"></a>

Переменная, которая будет обновлена.

Обязательный тэг. Значение тэга `<Value>`: любое значение.

```xml
<Value>Value</Value>
```
