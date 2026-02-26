---
description: Событийное условие; срабатывает при входе курсора в видимую область объекта.
---

# MouseEnterCondition

## Шаблон MouseEnterCondition <a href="#template_mouse_enter_condition" id="template_mouse_enter_condition"></a>

```xml
<Condition Name="" Type="MouseEnterCondition" Assembly="Conditions">
  <!--Тэги, общие для всех условий-->
  <AlwaysChange Value="" />
  <!--Тэги, специфичные для MouseEnterCondition-->
  <Object Name="" />
</Condition>
```

## Описание MouseEnterCondition <a href="#description_mouse_enter_condition" id="description_mouse_enter_condition"></a>

```xml
<Condition Name="MouseEnterConditionName" Type="MouseEnterCondition" Assembly="Conditions">
  <!--Тэги, общие для всех условий-->
  <!--Тэги, специфичные для MouseEnterCondition-->
</Condition>
```

## Тэги, специфичные для MouseEnterCondition <a href="#tags_mouse_enter_condition" id="tags_mouse_enter_condition"></a>

### Object <a href="#object" id="object"></a>

Объект, на котором срабатывает событие входа курсора в видимую область объекта.

Необязательный тэг. Значение тэга `<Object>`: не ожидается.

Если тэг `<Object>` отсутствует, то событие срабатывает для формы.

```xml
<Object Name="ObjectName" />
```

#### Атрибуты тэга `<Object>` <a href="#attributes_tag_object" id="attributes_tag_object"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="469.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Название объекта.</p><p></p><p>Обязательный атрибут. Ожидается название одного из <a href="../../objects/">объектов</a>, описанных в форме.</p></td></tr></tbody></table>
