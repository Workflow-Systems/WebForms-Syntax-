---
description: Графический объект; галочка.
---

# CheckBox

## Шаблон CheckBox

Перечень всех возможных тэгов объекта:

```xml
<MyObject Name="" Type="CheckBox" Assembly="BaseControls" ChangeForm="">
  <!--Тэги, общие для всех графических объектов-->
  <Top></Top>
  <Bottom></Bottom>
  <Left></Left>
  <Right></Right>
  <Height></Height>
  <Width></Width>
  <FontStyle></FontStyle>
  <ForeColor></ForeColor>
  <BackColor></BackColor>
  <Enabled></Enabled>
  <Visible></Visible>
  <Hint></Hint>
  <Change User="" Source="" ValueSet="" />
  <!--Тэги, специфичные для CheckBox-->
  <Text></Text>
  <Value></Value>
</MyObject>
```

## Описание CheckBox

```xml
<MyObject Name="ButtonName" Type="CheckBox" Assembly="BaseControls">
  <!--Тэги, общие для всех графических объектов-->
  <!--Тэги, специфичные для CheckBox-->
</MyObject>
```

Значением CheckBox считается признак установки галочки.

### Получение значения CheckBox

```xml
<Object Name="CheckBoxName" />
```

### Задание значения CheckBox

Значение объекта: ожидается логическое значение.

```xml
<Object Name="CheckBoxName">False</Object>
```

## Тэги, специфичные для CheckBox

### Text

Текст подписи для галочки.

Необязательный тэг. Любое значение будет переведено в текстовое.

```xml
<Text>Текст</Text>
```

### Value

Признак установки галочки.

Необязательный тэг. Ожидается логическое значение.

По умолчанию используется значение False.

```xml
<Value>False</Value>
```

## Get-проперти для получения свойств

### Text <a href="#get_text" id="get_text"></a>

Возвращает текст подписи для галочки.

```xml
<Object Name="CheckBoxName">
  <Property Name="Text" />
</Object>
```

## Set-проперти для динамического задания свойств

### Text <a href="#set_text" id="set_text"></a>

Задает текст подписи для галочки.

Любое значение будет переведено в текстовое.

```xml
<Object Name="CheckBoxName">
  <Property Name="Text">Text</Property>
</Object>
```
