---
description: Графический объект; поле для выбора цвета.
---

# ColorBox

## Шаблон ColorBox <a href="#template_combobox" id="template_combobox"></a>

Перечень всех возможных тэгов объекта:

```xml
<MyObject Name="" Type="ColorBox" Assembly="BaseControls" ChangeForm="">
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
  <!--Тэги, специфичные для ComboBox-->
  <Value></Value>
</MyObject>
```

## Описание ColorBox <a href="#description_combobox" id="description_combobox"></a>

```xml
<MyObject Name="ColorBoxName" Type="ColorBox" Assembly="BaseControls">
  <!--Тэги, общие для всех графических объектов-->
  <!--Тэги, специфичные для ComboBox-->
</MyObject>
```

### Получение значения ColorBox <a href="#get_value_combobox" id="get_value_combobox"></a>

Значением ColorBox считается выбранный цвет в формате HTML (#rrggbb).

```xml
<Object Name="ColorBoxName" />
```

### Задание значения ColorBox <a href="#set_value_combobox" id="set_value_combobox"></a>

Значение объекта: ожидается цвет в формате HTML (#rrggbb).

Любое значение будет переведено в текстовое.

```xml
<Object Name="ColorBoxName">#e33838</Object>
```

## Тэги, специфичные для ColorBox

### Value

Цвет.

Необязательный тэг. Ожидается один из цветов в формате HTML (#rrggbb).

По умолчанию используется значение null.

```xml
<Value>#0366d6</Value>
```

## Get-проперти для получения свойств <a href="#get_property_combobox" id="get_property_combobox"></a>

### Red <a href="#get_enter_text" id="get_enter_text"></a>

Возвращает красную составляющую цвета.

```xml
<Object Name="ColorBoxName">
  <Property Name="Red" />
</Object>
```

### Green <a href="#get_max_length" id="get_max_length"></a>

Возвращает зеленую составляющую цвета.

```xml
<Object Name="ColorBoxName">
  <Property Name="Green" />
</Object>
```

### Blue <a href="#get_auto_complete_mode" id="get_auto_complete_mode"></a>

Возвращает синюю составляющую цвета.

```xml
<Object Name="ColorBoxName">
  <Property Name="Blue" />
</Object>
```

## Set-проперти для динамического задания свойств <a href="#set_property_combobox" id="set_property_combobox"></a>

### Red <a href="#get_enter_text" id="get_enter_text"></a>

Задает красную составляющую цвета.

Ожидается целочисленное значение в диапазоне от 0 до 255.

```xml
<Object Name="ComboBoxName">
  <Property Name="Red">1</Property>
</Object>
```

### Green <a href="#get_max_length" id="get_max_length"></a>

Задает зеленую составляющую цвета.

Ожидается целочисленное значение в диапазоне от 0 до 255.

```xml
<Object Name="ComboBoxName">
  <Property Name="Green">2</Property>
</Object>
```

### Blue <a href="#get_auto_complete_mode" id="get_auto_complete_mode"></a>

Задает синюю составляющую цвета.

Ожидается целочисленное значение в диапазоне от 0 до 255.

```xml
<Object Name="ComboBoxName">
  <Property Name="Blue">3</Property>
</Object>
```
