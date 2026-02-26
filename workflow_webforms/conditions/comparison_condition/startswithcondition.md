---
description: >-
  Условие типа ComparisonCondition; проверка на начало значения с определенного
  текста.
---

# StartsWithCondition

## Шаблон StartsWithCondition <a href="#template_starts_with_condition" id="template_starts_with_condition"></a>

```xml
<Condition Name="" Type="StartsWithCondition" Assembly="Conditions">
  <!--Тэги, общие для всех условий-->
  <AlwaysChange Value="" />
  <!--Тэги, специфичные для ComparisonCondition-->
  <Items>
    <Item></Item>
    <Item></Item>
  </Items>
  <DataType Type="" />
  <Satisfy MinCount="" MaxCount="" />
  <Comparison Type="" Order="" />
  <!--Тэги, специфичные для StartsWithCondition-->
</Condition>
```

## Описание StartsWithCondition <a href="#description_starts_with_condition" id="description_starts_with_condition"></a>

```xml
<Condition Name="StartsWithConditionName" Type="StartsWithCondition" Assembly="Conditions">
  <!--Тэги, общие для всех условий-->
  <!--Тэги, специфичные для ComparisonCondition-->
  <!--Тэги, специфичные для StartsWithCondition-->
</Condition>
```

## Тэги, специфичные для StartsWithCondition <a href="#tags_starts_with_condition" id="tags_starts_with_condition"></a>

### DataType <a href="#data_type" id="data_type"></a>

Для данного типа условий любой указанный тип будет переводится в текстовый.

```xml
<DataType Type="DataTypeName" />
```

#### Атрибуты тэга `<DataType>` <a href="#attributes_tag_data_type" id="attributes_tag_data_type"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="463.3333333333333"></th></tr></thead><tbody><tr><td align="center">Type</td><td><p>Название типа данных.</p><p></p><p>Обязательный атрибут. Ожидается название одного из <a href="/broken/pages/-MaRtBVKMO4VR0KCghVx">типов данных</a>.</p></td></tr></tbody></table>

### Items <a href="#items" id="items"></a>

Содержит значение, которое проверяется на предмет, начинается ли оно с определенного текста.

Необязательный тэг. Значение тэга `<Items>`: список тэгов [`<Item>`](startswithcondition.md#items_item)(количество ожидаемых тэгов: 2).

Если тэг `<Items>` отсутствует, то условие всегда будет иметь значение False.

```xml
<Items>
  <Item>Value1</Item>
  <Item>Value2</Item>
</Items>
```

#### Тэг `<Item>` <a href="#items_item" id="items_item"></a>

Первый тэг `<Item>` - проверяемое значение.

Второй тэг `<Item>` - искомый текст.

Необязательные тэги. Значение тэгов `<Item>`: любое значение будет переведено в текстовое.
