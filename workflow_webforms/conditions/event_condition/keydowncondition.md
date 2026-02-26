---
description: Событийное условие; срабатывает при нажатии клавиши на объекте или форме.
---

# KeyDownCondition

## Шаблон KeyDownCondition <a href="#template_key_down_condition" id="template_key_down_condition"></a>

```xml
<Condition Name="" Type="KeyDownCondition" Assembly="Conditions">
  <!--Тэги, общие для всех условий-->
  <AlwaysChange Value="" />
  <!--Тэги, специфичные для KeyDownCondition-->
  <Object Name="" />
  <Key Control="" Shift="" Alt="" Value="" />
  <ControlKey></ControlKey>
  <ShiftKey></ShiftKey>
  <AltKey></AltKey>
  <Key1></Key1>
  <Key2></Key2>
</Condition>
```

## Описание KeyDownCondition <a href="#description_key_down_condition" id="description_key_down_condition"></a>

```xml
<Condition Name="KeyDownConditionName" Type="KeyDownCondition" Assembly="Conditions">
  <!--Тэги, общие для всех условий-->
  <!--Тэги, специфичные для KeyDownCondition-->
</Condition>
```

## Тэги, специфичные для KeyDownCondition <a href="#tags_key_down_condition" id="tags_key_down_condition"></a>

### Object <a href="#object" id="object"></a>

[Объект](../../objects/), на котором срабатывает событие нажатия клавиши.

Необязательный тэг. Значение тэга `<Object>`: не ожидается.

Если тэг `<Object>` отсутствует, то событие срабатывает для формы.

```xml
<Object Name="ObjectName" />
```

#### Атрибуты тэга `<Object>` <a href="#attributes_tag_object" id="attributes_tag_object"></a>

<table data-header-hidden><thead><tr><th width="150" align="center"></th><th width="502.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Название объекта.</p><p></p><p>Обязательный атрибут. Ожидается название одного из объектов, описанных в форме.</p></td></tr></tbody></table>

### Key <a href="#key" id="key"></a>

Описание нажатой клавиши.

Необязательный тэг. Значение тэга `<Key>`: не ожидается.

Если тэг `<Key>` отсутствует, то наличие тэгов [`<Key1>`](keydowncondition.md#key1) и/или [`<Key2>`](keydowncondition.md#key2) обязательно.

```xml
<Key Control="False" Shift="False" Alt="False" Value="Enter" />
```

#### Атрибуты тэга `<Key>` <a href="#attributes_tag_key" id="attributes_tag_key"></a>

<table data-header-hidden><thead><tr><th width="150" align="center"></th><th width="502.3333333333333"></th></tr></thead><tbody><tr><td align="center">Control</td><td><p>Признак нажатия клавиши Control совместно с нажатой клавишей.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.<br><br>По умолчанию значение считается неопределенным.</p></td></tr><tr><td align="center">Shift</td><td><p>Признак нажатия клавиши Shift совместно с нажатой клавишей.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.<br><br>По умолчанию значение считается неопределенным.</p></td></tr><tr><td align="center">Alt</td><td><p>Признак нажатия клавиши Alt совместно с нажатой клавишей.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.<br><br>По умолчанию значение считается неопределенным.</p></td></tr><tr><td align="center">Value</td><td>Нажатая клавиша.<br><br>Обязательный атрибут. Ожидается один из кодов нажатой клавиши.<br>Список возможных значений кодов клавиш доступен по <a href="https://developer.mozilla.org/en-US/docs/Web/API/UI_Events/Keyboard_event_code_values">ссылке</a>.</td></tr></tbody></table>

### ControlKey <a href="#control_key" id="control_key"></a>

Признак, определяющий, будет ли проверяться нажатие клавиши Control при нажатии на клавиши, указанные в тэгах [`<Key1>`](keydowncondition.md#key1) и [`<Key2>`](keydowncondition.md#key2).

Необязательный тэг. Ожидается логическое значение.

Если тэг `<ControlKey>` отсутствует, то значение считается неопределенным.

```xml
<ControlKey>True</ControlKey>
```

### ShiftKey <a href="#shift_key" id="shift_key"></a>

Признак, определяющий, будет ли проверяться нажатие клавиши Shift при нажатии на клавиши, указанные в тэгах [`<Key1>`](keydowncondition.md#key1) и [`<Key2>`](keydowncondition.md#key2).

Необязательный тэг. Ожидается логическое значение.

Если тэг `<ShiftKey>` отсутствует, то значение считается неопределенным.

```xml
<ShiftKey>True</ShiftKey>
```

### AltKey <a href="#alt_key" id="alt_key"></a>

Признак, определяющий, будет ли проверяться нажатие клавиши Alt при нажатии на клавиши, указанные в тэгах [`<Key1>`](keydowncondition.md#key1) и [`<Key2>`](keydowncondition.md#key2).

Необязательный тэг. Ожидается логическое значение.

Если тэг `<AltKey>` отсутствует, то значение считается неопределенным.

```xml
<AltKey>True</AltKey>
```

### Key1 <a href="#key1" id="key1"></a>

Первая нажатая клавиша (работает в сочетании с нажатием клавиши, указанной в тэге [`<Key2>`](keydowncondition.md#key2)).

Необязательный тэг. Ожидается один из кодов нажатой клавиши.\
Список возможных значений кодов клавиш доступен по [ссылке](https://developer.mozilla.org/en-US/docs/Web/API/UI_Events/Keyboard_event_code_values).

Если тэг `<Key1>` отсутствует, то наличие тэгов [`<Key>`](keydowncondition.md#key) или [`<Key2>`](keydowncondition.md#key2) обязательно.

```xml
<Key1>Enter</Key1>
```

### Key2 <a href="#key2" id="key2"></a>

Вторая нажатая клавиша (работает в сочетании с нажатием клавиши, указанной в тэге [`<Key1>`](keydowncondition.md#key1)).

Необязательный тэг. Ожидается один из кодов нажатой клавиши.\
Список возможных значений кодов клавиш доступен по [ссылке](https://developer.mozilla.org/en-US/docs/Web/API/UI_Events/Keyboard_event_code_values).

```xml
<Key2>Escape</Key2>
```
