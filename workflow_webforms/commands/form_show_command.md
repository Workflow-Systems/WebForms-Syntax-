---
description: Команда; открывает форму (web-страницу).
---

# FormShowCommand

## Шаблон FormShowCommand <a href="#template_form_show_command" id="template_form_show_command"></a>

```xml
<Command Name="" Type="FormShowCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <Condition Name="" />
  <Lock Value="" />
  <!--Тэги, специфичные для FormShowCommand-->
  <Xml Type="Path"></Xml>
  <OpenInNewWindow Value="" />
  <Parameters>
    <Parameter Name="" />
  </Parameters>
</Command>
```

## Описание FormShowCommand <a href="#description_form_show_command" id="description_form_show_command"></a>

```xml
<Command Name="FormShowCommandName" Type="FormShowCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <!--Тэги, специфичные для FormShowCommand-->
</Command>
```

Команда не имеет результата.

## Тэги, специфичные для FormShowCommand <a href="#tags_form_show_command" id="tags_form_show_command"></a>

### Xml <a href="#xml" id="xml"></a>

Страница, которая будет открыта.

Обязательный тэг. Значение тэга `<Xml>`: url-адрес страницы.

```xml
<Xml Type="Path">Path</Xml>
```

#### Атрибуты тэга `<Xml>` <a href="#attributes_tag_xml" id="attributes_tag_xml"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="449.3333333333333"></th></tr></thead><tbody><tr><td align="center">Type</td><td><p>Название типа загрузки xml-кода.</p><p></p><p>Обязательный атрибут. Ожидается название одного из <a href="form_show_command.md#xml_code_loading_types">типов загрузки</a> xml-кода.</p></td></tr></tbody></table>

#### Типы загрузки xml-кода <a href="#xml_code_loading_types" id="xml_code_loading_types"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="449.3333333333333"></th></tr></thead><tbody><tr><td align="center">Path</td><td>Загрузка кода из файла, расположенного по определенному пути.</td></tr></tbody></table>

Значение тэга `<Xml>` при атрибуте `Type`, равным Path: любое значение будет переведено в текстовое.

### OpenInNewWindow <a href="#open_in_new_window" id="open_in_new_window"></a>

Признак, определяющий, будет ли страница открыта в новой вкладке.

Необязательный тэг. Значение тэга `<OpenInNewWindow>`: не ожидается.

Если тэг `<OpenInNewWindow>` отсутствует, то для атрибута `Value` используется значение True.

```xml
<OpenInNewWindow Value="True" />
```

#### Атрибуты тэга `<OpenInNewWindow>` <a href="#attributes_tag_open_in_new_window" id="attributes_tag_open_in_new_window"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="449.3333333333333"></th></tr></thead><tbody><tr><td align="center">Value</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается логическое значение.</p></td></tr></tbody></table>

### Parameters <a href="#parameters" id="parameters"></a>

Параметры, которые будут переданы на дочернюю форму.

Необязательный тэг. Значение тэга `<Parameters>`: список тэгов `<Parameter>`.

```xml
<Parameters>
  <Parameter Name="ParameterName1">ParameterValue1</Parameter>
  <Parameter Name="ParameterName2">ParameterValue2</Parameter>
</Parameters>
```

#### Тэг `<Parameter>` <a href="#parameters_parameter" id="parameters_parameter"></a>

Параметр, который будет передан страницу.

Необязательный тэг. Значение тэга `<Parameter>`: любое значение.

#### Атрибуты тэга `<Parameter>` <a href="#attributes_tag_parameters_parameter" id="attributes_tag_parameters_parameter"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="449.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Название параметра.</p><p></p><p>Обязательный атрибут. Значение атрибута <code>Name</code>: название одного из явных или неявных параметров дочерней формы.</p></td></tr></tbody></table>
