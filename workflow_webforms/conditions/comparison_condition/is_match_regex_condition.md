---
description: >-
  Условие типа ComparisonCondition; проверка на соответствие регулярному
  выражению.
---

# IsMatchRegexCondition

## Шаблон IsMatchRegexCondition <a href="#template_is_match_regex_condition" id="template_is_match_regex_condition"></a>

```xml
<Condition Name="" Type="IsMatchRegexCondition" Assembly="Conditions">
  <!--Тэги, общие для всех условий-->
  <AlwaysChange Value=""/>
  <!--Тэги, специфичные для ComparisonCondition-->
  <Items>
    <Item></Item>
  </Items>
  <Satisfy MinCount="" MaxCount="" />
  <Comparison Type="" Order="" />
  <!--Тэги, специфичные для IsMatchRegexCondition-->
  <Regex></Regex>
</Condition>
```

## Описание IsMatchRegexCondition <a href="#description_is_match_regex_condition" id="description_is_match_regex_condition"></a>

```xml
<Condition Name="IsMatchRegexConditionName" Type="IsMatchRegexCondition" Assembly="Conditions">
  <!--Тэги, общие для всех условий-->
  <!--Тэги, специфичные для ComparisonCondition-->
  <!--Тэги, специфичные для IsMatchRegexCondition-->
</Condition>
```

## Тэги, специфичные для IsMatchRegexCondition <a href="#tags_is_match_regex_condition" id="tags_is_match_regex_condition"></a>

### Regex <a href="#regex" id="regex"></a>

Регулярное выражение для проверки.

Обязательный тэг. Любое значение, которое будет переведено в текстовое.

Например, регулярное выражение:\
"`^[_a-z0-9-]+(\.[_a-z0-9-]+)*@[a-z0-9-]+(\.[a-z0-9-]+)*(\.[a-z]{2,4})$`" - проверяет на соответствие корректному E-mail-адресу.

```xml
<Regex>^[_a-z0-9-]+(\.[_a-z0-9-]+)*@[a-z0-9-]+(\.[a-z0-9-]+)*(\.[a-z]{2,4})$</Regex>
```
