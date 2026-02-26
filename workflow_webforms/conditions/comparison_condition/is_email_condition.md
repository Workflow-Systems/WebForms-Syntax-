---
description: >-
  Условие типа ComparisonCondition; проверка на корректное значение
  Email-адреса.
---

# IsEmailCondition

## Шаблон IsEmailCondition <a href="#template_is_email_condition" id="template_is_email_condition"></a>

```xml
<Condition Name="" Type="IsEmailCondition" Assembly="Conditions">
  <!--Тэги, общие для всех условий-->
  <AlwaysChange Value="" />
  <!--Тэги, специфичные для ComparisonCondition-->
  <Items>
    <Item></Item>
  </Items>
  <Satisfy MinCount="" MaxCount="" />
  <Comparison Type="" Order="" />
  <!--Тэги, специфичные для IsEmailCondition-->
</Condition>
```

## Описание IsEmailCondition <a href="#description_is_email_condition" id="description_is_email_condition"></a>

```xml
<Condition Name="IsEmailConditionName" Type="IsEmailCondition" Assembly="Conditions">
  <!--Тэги, общие для всех условий-->
  <!--Тэги, специфичные для ComparisonCondition-->
  <!--Тэги, специфичные для IsEmailCondition-->
</Condition>
```

{% hint style="info" %}
Проверка осуществляется с помощью регулярного выражения:

`^\w+([-+.']\w+)*@\w+([-.]\w+)*\.\w+([-.]\w+)*$`
{% endhint %}
