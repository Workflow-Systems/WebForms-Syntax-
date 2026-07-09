---
description: >-
  Событийное условие; срабатывает при нажатии клавиши символа на объекте или
  форме.
---

# KeyPressCondition

## Шаблон KeyPressCondition <a href="#template_key_press_condition" id="template_key_press_condition"></a>

```xml
<Condition Name="" Type="KeyPressCondition" Assembly="Conditions">
  <!--Тэги, общие для всех условий-->
  <AlwaysChange Value="" />
  <!--Тэги, специфичные для KeyPressCondition-->
  <Object Name="" />
  <Key Code="" />
</Condition>
```

## Описание KeyPressCondition <a href="#description_key_press_condition" id="description_key_press_condition"></a>

```xml
<Condition Name="KeyPressConditionName" Type="KeyPressCondition" Assembly="Conditions">
  <!--Тэги, общие для всех условий-->
  <!--Тэги, специфичные для KeyPressCondition-->
</Condition>
```

## Тэги, специфичные для KeyPressCondition <a href="#tags_key_press_condition" id="tags_key_press_condition"></a>

### Object <a href="#object" id="object"></a>

[Объект](../../objects/), на котором срабатывает событие нажатия клавиши символа.

Необязательный тэг. Значение тэга `<Object>`: не ожидается.

Если тэг `<Object>` отсутствует, то событие срабатывает для формы.

```xml
<Object Name="ObjectName" />
```

#### Атрибуты тэга `<Object>` <a href="#attributes_tag_object" id="attributes_tag_object"></a>

<table data-header-hidden><thead><tr><th width="150" align="center"></th><th width="502.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Название объекта.</p><p></p><p>Обязательный атрибут. Ожидается название одного из объектов, описанных в форме.</p></td></tr></tbody></table>

### Key <a href="#key" id="key"></a>

Описание нажатой клавиши.

Обязательный тэг. Значение тэга `<Key>`: не ожидается.

```xml
<Key Code="13" />
```

#### Атрибуты тэга `<Key>` <a href="#attributes_tag_key" id="attributes_tag_key"></a>

<table data-header-hidden><thead><tr><th width="150" align="center"></th><th width="502.3333333333333"></th></tr></thead><tbody><tr><td align="center">Code</td><td><p>Код нажатой клавиши.</p><p></p><p>Обязательный атрибут. Список возможных значений кодов клавиш доступен по <a href="https://developer.mozilla.org/en-US/docs/Web/API/UI_Events/Keyboard_event_code_values">ссылке</a>.</p></td></tr></tbody></table>
