---
description: >-
  Проверка содержимого формы; в случае неверного значения (то есть
  удовлетворяющего проверке) рядом с проверяемым объектом будет расположена
  "звездочка".
---

# Checkings

## Описание Checking <a href="#description_checking" id="description_checking"></a>

Значение: тэги [`<Object>`](checkings.md#object), [`<ConditionExpression>`](checkings.md#condition_expression) и [`<AsteriskHint>`](checkings.md#asterisk_hint).

```xml
<Checking>
  <Object Name="" />
  <Group Name="" />
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
  <AsteriskHint></AsteriskHint>
</Checking>
```

### Object <a href="#object" id="object"></a>

[Объект](objects/), значение которого проверяется.

Обязательный тэг. Значение тэга `<Object>`: не ожидается.

#### Атрибуты тэга `<Object>` <a href="#attributes_tag_object" id="attributes_tag_object"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="458.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Название объекта.</p><p></p><p>Обязательный атрибут. Значение атрибута <code>Name</code>: название одного из объектов, описанных в форме.</p></td></tr></tbody></table>

### Group <a href="#group" id="group"></a>

Группа, к которой относится Сhecking.

Необязательный тэг. Значение тэга `<Group>`: не ожидается.

#### Атрибуты тэга `<Group>` <a href="#attributes_tag_group" id="attributes_tag_group"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="458.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Название группы.</p><p></p><p>Обязательный атрибут. Любое значение будет переведено в текстовое.</p></td></tr></tbody></table>

### ConditionExpression <a href="#condition_expression" id="condition_expression"></a>

Логическое выражение из значений условий.

Обязательный тэг. Ожидается логическое выражение с использованием тэгов `<And>`, `<Or>`, `<Not>` в качестве операций и тэгов `<Condition>` в качестве операндов.

### AsteriskHint <a href="#asterisk_hint" id="asterisk_hint"></a>

Всплывающая подсказка для "звездочки" рядом с объектом.

Необязательный тэг. Любое значение будет переведено в текстовое.
