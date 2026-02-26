---
description: Событийное условие; срабатывает при клике на ячейку таблицы.
---

# CellClickCondition

## Шаблон CellClickCondition <a href="#template_cell_click_condition" id="template_cell_click_condition"></a>

```xml
<Condition Name="" Type="CellClickCondition" Assembly="Conditions">
  <!--Тэги, общие для всех условий-->
  <AlwaysChange Value="" />
  <!--Тэги, специфичные для CellClickCondition-->
  <Table Name="" />
</Condition>
```

## Описание CellClickCondition <a href="#description_cell_click_condition" id="description_cell_click_condition"></a>

```xml
<Condition Name="CellClickConditionName" Type="CellClickCondition" Assembly="Conditions">
  <!--Тэги, общие для всех условий-->
  <!--Тэги, специфичные для CellClickCondition-->
</Condition>
```

## Тэги, специфичные для CellClickCondition <a href="#tags_cell_click_condition" id="tags_cell_click_condition"></a>

### Table <a href="#table" id="table"></a>

[Таблица](../../objects/databasetable/), в которой срабатывает событие клика на ячейке.

Обязательный тэг. Значение тэга `<Table>`: не ожидается.

```xml
<Table Name="TableName" />
```

#### Атрибуты тэга `<Table>` <a href="#attributes_tag_table" id="attributes_tag_table"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="463.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Название объекта таблицы.</p><p></p><p>Обязательный атрибут. Ожидается название одного из объектов таблиц, описанных в форме.</p></td></tr></tbody></table>
