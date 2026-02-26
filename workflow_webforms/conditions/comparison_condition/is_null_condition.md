---
description: Условие типа ComparisonCondition; сравнение значения с NULL.
---

# IsNullCondition

## Шаблон IsNullCondition <a href="#template_is_null_condition" id="template_is_null_condition"></a>

```xml
<Condition Name="" Type="IsNullCondition" Assembly="Conditions">
  <!--Тэги, общие для всех условий-->
  <AlwaysChange Value="" />
  <!--Тэги, специфичные для ComparisonCondition-->
  <Items>
    <Item></Item>
  </Items>
  <DataType Type="" />
  <Satisfy MinCount="" MaxCount="" />
  <Comparison Type="" Order="" />
  <!--Тэги, специфичные для IsNullCondition-->
</Condition>
```

## Описание IsNullCondition <a href="#description_is_null_condition" id="description_is_null_condition"></a>

```xml
<Condition Name="IsNullConditionName" Type="IsNullCondition" Assembly="Conditions">
  <!--Тэги, общие для всех условий-->
  <!--Тэги, специфичные для ComparisonCondition-->
  <!--Тэги, специфичные для IsNullCondition-->
</Condition>
```

## Тэги, специфичные для IsNullCondition <a href="#tags_is_null_condition" id="tags_is_null_condition"></a>

### Items <a href="#items" id="items"></a>

Содержит значение, которое сравнивается с NULL.

Необязательный тэг. Значение тэга `<Items>`: список тэгов [`<Item>`](is_null_condition.md#items_item)(количество ожидаемых тэгов: 1).

Если тэг `<Items>` отсутствует, то условие всегда будет иметь значение False.

```xml
<Items>
  <Item>Value1</Item>
</Items>
```

#### Тэг `<Item>` <a href="#items_item" id="items_item"></a>

Сравниваемое значение.

Необязательный тэг. Значение тэга `<Item>`: любое значение.
