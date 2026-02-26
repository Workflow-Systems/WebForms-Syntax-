---
description: >-
  Условие типа ComparisonCondition; проверка значения на принадлежность к
  определенному типу данных.
---

# IsDataTypeCondition

## Шаблон IsDataTypeCondition <a href="#template_is_data_type_condition" id="template_is_data_type_condition"></a>

```xml
<Condition Name="" Type="IsDataTypeCondition" Assembly="Conditions">
  <!--Тэги, общие для всех условий-->
  <AlwaysChange Value="" />
  <!--Тэги, специфичные для ComparisonCondition-->
  <Items>
    <Item></Item>
  </Items>
  <DataType Type="" />
  <Satisfy MinCount="" MaxCount="" />
  <Comparison Type="" Order="" />
  <!--Тэги, специфичные для IsDataTypeCondition-->
</Condition>
```

## Описание IsDataTypeCondition <a href="#description_is_data_type_condition" id="description_is_data_type_condition"></a>

```xml
<Condition Name="IsDataTypeConditionName" Type="IsDataTypeCondition" Assembly="Conditions">
  <!--Тэги, общие для всех условий-->
  <!--Тэги, специфичные для ComparisonCondition-->
  <!--Тэги, специфичные для IsDataTypeCondition-->
</Condition>
```

## Тэги, специфичные для IsDataTypeCondition <a href="#tags_is_data_type_condition" id="tags_is_data_type_condition"></a>

### DataType <a href="#data_type" id="data_type"></a>

[Тип данных](/broken/pages/-MaRtBVKMO4VR0KCghVx), на принадлежность к которому будет осуществляться проверка значения.

```xml
<DataType Type="DataTypeName" />
```

#### Атрибуты тэга `<DataType>` <a href="#attributes_tag_data_type" id="attributes_tag_data_type"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="463.3333333333333"></th></tr></thead><tbody><tr><td align="center">Type</td><td><p>Название типа данных.</p><p></p><p>Обязательный атрибут. Ожидается название одного из <a href="/broken/pages/-MaRtBVKMO4VR0KCghVx">типов данных</a>.</p></td></tr></tbody></table>

### Items <a href="#items" id="items"></a>

Содержит значение, которое проверяется на предмет принадлежности к определенному типу данных.

Необязательный тэг. Значение тэга `<Items>`: список тэгов [`<Item>`](is_data_type_condition.md#items_item)(количество ожидаемых тэгов: 1).

Если тэг `<Items>` отсутствует, то условие всегда будет иметь значение False.

```xml
<Items>
  <Item>Value2</Item>
</Items>
```

#### Тэг `<Item>` <a href="#items_item" id="items_item"></a>

Проверяемое значение.

Необязательный тэг. Значение тэга `<Item>`: любое значение.
