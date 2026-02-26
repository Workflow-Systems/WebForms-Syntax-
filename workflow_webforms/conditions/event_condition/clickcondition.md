---
description: Событийное условие; срабатывает при клике на объекте или форме.
---

# ClickCondition

## Шаблон ClickCondition <a href="#template_click_condition" id="template_click_condition"></a>

```xml
<Condition Name="" Type="ClickCondition" Assembly="Conditions">
  <!--Тэги, общие для всех условий-->
  <AlwaysChange Value="" />
  <!--Тэги, специфичные для ClickCondition-->
  <Object Name="" />
  <Button Type="" />
</Condition>
```

## Описание ClickCondition <a href="#description_click_condition" id="description_click_condition"></a>

```xml
<Condition Name="ClickConditionName" Type="ClickCondition" Assembly="Conditions">
  <!--Тэги, общие для всех условий-->
  <!--Тэги, специфичные для ClickCondition-->
</Condition>
```

## Тэги, специфичные для ClickCondition <a href="#tags_click_condition" id="tags_click_condition"></a>

### Object <a href="#object" id="object"></a>

[Объект](../../objects/), на котором срабатывает событие клика.

Необязательный тэг. Значение тэга `<Object>`: не ожидается.

Если тэг `<Object>` отсутствует, то событие срабатывает для всех объектов формы за исключением тех, что указаны в тэге [`<ExceptObjects>`](clickcondition.md#except_objects).

```xml
<Object Name="ObjectName" />
```

#### Атрибуты тэга `<Object>` <a href="#attributes_tag_object" id="attributes_tag_object"></a>

<table data-header-hidden><thead><tr><th width="150" align="center"></th><th width="502.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Название объекта.</p><p></p><p>Обязательный атрибут. Ожидается название одного из объектов, описанных в форме.</p></td></tr></tbody></table>

### Button <a href="#button" id="button"></a>

Кнопка мыши, нажатая во время клика.

Необязательный тэг. Значение тэга `<Button>`: не ожидается.

Если тэг `<Button>` отсутствует, то для атрибута `Type` используется значение Any.

```xml
<Button Type="Any" />
```

#### Атрибуты тэга `<Button>` <a href="#attributes_tag_button" id="attributes_tag_button"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="502.3333333333333"></th></tr></thead><tbody><tr><td align="center">Type</td><td><p>Тип нажатой кнопки.</p><p></p><p>Обязательный атрибут. Ожидается название одного из <a href="clickcondition.md#mouse_button_types">типов кнопок мышки</a>.</p></td></tr></tbody></table>

#### Типы кнопок мышки <a href="#mouse_button_types" id="mouse_button_types"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="502.3333333333333"></th></tr></thead><tbody><tr><td align="center">Any</td><td>Любая кнопка</td></tr><tr><td align="center">Left</td><td>Левая кнопка</td></tr><tr><td align="center">Right</td><td>Правая кнопка</td></tr></tbody></table>
