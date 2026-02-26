---
description: Команда; присваивает фокус заданному объекту на странице.
---

# FocusSetCommand

## Шаблон FocusSetCommand <a href="#template_focus_set_command" id="template_focus_set_command"></a>

```xml
<Command Name="" Type="FocusSetCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <Condition Name="" />
  <Lock Value="" />
  <!--Тэги, специфичные для FocusSetCommand-->
  <Object Name="" />
</Command>
```

## Описание FocusSetCommand <a href="#description_focus_set_command" id="description_focus_set_command"></a>

```xml
<Command Name="FocusSetCommandName" Type="FocusSetCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <!--Тэги, специфичные для FocusSetCommand-->
</Command>
```

### Результат выполнения FocusSetCommand <a href="#result_focus_set_command" id="result_focus_set_command"></a>

Команда не имеет результата.

## Тэги, специфичные для FocusSetCommand <a href="#tags_focus_set_command" id="tags_focus_set_command"></a>

### Object <a href="#object" id="object"></a>

Объект, которому будет присвоен фокус.

Обязательный тэг. Значение тэга `<Object>`: не ожидается.

```xml
<Object Name="ObjectName" />
```

#### Атрибуты тэга `<Object>` <a href="#attributes_tag_object" id="attributes_tag_object"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="426.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Название объекта.</p><p></p><p>Обязательный атрибут. Ожидается название одного из <a href="../objects/">объектов</a> на форме.</p></td></tr></tbody></table>
