---
description: Условие типа ComparisonCondition; сравнение значений на "не равно".
---

# NotEqualCondition

## Шаблон NotEqualCondition <a href="#template_not_equal_condition" id="template_not_equal_condition"></a>

```xml
<Condition Name="" Type="NotEqualCondition" Assembly="Conditions">
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
  <!--Тэги, специфичные для NotEqualCondition-->
</Condition>
```

## Описание NotEqualCondition <a href="#description_not_equal_condition" id="description_not_equal_condition"></a>

```xml
<Condition Name="NotEqualConditionName" Type="NotEqualCondition" Assembly="Conditions">
  <!--Тэги, общие для всех условий-->
  <!--Тэги, специфичные для ComparisonCondition-->
  <!--Тэги, специфичные для NotEqualCondition-->
</Condition>
```

## Тэги, специфичные для NotEqualCondition <a href="#tags_not_equal_condition" id="tags_not_equal_condition"></a>

### Items <a href="#items" id="items"></a>

Значения, которые сравниваются на "не равно".

Необязательный тэг. Значение тэга `<Items>`: список тэгов [`<Item>`](not_equal_condition.md#items_item) (количество ожидаемых тэгов: от 1).

Если тэг `<Items>` отсутствует, то условие всегда будет иметь значение False.

```xml
<Items>
  <Item>Value1</Item>
  <Item>Value2</Item>
  <Item>Value3</Item>
</Items>
```

#### Тэг `<Item>` <a href="#items_item" id="items_item"></a>

Значение для сравнения.

Необязательный тэг. Значение тэга `<Item>`: любое значение.
