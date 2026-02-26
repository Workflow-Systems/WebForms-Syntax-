---
description: Условие типа ComparisonCondition; сравнение значений на "равно".
---

# EqualCondition

## Шаблон EqualCondition <a href="#template_equal_condition" id="template_equal_condition"></a>

```xml
<Condition Name="" Type="EqualCondition" Assembly="Conditions">
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
  <!--Тэги, специфичные для EqualCondition-->
</Condition>
```

## Описание EqualCondition <a href="#description_equal_condition" id="description_equal_condition"></a>

```xml
<Condition Name="EqualConditionName" Type="EqualCondition" Assembly="Conditions">
  <!--Тэги, общие для всех условий-->
  <!--Тэги, специфичные для ComparisonCondition-->
  <!--Тэги, специфичные для EqualCondition-->
</Condition>
```

## Тэги, специфичные для EqualCondition <a href="#tags_equal_condition" id="tags_equal_condition"></a>

### Items <a href="#items" id="items"></a>

Значения, которые сравниваются на "равно".

Необязательный тэг. Значение тэга `<Items>`: список тэгов [`<Item>`](equal_condition.md#items_item)(количество ожидаемых тэгов: от 1).

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
