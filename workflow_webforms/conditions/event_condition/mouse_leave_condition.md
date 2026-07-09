---
description: >-
  Событийное условие; срабатывает при выходе курсора мыши из видимой области
  объекта.
---

# MouseLeaveCondition

## Шаблон MouseLeaveCondition <a href="#template_mouse_leave_condition" id="template_mouse_leave_condition"></a>

```xml
<Condition Name="" Type="MouseLeaveCondition" Assembly="Conditions">
  <!--Тэги, общие для всех условий-->
  <AlwaysChange Value="" />
  <!--Тэги, специфичные для MouseLeaveCondition-->
  <Object Name="" />
</Condition>
```

## Описание MouseLeaveCondition <a href="#description_mouse_leave_condition" id="description_mouse_leave_condition"></a>

```xml
<Condition Name="MouseLeaveConditionName" Type="MouseLeaveCondition" Assembly="Conditions">
  <!--Тэги, общие для всех условий-->
  <!--Тэги, специфичные для MouseLeaveCondition-->
</Condition>
```

## Тэги, специфичные для MouseLeaveCondition <a href="#tags_mouse_leave_condition" id="tags_mouse_leave_condition"></a>

### Object <a href="#object" id="object"></a>

Объект, на котором срабатывает событие выхода курсора мыши из видимой области объекта.

Необязательный тэг. Значение тэга `<Object>`: не ожидается.

Если тэг `<Object>` отсутствует, то событие срабатывает для формы.

```xml
<Object Name="ObjectName" />
```

#### Атрибуты тэга `<Object>` <a href="#attributes_tag_object" id="attributes_tag_object"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="469.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Название <a href="../../objects/">объекта</a>.</p><p></p><p>Обязательный атрибут. Ожидается название одного из <a href="../../objects/">объектов</a>, описанных в форме.</p></td></tr></tbody></table>
