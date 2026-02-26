---
description: Команда; выполняет присвоение значения.
---

# ValueSetCommand

## Шаблон ValueSplatetCommand <a href="#template_value_set_command" id="template_value_set_command"></a>

```xml
<Command Name="" Type="ValueSetCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <Condition Name="" />
  <Lock Value="" />
  <!--Тэги, специфичные для ValueSetCommand-->
  <Object Name=""></Object>
</Command>
```

## Описание ValueSetCommand <a href="#description_value_set_command" id="description_value_set_command"></a>

```xml
<Command Name="ValueSetCommandName" Type="ValueSetCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <!--Тэги, специфичные для ValueSetCommand-->
</Command>
```

### Результат выполнения ValueSetCommand <a href="#result_value_set_command" id="result_value_set_command"></a>

Команда не имеет результата.

## Тэги, специфичные для ValueSetCommand <a href="#tags_value_set_command" id="tags_value_set_command"></a>

Внутри тэга `<Command>` ожидается одна из [конструкций](value_set_command.md#value_set_constructions) присвоения значения.

## Конструкции присвоения значения <a href="#value_set_constructions" id="value_set_constructions"></a>

### Присвоение значения объекту (тэг `<Object>`**)** <a href="#set_object" id="set_object"></a>

[Объект](../objects/) (переменная, графический объект, элемент меню или контекстное меню), которому будет присваиваться значение.

Обязательный тэг. Значение тэга `<Object>`: ожидаемое для объекта значение.

```xml
<Object Name="ObjectName">Value</Object>
```

#### Атрибуты тэга `<Object>` <a href="#attributes_tag_set_object" id="attributes_tag_set_object"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Название объекта.</p><p></p><p>Обязательный атрибут. Значение атрибута <code>Name</code>: название одного из объектов, описанных в форме.</p></td></tr></tbody></table>

### Присвоение посредством set-проперти объекта (тэг `<Object>`) <a href="#set_object_property" id="set_object_property"></a>

[Объект](../objects/) (переменная, графический объект, элемент меню или контекстное меню), посредством set-проперти которого будет присваиваться значение.

Обязательный тэг. Значение тэга `<Object>`: тэг `<Property>`.

```xml
<Object Name="ObjectName">
  <Property Name="PropertyName">Value</Property>
</Object>
```

#### Атрибуты тэга `<Object>` <a href="#attributes_tag_set_object_property" id="attributes_tag_set_object_property"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Название объекта.</p><p></p><p>Обязательный атрибут. Значение атрибута <code>Name</code>: название одного из объектов, описанных в форме.</p></td></tr></tbody></table>

#### Тэг `<Property>` <a href="#set_object_property_property" id="set_object_property_property"></a>

Set-проперти объекта.

Обязательный тэг. Значение тэга `<Property>`: ожидаемое для set-проперти объекта значение.

#### Атрибуты тэга `<Property>` <a href="#attributes_tag_set_object_property_property" id="attributes_tag_set_object_property_property"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Название set-проперти объекта.</p><p></p><p>Обязательный атрибут. Значение атрибута <code>Name</code>: название одного из set-проперти объекта.</p></td></tr></tbody></table>

### Присвоение посредством set-проперти формы (тэг `<Form>`) <a href="#set_form_property" id="set_form_property"></a>

[Форма](/broken/pages/-MaRrLvqMdBI-ceJPvyX), посредством set-проперти которой будет присваиваться значение.

Обязательный тэг. Значение тэга `<Form>`: тэг `<Property>`.

```xml
<Form>
  <Property Name="PropertyName">Value</Property>
</Form>
```

#### Тэг `<Property>` <a href="#set_form_property_property" id="set_form_property_property"></a>

Set-проперти формы.

Обязательный тэг. Значение тэга `<Property>`: ожидаемое для set-проперти формы значение.

#### Атрибуты тэга `<Property>` <a href="#attributes_tag_set_form_property_property" id="attributes_tag_set_form_property_property"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Название set-проперти формы.</p><p></p><p>Обязательный атрибут. Значение атрибута <code>Name</code>: название одного из set-проперти формы.</p></td></tr></tbody></table>

### Присвоение значения явному или неявному параметру формы (тэг `<Parameter>`) <a href="#set_parameter" id="set_parameter"></a>

[Параметр формы](../parameters.md), которому будет присваиваться значение.

Обязательный тэг. Значение тэга `<Parameter>`: любое значение.

```xml
<Parameter Name="ParameterName">Value</Parameter> 
```

#### Атрибуты тэга `<Parameter>` <a href="#attributes_tag_set_parameter" id="attributes_tag_set_parameter"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Название параметра формы.</p><p></p><p>Обязательный атрибут. Значение атрибута <code>Name</code>: название одного из явных параметров, описанных в форме, или неявных.</p></td></tr></tbody></table>
