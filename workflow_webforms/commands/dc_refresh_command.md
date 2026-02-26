---
description: >-
  Команда; перезагружает данные с сервера в определенных загружающих соединениях
  с данными или точками доступа.
---

# DataConnectionRefreshCommand

## Шаблон DataConnectionRefreshCommand <a href="#template_dc_refresh_command" id="template_dc_refresh_command"></a>

```xml
<Command Name="" Type="DataConnectionRefreshCommand"  Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <Condition Name="" />
  <Lock Value="" />
  <!--Тэги, специфичные для DataConnectionRefreshCommand-->
  <Parallel></Parallel>
  <DataConnections>
    <DataConnection Name="" Query="" Packet="" PacketGroup=""/>
  </DataConnections>
</Command>
```

## Описание DataConnectionRefreshCommand <a href="#description_dc_refresh_command" id="description_dc_refresh_command"></a>

В команде используется пакетная загрузка запросов. Все [`<DataConnection>`](dc_refresh_command.md#data_connections_data_connection) добавляются в очередь загрузки, при этом очередь может подразделяется на несколько подочередей - для асинхронных и синхронных запросов.

```xml
<Command Name="DataConnectionRefreshCommandName" Type="DataConnectionRefreshCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <!--Тэги, специфичные для DataConnectionRefreshCommand-->
</Command>
```

### Результат выполнения DataConnectionRefreshCommand <a href="#result_dc_refresh_command" id="result_dc_refresh_command"></a>

Команда не имеет результата.

## Тэги, специфичные для DataConnectionRefreshCommand <a href="#tags_dc_refresh_command" id="tags_dc_refresh_command"></a>

### Parallel <a href="#parallel" id="parallel"></a>

В команде используется параллельная загрузка соединений в рамках одного пакета. Для того чтобы включить этот механизм нужно в тэге `<Parallel>` указать значение True. Если не указывать этот тэг, значение по умолчанию будет False.

Необязательный тэг. Ожидается логическое значение.

```xml
<Parallel>True</Parallel>
```

### DataConnections <a href="#data_connections" id="data_connections"></a>

Соединения, которые будут обновлены.

Необязательный тэг. Значение тэга `<DataConnections>`: список тэгов [`<DataConnection>`](dc_refresh_command.md#data_connections_data_connection).

```xml
<DataConnections>
  <DataConnection Name="DataConnectionName1" Query="QueryName1" Packet="True" PacketGroup="Group1"/>
  <DataConnection Name="DataConnectionName2" Query="QueryName2" Packet="True" PacketGroup="Group2"/>
</DataConnections>
```

#### Тэг `<DataConnection>` <a href="#data_connections_data_connection" id="data_connections_data_connection"></a>

Загружающие соединение, которое будет обновлено.

Необязательный тэг.

#### Атрибуты тэга `<DataConnection>` <a href="#attributes_tag_data_connections_data_connection" id="attributes_tag_data_connections_data_connection"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Название загружающего соединения.</p><p></p><p>Обязательный атрибут. Значение атрибута <code>Name</code>: название одного из загружающих соединений с данными или точками доступа, описанных в форме.</p></td></tr><tr><td align="center">Query</td><td><p>Название запроса загружающего соединения.</p><p></p><p>Необязательный атрибут. Значение атрибута <code>Query</code>: название одного из запросов загружающего соединения с данными.</p></td></tr><tr><td align="center">Packet</td><td><p>Признак, определяющий, будет ли текущий <code>&#x3C;DataConnection></code> загружен с использованием пакетной загрузки.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p></td></tr><tr><td align="center">PacketGroup</td><td><p>Название очереди в которой будет загружен запрос или соединение с данными.</p><p></p><p>Необязательный атрибут. Любое значение будет переведено в текстовое.</p></td></tr></tbody></table>
