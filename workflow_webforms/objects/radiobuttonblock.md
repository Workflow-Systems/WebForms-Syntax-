---
description: Графический объект; группа радиокнопок.
---

# RadioButtonBlock

## Шаблон RadioButtonBlock <a href="#template_radiobuttonblock" id="template_radiobuttonblock"></a>

Перечень всех возможных тэгов объекта:

```xml
<MyObject Name="" Type="RadioButtonBlock" Assembly="BaseControls" ChangeForm="">
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
  <!--Тэги, специфичные для RadioButtonBlock-->
  <Options>
    <Option Name="">
      <Top></Top>
      <Left></Left>
      <Height></Height>
      <Width></Width>
      <FontStyle></FontStyle>
      <ForeColor></ForeColor>
      <BackColor></BackColor>
      <Enabled></Enabled>
      <Visible></Visible>
      <Hint></Hint>
      <ContextMenu Name="" />
      <Change User="" Source="" ValueSet="" />
      <Text></Text>
      <Checked></Checked>
      <Value></Value>
    </Option>
  </Options>
  <Value></Value>
</MyObject>
```

## Описание RadioButtonBlock <a href="#description_radiobuttonblock" id="description_radiobuttonblock"></a>

```xml
<MyObject Name="RadioButtonBlockName" Type="RadioButtonBlock" Assembly="BaseControls">
  <!--Тэги, общие для всех графических объектов-->
  <!--Тэги, специфичные для RadioButtonBlock-->
</MyObject>
```

### Получение значения RadioButtonBlock <a href="#get_value_radiobuttonblock" id="get_value_radiobuttonblock"></a>

Значением `RadioButtonBlock` считается значение выбранной радиокнопки.

```xml
<Object Name="RadioButtonBlockName" />
```

### Задание значения RadioButtonBlock <a href="#set_value_radiobuttonblock" id="set_value_radiobuttonblock"></a>

Значение объекта: любое значение.

```xml
<Object Name="RadioButtonBlockName"></Object>
```

## Тэги, специфичные для RadioButtonBlock <a href="#tags_radiobuttonblock" id="tags_radiobuttonblock"></a>

### Options <a href="#options" id="options"></a>

Содержит список радиокнопок.

Необязательный тэг. Значение тэга `<Options>`: список тэгов [`<Option>`](radiobuttonblock.md#options_option), содержащих описание радиокнопок.

```xml
<Options></Options>
```

### Value <a href="#value" id="value"></a>

Значение группы радиокнопок.

Необязательный тэг. Значение тэга `<Value>`: любое значение.

```xml
<Value>Value</Value>
```

## Тэг `<Option>` <a href="#options_option" id="options_option"></a>

Графический объект; радиокнопка (круглая кнопка).

### Описание радиокнопки <a href="#description_options_option" id="description_options_option"></a>

```xml
<Option Name="">
  <!--Тэги, общие для всех графических объектов-->
  <!--Тэги, специфичные для радиокнопки-->
</Option>
```

### Атрибуты тэга`<Option>` <a href="#attributes_options_option" id="attributes_options_option"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="435.6666666666667"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Название радиокнопки.</p><p></p><p>Обязательный атрибут.</p></td></tr></tbody></table>

### Тэги, специфичные для радиокнопки <a href="#tags_options_option" id="tags_options_option"></a>

#### Text <a href="#options_option_text" id="options_option_text"></a>

Текст рядом с радиокнопкой.

Необязательный тэг. Любое значение будет переведено в текстовое.

```xml
<Text>Текст</Text>
```

#### Checked <a href="#options_option_checked" id="options_option_checked"></a>

Признак выбора радиокнопки из группы.

Необязательный тэг. Ожидается логическое значение.

По умолчанию используется значение False.

```xml
<Checked>False</Checked>
```

#### Value <a href="#options_option_value" id="options_option_value"></a>

Значение радиокнопки.

Необязательный тэг. Значение тэга `<Value>`: любое значение.

```xml
<Value>Value</Value>
```

## Get-проперти для получения свойств <a href="#get_property_radiobuttonblock" id="get_property_radiobuttonblock"></a>

### Text <a href="#get_text" id="get_text"></a>

Возвращает текст рядом с радиокнопкой Option.

Значение тэга `<Property>`: тэг `<Parameters>` со вложенными тэгами `<Parameter>`, один из которых имеет атрибут `Name`, равный Option.

```xml
<Object Name="RadioButtonBlockName">
  <Property Name="Text">
    <Parameters>
      <!--Значение тэга Parameter с атрибутом Name, равным Option: ожидается название одной из радиокнопок-->
      <Parameter Name="Option">OptionName</Parameter>
    </Parameters>
  </Property>
</Object>
```

Если начение тэга `<Property>` отсутствует, то будет возвращен текст рядом с выбранной радиокнопкой.

```xml
<Object Name="RadioButtonBlockName">
  <Property Name="Text" />
</Object>
```

### Checked <a href="#get_checked" id="get_checked"></a>

Возвращает признак выбора радиокнопки [`<Option>`](radiobuttonblock.md#options_option) из группы.

```xml
<Object Name="RadioButtonBlockName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter, один из которых имеет атрибут Name, равный Option-->
  <Property Name="Checked">
    <Parameters>
      <!--Значение тэга Parameter с атрибутом Name, равным Option: ожидается название одной из радиокнопок-->
      <Parameter Name="Option">OptionName</Parameter>
    </Parameters>
  </Property>
</Object>
```

## Set-проперти для динамического задания свойств <a href="#set_property_radiobuttonblock" id="set_property_radiobuttonblock"></a>

### Text <a href="#set_text" id="set_text"></a>

Задает текст рядом с радиокнопкой [`<Option>`](radiobuttonblock.md#options_option).

```xml
<Object Name="RadioButtonBlockName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter-->
  <Property Name="Text">
    <Parameters>
      <!--Необязательный параметр. При отсутствии обновляет текст рядом с выделенной радиокнопкой-->
      <!--Значение тэга Parameter с атрибутом Name, равным Option: ожидается название одной из радиокнопок-->
      <Parameter Name="Option">OptionName</Parameter>
      <!--Значение тэга Parameter с атрибутом Name, равным Value: любое значение будет переведено в текстовое-->
      <Parameter Name="Value">Text</Parameter>
    </Parameters>
  </Property>
</Object>
```

### Checked <a href="#set_checked" id="set_checked"></a>

Задает признак выбора радиокнопки [`<Option>`](radiobuttonblock.md#options_option) из группы.

```xml
<Object Name="RadioButtonBlockName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter-->
  <Property Name="Checked">
    <Parameters>
      <!--Значение тэга Parameter с атрибутом Name, равным Option: ожидается название одной из радиокнопок-->
      <Parameter Name="Option">OptionName</Parameter>
      <!--Значение тэга Parameter с атрибутом Name, равным Value: ожидается логическое значение-->
      <Parameter Name="Value">True</Parameter>
    </Parameters>
  </Property>
</Object>
```
