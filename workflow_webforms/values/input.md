---
description: Входящие значения для сущности (применяются только при описании команд).
---

# Input

## Шаблон Input <a href="#template_input" id="template_input"></a>

```xml
<Input Name="InputName">InputText</Input>
```

## Описание Input <a href="#description_input" id="description_input"></a>

Значение, которое будет передано в команду при выполнении.

Необязательный тэг. Значение тэга `<Input>`: любое значение.

#### Атрибуты тэга `<Input>` <a href="#attributes_input" id="attributes_input"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Имя входящего значения. </p><p></p><p>Обязательный атрибут. Ожидается имя одного из входящих значений, описанных в команде.</p></td></tr></tbody></table>

Например, описание команды типа [ValueSetCommand](../commands/value_set_command.md) может выглядеть так:

```xml
<Command Name="ValueSetCommand" Type="ValueSetCommand" Assembly="Commands">
    <Object Name="TextBox">
        <Input Name="Text" />
    </Object>
</Command>
```

Такое описание будет означать, что в качестве входящего значения Text будет использовано значение, которое будет следующим образом передано при вызове данной команды:

```xml
<Command Name="ValueSetCommand">
    <Input Name="Text">text</Input>
</Command>
```

При описании команды для тэга `<Input>` можно не указывать атрибут `Name`, в этом случае именем входящего значения будет Value.

При вызове команды c тэгом `<Input>` с именем Value тэг `<Input>` можно опускать, то есть при вызове команды следующие 2 описания равнозначны.

Описание 1:

```xml
<Command Name="ValueSetCommand">
    <Input Name="Value">text</Input>
</Command>
```

Описание 2:

```xml
<Command Name="ValueSetCommand">text</Command>
```

Если при вызове команды не был передан тэг `<Input>` с именем, которое используется при описании, то в качестве входящего значения будет использовано значение, определенное в данном тэге `<Input>` по умолчанию.

Значение по умолчанию для тэга `<Input>` задаются следующим образом:

```xml
<Command Name="ValueSetCommand" Type="ValueSetCommand" Assembly="Commands">
    <Object Name="TextBox">
        <Input Name="Text">default text</Input>
    </Object>
</Command>
```
