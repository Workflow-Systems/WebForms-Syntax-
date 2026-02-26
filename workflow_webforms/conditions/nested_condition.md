---
description: >-
  Условие; состоит из логического выражения, составленного из значений других
  условий.
---

# NestedCondition

## Шаблон NestedCondition <a href="#template_nested_condition" id="template_nested_condition"></a>

```xml
<Condition Name="" Type="NestedCondition" Assembly="Conditions">
  <!--Тэги, общие для всех условий-->
  <AlwaysChange Value="" />
  <!--Тэги, специфичные для NestedCondition-->
  <ConditionExpression>
    <Or>
      <Not>
        <And>
          <Condition Name="" />
          <Condition Name="" />
          <Condition Name="" />
        </And>
      </Not>
      <And>
        <Condition Name="" />
        <Condition Name="" />
      </And>
    </Or>
  </ConditionExpression>
</Condition>
```

## Описание NestedCondition <a href="#description_nested_condition" id="description_nested_condition"></a>

```xml
<Condition Name="NestedConditionName" Type="NestedCondition" Assembly="Conditions">
  <!--Тэги, общие для всех условий-->
  <!--Тэги, специфичные для NestedCondition-->
</Condition>
```

## Тэги, специфичные для NestedCondition <a href="#tags_nested_condition" id="tags_nested_condition"></a>

### ConditionExpression <a href="#condition_expression" id="condition_expression"></a>

Значение тэга `<ConditionExpression>`: список тэгов [`<And>`](nested_condition.md#condition_expression_and), [`<Or>`](nested_condition.md#condition_expression_or) и [`<Not>`](nested_condition.md#condition_expression_not) или тэг [`<Condition>`](nested_condition.md#condition_expression_condition).

```xml
<ConditionExpression>
  <Or>
    <Not>
      <And>
        <Condition Name="ConditionName1" />
        <Condition Name="ConditionName2" />
        <Condition Name="ConditionName3" />
      </And>
    </Not>
    <And>
      <Condition Name="ConditionName4" />
      <Condition Name="ConditionName5" />
    </And>
  </Or>
</ConditionExpression>
```

#### Тэг `<And>` <a href="#condition_expression_and" id="condition_expression_and"></a>

Логическое умножение нескольких условий.

Необязательный тэг. Значение тэга `<And>`: список тэгов [`<Condition>`](nested_condition.md#condition_expression_condition), `<And>`, [`<Or>`](nested_condition.md#condition_expression_or) и [`<Not>`](nested_condition.md#condition_expression_not).

#### Тэг `<Or>` <a href="#condition_expression_or" id="condition_expression_or"></a>

Логическое сложение нескольких условий.

Необязательный тэг. Значение тэга `<Or>`: список тэгов [`<Condition>`](nested_condition.md#condition_expression_condition), [`<And>`](nested_condition.md#condition_expression_and), `<Or>` и [`<Not>`](nested_condition.md#condition_expression_not).

#### Тэг `<Not>` <a href="#condition_expression_not" id="condition_expression_not"></a>

Логическое отрицание одного условия.

Необязательный тэг. Значение тэга `<Not>`: тэг [`<Condition>`](nested_condition.md#condition_expression_condition), [`<And>`](nested_condition.md#condition_expression_and), [`<Or>`](nested_condition.md#condition_expression_or) или `<Not>`.

#### Тэг `<Condition>` <a href="#condition_expression_condition" id="condition_expression_condition"></a>

Условие.

Необязательный тэг. Значение тэга `<Condition>`: не ожидается.

#### Атрибуты тэга `<Condition>` <a href="#attributes_tag_condition_expression_condition" id="attributes_tag_condition_expression_condition"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="472.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Название условия.</p><p></p><p>Обязательный атрибут. Ожидается название одного из условий, описанных в форме.</p></td></tr></tbody></table>
