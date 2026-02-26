---
description: Условие с логическим значением.
---

# Conditions

## Описание Condition <a href="#description_condition" id="description_condition"></a>

Условие имеет логическое значение.

```xml
<Condition Name="ConditionName" Type="ConditionType" Assembly="ConditionAssembly">
  <!--Тэги, общие для всех условий-->
  <!--Тэги, специфичные для определенного условия (зависит от типа)-->
</Condition>
```

#### Атрибуты Condition <a href="#attributes_condition" id="attributes_condition"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="460.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Обязательный атрибут.</p><p></p><p>Название условия.</p></td></tr><tr><td align="center">Type</td><td><p>Обязательный атрибут.</p><p></p><p>Название типа условия в сборке.</p></td></tr><tr><td align="center">Assembly</td><td><p>Обязательный атрибут.</p><p></p><p>Название сборки (библиотека).</p></td></tr></tbody></table>

{% hint style="info" %}
Все условия можно поделить на две группы: условия сравнения и событийные условия.

**Условия сравнения** рассылают уведомления своим подписчикам, только если результат условия изменится. К условиям сравнения относятся все условия, в которых происходит сравнение значений: [EqualCondition](comparison_condition/equal_condition.md), [IsNullCondition](comparison_condition/is_null_condition.md) и подобные. Также к условия сравнения относится условие [NestedCondition](nested_condition.md).

**Событийные условия** рассылают уведомления каждый раз когда происходит событие. К ним относятся условия [CellDoubleClickCondition](/broken/pages/-M_yOkwiQuOVd5ZkGd8V), [FormClosingCondition ](/broken/pages/-M_yO_b4wzX1siuUO8ki)и подобные.
{% endhint %}

## Тэги, общие для всех условий <a href="#common_tags" id="common_tags"></a>

### AlwaysChange <a href="#always_change" id="always_change"></a>

Признак, определяющий, будет ли условие генерировать событие изменения своего значения в том случае, если операнды условия были изменены, но само значение условия не изменилось.

Необязательный тэг. Значение тэга `<AlwaysChange>`: не ожидается.

Если тэг `<AlwaysChange>` отсутствует, то для атрибута `Value` используется значение False.

```xml
<AlwaysChange Value="False" />
```

#### Атрибуты тэга `<AlwaysChange>` <a href="#attributes_tag_always_change" id="attributes_tag_always_change"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="460.3333333333333"></th></tr></thead><tbody><tr><td align="center">Value</td><td><p>Значение указанного признака.</p><p></p><p>Обязательный атрибут. Ожидается логическое значение.</p></td></tr></tbody></table>
