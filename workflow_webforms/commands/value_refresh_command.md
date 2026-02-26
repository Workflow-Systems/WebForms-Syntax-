---
description: Команда; сериализует переменную в json строку.
---

# SerializeToJsonCommand

## Шаблон SerializeToJsonCommand <a href="#template_serialize_to_json_command" id="template_serialize_to_json_command"></a>

```xml
<Command Name="" Type="SerializeToJsonCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <Condition Name="" />
  <Lock Value="" />
  <!--Тэги, специфичные для SerializeToJsonCommand-->
  <Variable></Variable>
</Command>
```

## Описание SerializeToJsonCommand <a href="#description_serialize_to_json_command" id="description_serialize_to_json_command"></a>

```xml
<Command Name="SerializeToJsonCommandName" Type="SerializeToJsonCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <!--Тэги, специфичные для SerializeToJsonCommand-->
</Command>
```

### Результат выполнения SerializeToJsonCommand <a href="#result_serialize_to_json_command" id="result_serialize_to_json_command"></a>

#### Value <a href="#result_value" id="result_value"></a>

Строка содержащая представление переменной в json.

## Тэги, специфичные для SerializeToJsonCommand <a href="#tags_serialize_to_json_command" id="tags_serialize_to_json_command"></a>

### Variable <a href="#variable" id="variable"></a>

[Переменная](../objects/variable.md), которая будет сериализована в json строку.

Обязательный тэг. Значение тэга `<Variable>`: любое значение.

```xml
<Variable></Variable>
```
