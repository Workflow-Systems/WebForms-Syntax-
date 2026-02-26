---
description: >-
  Графический объект; элемент пользовательского интерфейса, отображающий текст
  для пользователя.
---

# Label

## Шаблон Label <a href="#template" id="template"></a>

Перечень всех возможных тэгов объекта:

```xml
<MyObject Name="" Type="Label" Assembly="BaseControls" ChangeForm="">
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
  <!--Тэги, специфичные для Label-->
  <TextAlign></TextAlign>
  <Text></Text>
  <DynamicHeight></DynamicHeight>
</MyObject>
```

## Описание Label <a href="#description" id="description"></a>

```xml
<MyObject Name="LabelName" Type="Label" Assembly="BaseControls">
  <!--Тэги, общие для всех графических объектов-->
  <!--Тэги, специфичные для Label-->
</MyObject>
```

### Получение значения Label <a href="#get_value" id="get_value"></a>

Значением `Label` считается текст надписи.

```xml
<Object Name="LabelName" />
```

### Задание значения Label <a href="#set_value" id="set_value"></a>

Любое значение будет переведено в текстовое.

```xml
<Object Name="LabelName"></Object>
```

## Тэги, специфичные для Label <a href="#specific-tags" id="specific-tags"></a>

### TextAlign <a href="#text_align" id="text_align"></a>

Название типа положения текста надписи.

Необязательный тэг. Ожидается название одного из типов положения текста:

<table data-header-hidden><thead><tr><th width="214" align="center"></th><th width="437.3333333333333"></th></tr></thead><tbody><tr><td align="center">TopLeft</td><td>Слева сверху</td></tr><tr><td align="center">TopCenter</td><td>По центру сверху</td></tr><tr><td align="center">TopRight</td><td>Справа сверху</td></tr><tr><td align="center">MiddleLeft</td><td>Слева посередине</td></tr><tr><td align="center">MiddleCenter</td><td>По центру посередине</td></tr><tr><td align="center">MiddleRight</td><td>Справа посередине</td></tr><tr><td align="center">BottomLeft</td><td>Слева снизу</td></tr><tr><td align="center">BottomCenter</td><td>По центру снизу</td></tr><tr><td align="center">BottomRight</td><td>Справа снизу</td></tr></tbody></table>

Если тэг `<TextAlign>` отсутствует, то используется значение MiddleLeft.

```xml
<TextAlign>MiddleLeft</TextAlign>
```

### Text <a href="#text" id="text"></a>

Текст надписи.

Необязательный тэг. Любое значение будет переведено в текстовое.

```xml
<Text>Текст</Text>
```

### DynamicHeight <a href="#dynamic_height" id="dynamic_height"></a>

Признак, включающий механизм динамического расчета высоты объекта.

{% hint style="danger" %}
Признак DynamicHeight со значением True нельзя использовать одновременно со свойством [Height](https://wfsys.gitbook.io/workflow-web-forms-syntax/workflow_webforms/objects#height).&#x20;
{% endhint %}

Необязательный тэг. Ожидается логическое значение.

По умолчанию используется значение False.

```xml
<DynamicHeight>True</DynamicHeight>
```

## Get-проперти для получения свойств <a href="#get_properties" id="get_properties"></a>

### TextAlign <a href="#get_text_align" id="get_text_align"></a>

Возвращает название типа положения текста надписи.

```xml
<Object Name="LabelName">
  <Property Name="TextAlign" />
</Object>
```

### Text <a href="#get_text" id="get_text"></a>

Возвращает текст надписи.

```xml
<Object Name="LabelName">
  <Property Name="Text" />
</Object>
```

### DynamicHeight <a href="#get_dynamic_height" id="get_dynamic_height"></a>

Возвращает значение признака, включающего механизм динамического расчета высоты объекта.

```xml
<Object Name="LabelName">
  <Property Name="DynamicHeight" />
</Object>
```

## Set-проперти для динамического задания свойств <a href="#set_properties" id="set_properties"></a>

### TextAlign <a href="#set_text_align" id="set_text_align"></a>

Задает название типа положения текста надписи.

Ожидается одно из названий типов положения текста.

```xml
<Object Name="LabelName">
  <Property Name="TextAlign">TopLeft</Property>
</Object>
```

### Text <a href="#set_text" id="set_text"></a>

Задает текст надписи.

Любое значение будет переведено в текстовое.

```xml
<Object Name="LabelName">
  <Property Name="Text">Text</Property>
</Object>
```

### DynamicHeight <a href="#set_dynamic_height" id="set_dynamic_height"></a>

Задает значение признаку, включающему механизм динамического расчета высоты объекта.

Ожидается логическое  значение.

```xml
<Object Name="LabelName">
  <Property Name="DynamicHeight">True</Property>
</Object>
```
