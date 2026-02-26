---
description: >-
  Событийное условие; срабатывает, когда одно из загружающих соединений начало
  загрузку.
---

# DataConnectionsLoadingCondition

## Шаблон DataConnectionsLoadingCondition <a href="#template_data_connections_loading_condition" id="template_data_connections_loading_condition"></a>

```xml
<Condition Name="" Type="DataConnectionsLoadingCondition" Assembly="Conditions">
  <!--Тэги, общие для всех условий-->
  <!--Тэги, специфичные для DataConnectionsLoadingCondition-->
  <DataConnections>
    <DataConnection Name="" />
  </DataConnections>
</Condition>
```

## Описание DataConnectionsLoadingCondition <a href="#description_data_connections_loading_condition" id="description_data_connections_loading_condition"></a>

```xml
<Condition Name="DataConnectionsLoadingConditionName" Type="DataConnectionsLoadingCondition" Assembly="Conditions">
  <!--Тэги, общие для всех условий-->
  <!--Тэги, специфичные для DataConnectionsLoadingCondition-->
</Condition>
```

{% hint style="info" %}
В следующий раз условие готово к срабатыванию после того, как все соединения были загружены.
{% endhint %}

## Тэги, специфичные для DataConnectionsLoadingCondition <a href="#tags_data_connections_loading_condition" id="tags_data_connections_loading_condition"></a>

### DataConnections <a href="#data_connections" id="data_connections"></a>

Список загружающих [соединений с данными](../../dataconnections/).

Обязательный тэг. Значение тэга `<DataConnections>`: список тэгов [`<DataConnection>`](dataconnectionsloadingcondition.md#data_connections_data_connection).

```xml
<DataConnections>
  <DataConnection Name="DataConnectionName" />
</DataConnections>
```

#### Тэг `<DataConnection>` <a href="#data_connections_data_connection" id="data_connections_data_connection"></a>

Загружающее [соединение с данными](../../dataconnections/).

Обязательный тэг. Значение тэга `<DataConnections>`: не ожидается.

#### Атрибуты тэга `<DataConnection>` <a href="#attributes_tag_data_connections_data_connection" id="attributes_tag_data_connections_data_connection"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="463.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Название загружающего соединения с данными.</p><p></p><p>Обязательный атрибут. Ожидается название одного из загружающих соединений с данными, описанных в форме.</p></td></tr></tbody></table>
