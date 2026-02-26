---
description: Условие типа ComparisonCondition; сравнение значения с не NULL.
---

# IsNotNullCondition

## Шаблон IsNotNullCondition <a href="#template_is_not_null_condition" id="template_is_not_null_condition"></a>

```xml
<Condition Name="" Type="IsNotNullCondition" Assembly="Conditions">
  <!--Тэги, общие для всех условий-->
  <AlwaysChange Value="" />
  <!--Тэги, специфичные для ComparisonCondition-->
  <Items>
    <Item></Item>
  </Items>
  <DataType Type="" />
  <Satisfy MinCount="" MaxCount="" />
  <Comparison Type="" Order="" />
  <!--Тэги, специфичные для IsNotNullCondition-->
</Condition>
```

## Описание IsNotNullCondition <a href="#description_is_not_null_condition" id="description_is_not_null_condition"></a>

```xml
<Condition Name="IsNotNullConditionName" Type="IsNotNullCondition" Assembly="Conditions">
  <!--Тэги, общие для всех условий-->
  <!--Тэги, специфичные для ComparisonCondition-->
  <!--Тэги, специфичные для IsNotNullCondition-->
</Condition>
```

## Тэги, специфичные для IsNotNullCondition <a href="#tags_is_not_null_condition" id="tags_is_not_null_condition"></a>

### Items <a href="#items" id="items"></a>

Содержит значение, которые сравнивается с не NULL.

Необязательный тэг. Значение тэга `<Items>`: список тэгов [`<Item>`](is_not_null_condition.md#items_item)(количество ожидаемых тэгов: 1).

Если тэг `<Items>` отсутствует, то условие всегда будет иметь значение False.

```xml
<Items>
  <Item>Value1</Item>
</Items>
```

#### Тэг `<Item>` <a href="#items_item" id="items_item"></a>

Сравниваемое значение.

Необязательный тэг. Значение тэга `<Item>`: любое значение.
