---
description: Условие типа ComparisonCondition; сравнение значений на "не больше".
---

# NotGreaterCondition

## Шаблон NotGreaterCondition <a href="#template_not_greater_condition" id="template_not_greater_condition"></a>

```xml
<Condition Name="" Type="NotGreaterCondition" Assembly="Conditions">
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
  <!--Тэги, специфичные для NotGreaterCondition-->
</Condition>
```

## Описание NotGreaterCondition <a href="#description_not_greater_condition" id="description_not_greater_condition"></a>

```xml
<Condition Name="NotGreaterConditionName" Type="NotGreaterCondition" Assembly="Conditions">
  <!--Тэги, общие для всех условий-->
  <!--Тэги, специфичные для ComparisonCondition-->
  <!--Тэги, специфичные для NotGreaterCondition-->
</Condition>
```

## Тэги, специфичные для NotGreaterCondition <a href="#tags_not_greater_condition" id="tags_not_greater_condition"></a>

### Items <a href="#items" id="items"></a>

Содержит значения, которые сравниваются на "не больше".

Необязательный тэг. Значение тэга `<Items>`: список тэгов [`<Item>`](not_greater_condition.md#items_item)(количество ожидаемых тэгов: 2).

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
