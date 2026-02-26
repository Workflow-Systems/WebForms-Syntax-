---
description: Событийное условие; срабатывает при изменении значения.
---

# ChangedCondition

## Шаблон ChangedCondition <a href="#template_changed_condition" id="template_changed_condition"></a>

```xml
<Condition Name="" Type="ChangedCondition" Assembly="Conditions">
  <!--Тэги, общие для всех условий-->
  <AlwaysChange Value="" />
  <!--Тэги, специфичные для ChangedCondition-->
  <Items>
    <Item></Item>
  </Items>
</Condition>
```

## Описание ChangedCondition <a href="#description_changed_condition" id="description_changed_condition"></a>

```xml
<Condition Name="ChangedConditionName" Type="ChangedCondition" Assembly="Conditions">
  <!--Тэги, общие для всех условий-->
  <!--Тэги, специфичные для ChangedCondition-->
</Condition>
```

## Тэги, специфичные для ChangedCondition <a href="#tags_changed_condition" id="tags_changed_condition"></a>

### Items <a href="#items" id="items"></a>

Значения для определения изменений хотя бы одного из них.

Обязательный тэг. Значение тэга `<Items>`: список тэгов [`<Item>`](changed_condition.md#items_item).

```xml
<Items>
  <Item>Value1</Item>
  <Item>Value2</Item>
</Items>
```

#### Тэг `<Item>` <a href="#items_item" id="items_item"></a>

Значение для определения его изменений.

Необязательный тэг. Значение тэг `<Item>`: любое значение.
