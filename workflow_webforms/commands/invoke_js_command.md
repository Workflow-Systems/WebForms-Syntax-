---
description: Команда выполнения
---

# InvokeJsCommand

## Шаблон InvokeJsCommand <a href="#template" id="template"></a>

```xml
<Command Name="" Type="InvokeJsCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <Condition Name="" />
  <Lock Value="" />
  <!--Тэги, специфичные для CallCommand-->
  <Value></Value>
  <Parameters>
    <Parameter Name="" SendAsArray=""></Parameter>
  </Parameters>
</Command>
```

## Описание InvokeJsCommand <a href="#description" id="description"></a>

```xml
<Command Name="InvokeJsCommandName" Type="InvokeJsCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <!--Тэги, специфичные для CallCommand-->
</Command>
```

### Результат выполнения InvokeJsCommand <a href="#execution-result" id="execution-result"></a>

Команда не имеет результата.

## Тэги, специфичные для InvokeJsCommand <a href="#tags_call_command" id="tags_call_command"></a>

### Value <a href="#value" id="value"></a>

Признак, определяющий, будет ли выполнение команды происходить в асинхронном режиме (в фоновом потоке).

Необязательный тэг. Ожидается название одного из режимов:

<table data-header-hidden><thead><tr><th width="202.08667435984262" align="center"></th><th width="521.8817842146913"></th></tr></thead><tbody><tr><td align="center">scrollToBottom</td><td></td></tr><tr><td align="center">cleanQueryString</td><td></td></tr><tr><td align="center">invokeButtonClick</td><td></td></tr></tbody></table>

По умолчанию используется значение All.

```xml
<Value></Value>
```

### Parameters <a href="#parameters" id="parameters"></a>

Необязательный тэг. Значение тэга `<Async>`: не ожидается.

Если тэг `<Async>` отсутствует, то для атрибута `Value` используется значение False.

```xml
<Parameters>
  <Parameter Name="" SendAsArray=""></Parameter>
</Parameters>
```

