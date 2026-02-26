---
description: Событийное условие; срабатывает при двойном клике на ячейку таблицы.
---

# CellDoubleClickCondition

## Шаблон CellDoubleClickCondition <a href="#template_cell_double_click_condition" id="template_cell_double_click_condition"></a>

```xml
<Condition Name="" Type="CellDoubleClickCondition" Assembly="Conditions">
  <!--Тэги, общие для всех условий-->
  <AlwaysChange Value="" />
  <!--Тэги, специфичные для CellDoubleClickCondition-->
  <Table Name="" />
</Condition>
```

## Описание CellDoubleClickCondition <a href="#description_cell_double_click_condition" id="description_cell_double_click_condition"></a>

```xml
<Condition Name="CellDoubleClickConditionName" Type="CellDoubleClickCondition" Assembly="Conditions">
  <!--Тэги, общие для всех условий-->
  <!--Тэги, специфичные для CellDoubleClickCondition-->
</Condition>
```

## Тэги, специфичные для CellDoubleClickCondition <a href="#tags_cell_double_click_condition" id="tags_cell_double_click_condition"></a>

### Table <a href="#table" id="table"></a>

[Таблица](../../objects/databasetable/), в которой срабатывает событие двойного клика на ячейке.

Обязательный тэг. Значение тэга `<Table>`: не ожидается.

```xml
<Table Name="TableName" />
```

#### Атрибуты тэга `<Table>` <a href="#attributes_tag_table" id="attributes_tag_table"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="463.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Название объекта таблицы.</p><p></p><p>Обязательный атрибут. Ожидается название одного из объектов таблиц, описанных в форме.</p></td></tr></tbody></table>
