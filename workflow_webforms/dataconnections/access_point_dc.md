---
description: >-
  Соединение с точками доступа; получает значения точек доступа с сервера, к
  которым затем можно обращаться на форме.
---

# AccessPointDataConnection

## Шаблон AccessPointDataConnection <a href="#template_access_point_data_connection" id="template_access_point_data_connection"></a>

```xml
<DataConnection Name="" Type="AccessPointDataConnection" Assembly="DataConnections">
  <Workflow Name="" />
  <AccessPoints>
    <AccessPoint Name="" />
  </AccessPoints>
</DataConnection>
```

## Описание AccessPointDataConnection <a href="#description_access_point_data_connection" id="description_access_point_data_connection"></a>

```xml
<DataConnection Name="AccessPointDataConnectionName" Type="AccessPointDataConnection" Assembly="DataConnections">
  <!--Тэги, общие для всех соединений с данными-->
  <!--Тэги, специфичные для AccessPointDataConnection-->
</DataConnection>
```

## Тэги, специфичные для AccessPointDataConnection <a href="#tags_access_point_data_connection" id="tags_access_point_data_connection"></a>

### Workflow <a href="#workflow" id="workflow"></a>

Процесс, в рамках которого происходит запрос значений точек доступа.

Обязательный тэг. Значение тэга `<Workflow>`: не ожидается.

```xml
<Workflow Name="WorkflowName" />
```

#### Атрибуты тэга `<Workflow>` <a href="#attributes_tag_workflow" id="attributes_tag_workflow"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="459.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Название процесса.</p><p></p><p>Обязательный атрибут. Ожидается название одного из процессов, расположенных на сервере и заголовочно описанных в базе.</p></td></tr></tbody></table>

### AccessPoints <a href="#access_points" id="access_points"></a>

Точки доступа.

Обязательный тэг. Значение тэга `<AccessPoints>`: список тэгов `<AccessPoint>`.

```xml
<AccessPoints>
  <AccessPoint Name="AccessPointName" />
</AccessPoints>
```

#### Тэг `<AccessPoint>` <a href="#access_points_access_point" id="access_points_access_point"></a>

Точка доступа.

Необязательный тэг. Значение тэга `<AccessPoint>`: не ожидается.

#### Атрибуты тэга `<AccessPoint>` <a href="#attributes_tag_access_points_access_point" id="attributes_tag_access_points_access_point"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="459.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Название точки доступа, которое описано в процессе на сервере и будет использоваться на форме.</p><p></p><p>Обязательный атрибут. Ожидается название одной из точек доступа, описанных в процессе на сервере.</p></td></tr></tbody></table>
