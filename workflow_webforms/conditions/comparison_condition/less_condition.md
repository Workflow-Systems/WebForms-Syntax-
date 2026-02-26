---
description: Условие типа ComparisonCondition; сравнение значений на "меньше".
---

# LessCondition

## Шаблон LessCondition <a href="#template_less_condition" id="template_less_condition"></a>

```xml
<Condition Name="" Type="LessCondition" Assembly="Conditions">
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
  <!--Тэги, специфичные для LessCondition-->
</Condition>
```

## Описание LessCondition <a href="#description_less_condition" id="description_less_condition"></a>

```xml
<Condition Name="LessConditionName" Type="LessCondition" Assembly="Conditions">
  <!--Тэги, общие для всех условий-->
  <!--Тэги, специфичные для ComparisonCondition-->
  <!--Тэги, специфичные для LessCondition-->
</Condition>
```

## Тэги, специфичные для LessCondition <a href="#tags_less_condition" id="tags_less_condition"></a>

### Items <a href="#items" id="items"></a>

Содержит значения, которые сравниваются на "меньше".

Необязательный тэг. Значение тэга `<Items>`: список тэгов [`<Item>`](less_condition.md#items_item)(количество ожидаемых тэгов: 2).

Если тэг `<Items>` отсутствует, то условие всегда будет иметь значение False.

```xml
<Items>
  <Item>Value1</Item>
  <Item>Value2</Item>
</Items>
```

#### Тэг `<Item>` <a href="#items_item" id="items_item"></a>

Первый тэг `<Item>` - первое значение.

Второй тэг `<Item>` - второе значение.

Необязательные тэги. Значение тэгов `<Item>`: любое значение.
