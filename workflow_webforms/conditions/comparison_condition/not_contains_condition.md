---
description: >-
  Условие типа ComparisonCondition; проверка на не вхождение одного текста в
  другой.
---

# NotContainsCondition

## Шаблон NotContainsCondition <a href="#template_not_contains_condition" id="template_not_contains_condition"></a>

```xml
<Condition Name="" Type="NotContainsCondition" Assembly="Conditions">
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
  <!--Тэги, специфичные для NotContainsCondition-->
</Condition>
```

## Описание NotContainsCondition <a href="#description_not_contains_condition" id="description_not_contains_condition"></a>

```xml
<Condition Name="NotContainsConditionName" Type="NotContainsCondition" Assembly="Conditions">
  <!--Тэги, общие для всех условий-->
  <!--Тэги, специфичные для ComparisonCondition-->
  <!--Тэги, специфичные для NotContainsCondition-->
</Condition>
```

## Тэги, специфичные для NotContainsCondition <a href="#tags_not_contains_condition" id="tags_not_contains_condition"></a>

### DataType <a href="#data_type" id="data_type"></a>

Для данного типа условий любой указанный тип будет переводится в текстовый.

```xml
<DataType Type="DataTypeName" />
```

#### Атрибуты тэга `<DataType>` <a href="#attributes_tag_data_type" id="attributes_tag_data_type"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="463.3333333333333"></th></tr></thead><tbody><tr><td align="center">Type</td><td><p>Название типа данных.</p><p></p><p>Обязательный атрибут. Ожидается название одного из <a href="/broken/pages/-MaRtBVKMO4VR0KCghVx">типов данных</a>.</p></td></tr></tbody></table>

### Items <a href="#items" id="items"></a>

Содержит значение, которое проверяется на предмет, что в него не входит определенный текст.

Необязательный тэг. Значение тэга `<Items>`: список тэгов [`<Item>`](not_contains_condition.md#items_item)(количество ожидаемых тэгов: 2).

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
