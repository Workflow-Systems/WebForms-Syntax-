---
description: Команда; запускает команду на сервере с определенными параметрами.
---

# CallCommand

## Шаблон CallCommand <a href="#template_call_command" id="template_call_command"></a>

```xml
<Command Name="" Type="CallCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <Condition Name="" />
  <Lock Value="" />
  <!--Тэги, специфичные для CallCommand-->
  <Workflow Name="" />
  <Command Name="" />
  <Parameters>
    <Parameter Name="" SendAsArray=""></Parameter>
  </Parameters>
</Command>
```

## Описание CallCommand <a href="#description_call_command" id="description_call_command"></a>

```xml
<Command Name="CallCommandName" Type="CallCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <!--Тэги, специфичные для CallCommand-->
</Command>
```

### Результат выполнения CallCommand <a href="#result_call_command" id="result_call_command"></a>

#### Value <a href="#result_value" id="result_value"></a>

Результат выполнения команды, возвращенный сервером.

Если возвращаемое значение от сервера это объект типа `Dictionary<string, object>`, то к результату команды CallCommand можно обращаться с помощью параметров Parameter, имена которых являются ключами этого `Dictionary`.

## Тэги, специфичные для CallCommand <a href="#tags_call_command" id="tags_call_command"></a>

### Workflow <a href="#workflow" id="workflow"></a>

Процесс, в рамках которого выполняется команда на сервере.

Обязательный тэг. Значение тэга `<Workflow>`: не ожидается.

```xml
<Workflow Name="WorkflowName" />
```

#### Атрибуты тэга `<Workflow>` <a href="#attributes_tag_workflow" id="attributes_tag_workflow"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Название процесса.</p><p></p><p>Обязательный атрибут. Ожидается название одного из процессов, описанных на сервере.</p></td></tr></tbody></table>

### Command <a href="#command" id="command"></a>

Команда, выполняющаяся на сервере.

Обязательный тэг. Значение тэга `<Command>`: не ожидается.

```xml
<Command Name="CommandName" />
```

#### Атрибуты тэга `<Command>` <a href="#attributes_tag_command" id="attributes_tag_command"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Название процесса.</p><p></p><p>Обязательный атрибут. Ожидается название одной из команд, описанных в указанном процессе на сервере.</p></td></tr></tbody></table>

### Parameters <a href="#parameters" id="parameters"></a>

Параметры, которые будут переданы в команду на сервере.

Необязательный тэг. Значение тэга `<Parameters>`: список тэгов [`<Parameter>`](call_command.md#parameters_parameter).

```xml
<Parameters>
  <Parameter Name="ParameterName1" SendAsArray="False">ParameterValue1</Parameter>
  <Parameter Name="ParameterName2" SendAsArray="True">ParameterValue2</Parameter>
</Parameters>
```

#### Тэг `<Parameter>` <a href="#parameters_parameter" id="parameters_parameter"></a>

Параметр, который будет передан в команду на сервере.

Необязательный тэг. Значение тэга `<Parameter>`: любое значение.

#### Атрибуты тэга `<Parameter>` <a href="#attributes_tag_parameters_parameter" id="attributes_tag_parameters_parameter"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Название одного из параметров, которые поддерживается указанной командой на сервере.</p><p></p><p>Обязательный атрибут.</p></td></tr><tr><td align="center">SendAsArray</td><td><p>Признак, определяющий будет ли значение передаваться как массив.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>Если атрибут <code>SendAsArray</code> отсутствует, то используется значение False.</p></td></tr></tbody></table>
