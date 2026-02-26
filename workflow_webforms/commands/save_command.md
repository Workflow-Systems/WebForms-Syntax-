---
description: >-
  Команда; отправляет данные на сервер посредством отправляющих соединений с
  данными.
---

# SaveCommand

## Шаблон SaveCommand <a href="#template_save_command" id="template_save_command"></a>

```xml
<Command Name="" Type="SaveCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <Condition Name="" />
  <Lock Value="" />
  <!--Тэги, специфичные для SaveCommand-->
  <DataConnections>
    <DataConnection Name="" />
  </DataConnections>
</Command>
```

## Описание SaveCommand <a href="#description_save_command" id="description_save_command"></a>

```xml
<Command Name="SaveCommandName" Type="SaveCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <!--Тэги, специфичные для SaveCommand-->
</Command>
```

### Результат выполнения SaveCommand <a href="#result_save_command" id="result_save_command"></a>

#### Value <a href="#result_value" id="result_value"></a>

Значение, возвращенное с сервера первым запросом из первого соединения с данными для отправки, указанного в команде.

## Тэги, специфичные для SaveCommand <a href="#tags_save_command" id="tags_save_command"></a>

### DataConnections <a href="#data_connections" id="data_connections"></a>

Отправляющие соединения с данными, которые будут отправлять данные на сервер.

Необязательный тэг. Значение тэга `<DataConnections>`: список тэгов [`<DataConnection>`](save_command.md#data_connections_data_connection).

```xml
<DataConnections>
  <DataConnection Name="DataConnectionName1" />
  <DataConnection Name="DataConnectionName2" />
</DataConnections>
```

#### Тэг `<DataConnection>` <a href="#data_connections_data_connection" id="data_connections_data_connection"></a>

Отправляющее [соединение с данными](../dataconnections/), которое будут отправлять данные на сервер.

Необязательный тэг.&#x20;

#### Атрибуты тэга `<DataConnection>` <a href="#attributes_tag_data_connections_data_connection" id="attributes_tag_data_connections_data_connection"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Название отправляющего соединения с данными, которое будут отправлять данные на сервер.</p><p></p><p>Обязательный атрибут. Значение атрибута <code>Name</code>: название одного из отправляющих соединений с данными, описанных в форме.</p></td></tr></tbody></table>
