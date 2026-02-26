---
description: >-
  Графический объект; поле с выпадающим списком и возможностью одновременного
  выбора нескольких элементов.
---

# CheckedComboBox

## Шаблон CheckedComboBox <a href="#template_checkedcombobox" id="template_checkedcombobox"></a>

Перечень всех возможных тэгов объекта:

```xml
<MyObject Name="" Type="CheckedComboBox" Assembly="BaseControls" ChangeForm="">
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
  <!--Тэги, специфичные для CheckedComboBox-->
  <DropDownHeight></DropDownHeight>
  <DropDownWidth></DropDownWidth>
  <InputLanguage></InputLanguage>
  <InputCase></InputCase>
  <SearchMode Value="" />
  <NullValue Show="" Title="" />
  <NullValueTitle></NullValueTitle>
  <ValueList>
    <DataConnection SourceDataConnection="">
      <Fields>
        <Field Name="" />
        <Field Name="" />
      </Fields>
    </DataConnection>
  </ValueList>
  <Value></Value>
</MyObject>
```

## Описание CheckedComboBox <a href="#description_checkedcombobox" id="description_checkedcombobox"></a>

```xml
<MyObject Name="CheckedComboBox" Type="CheckedComboBox" Assembly="BaseControls">
  <!--Тэги, общие для всех графических объектов-->
  <!--Тэги, специфичные для CheckedComboBox-->
</MyObject>
```

### Получение значения CheckedComboBox <a href="#get_value_checkedcombobox" id="get_value_checkedcombobox"></a>

Значением `<CheckedComboBox>` считается линейный массив выбранных элементов из списка.

```xml
<Object Name="CheckedComboBoxName" />
```

### Задание значения CheckedComboBox <a href="#set_value_checkedcombobox" id="set_value_checkedcombobox"></a>

Значение объекта: любое значение (кроме NULL) будет преобразовано в линейный массив.

```xml
<Object Name="CheckedComboBoxName"></Object>
```

## Тэги, специфичные для CheckedComboBox <a href="#tags_checkedcombobox" id="tags_checkedcombobox"></a>

### DropDownHeight <a href="#drop_down_height" id="drop_down_height"></a>

Высота выпадающего списка.

Необязательный тэг. Ожидается целочисленное значение.

По умолчанию используется стандартное значение .NET.

```xml
<DropDownHeight>100</DropDownHeight>
```

### DropDownWidth <a href="#drop_down_width" id="drop_down_width"></a>

Ширина выпадающего списка.

Необязательный тэг. Ожидается целочисленное значение.

По умолчанию используется значение ширины объекта.

```xml
<DropDownWidth>200</DropDownWidth>
```

### InputLanguage <a href="#input_language" id="input_language"></a>

Название языка для ограничения по вводимым символам.

Необязательный тэг. Ожидается название одного из языков:

<table data-header-hidden><thead><tr><th align="center"></th><th width="435.6666666666667"></th></tr></thead><tbody><tr><td align="center">Rus</td><td>Русский</td></tr><tr><td align="center">Eng</td><td>Английский</td></tr><tr><td align="center">None</td><td>Без ограничений по языку</td></tr></tbody></table>

По умолчанию используется значение None.

Если язык вводимого символа не совпадает с языком, указанном в данном тэге, то этот символ будет трансформирован в символ другого языка, расположенный на этой же клавише на клавиатуре.

```xml
<InputLanguage>None</InputLanguage>
```

### InputCase <a href="#input_case" id="input_case"></a>

Название типа регистра для ограничения по вводимым символам.

Необязательный тэг. Ожидается название одного из типов регистров:

<table data-header-hidden><thead><tr><th align="center"></th><th width="435.6666666666667"></th></tr></thead><tbody><tr><td align="center">Upper</td><td>Верхний регистр</td></tr><tr><td align="center">Lower</td><td>Нижний регистр</td></tr><tr><td align="center">None</td><td>Без ограничений по регистру</td></tr></tbody></table>

По умолчанию используется значение None.

Если регистр вводимого символа не совпадает с регистром, указанном в данном тэге, то этот символ будет трансформирован в указанный регистр.

```xml
<InputCase>None</InputCase>
```

### SearchMode <a href="#search_mode" id="search_mode"></a>

Признак, определяющий, может ли пользователь искать элементы в списке с помощью ручного ввода текста.

Необязательный тэг. Значение тэга `<SearchMode>`: не ожидается.

Если тэг `<SearchMode>` отсутствует, то для атрибута `Value` используется значение True.

```xml
<SearchMode Value="True" />
```

#### Атрибуты тэга \<SearchMode> <a href="#attributes_tag_search_mode" id="attributes_tag_search_mode"></a>

<table data-header-hidden><thead><tr><th width="190" align="center"></th><th width="453.6666666666667"></th></tr></thead><tbody><tr><td align="center">Value</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается логическое значение.</p></td></tr></tbody></table>

### NullValue <a href="#null_value" id="null_value"></a>

Настройка отображения NULL-значения объекта.

Необязательный тэг. Значение тэга `<NullValue>`: не ожидается.

Если тэг `<NullValue>` отсутствует, то для атрибута `Show` используется значение False.

```xml
<NullValue Show="False" Title="[Все]" />
```

#### Атрибуты тэга \<NullValue> <a href="#attributes_tag_null_value" id="attributes_tag_null_value"></a>

<table data-header-hidden><thead><tr><th width="150" align="center"></th><th width="435.6666666666667"></th></tr></thead><tbody><tr><td align="center">Show</td><td><p>Признак, определяющий, будет ли объект иметь значение NULL в том случае, если были отмечены все значения из выпадающего списка.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>Если атрибут <code>Show</code> отсутствует, то используется значение False.</p><p></p><p>Значение True так же означает, что в список элементов на первую позицию будет добавлен элемент "[Все]", по нажатию на который будут отмечены все остальные элементы в списке.</p></td></tr><tr><td align="center">Title</td><td><p>Отображаемое значение элемента, по нажатию на который будут отмечены все остальные элементы в списке.</p><p></p><p>Необязательный атрибут. Любое значение будет переведено в текстовое.</p><p></p><p>Если атрибут <code>Title</code> отсутствует, то используется пустое значение.</p></td></tr></tbody></table>

### NullValueTitle <a href="#null_value_title" id="null_value_title"></a>

Отображаемое значение элемента, по нажатию на который будут отмечены все остальные элементы в списке.

Необязательный тэг. Любое значение будет переведено в текстовое.

Если тэг `<NullValueTitle>` отсутствует, то используется пустое значение.

Игнорируется при наличии атрибута `Title` в тэге [`<NullValue>`](checkedcombobox.md#nullvalue).

```xml
<NullValueTitle>[Все]</NullValueTitle>
```

### ValueList <a href="#value_list" id="value_list"></a>

Элементы выпадающего списка.

Необязательный тэг. Ожидается таблица с одним, двумя или более столбцами (например, ссылка на [`GetDataConnection`](../dataconnections/)).

Первое поле будет соответствовать реальному значению элемента, второе – его отображаемому значению (если второго поля нет, то отображаемое значение равно реальному).

Все остальные поля могут быть опционально использованы в выражениях для условного форматирования элементов выпадающего списка.

```xml
<ValueList>
  <DataConnection SourceDataConnection="SourceDataConnectionName">
    <Fields>
      <Field Name="Field1Name" />
      <Field Name="Field2Name" />
    </Fields>
  </DataConnection>
</ValueList>
```

### Value <a href="#value" id="value"></a>

Значение, соответствующее линейному массиву реальных значений выбранных элементов.

Необязательный тэг. Любое значение (кроме NULL) будет преобразовано в линейный массив.

Если поле имеет значение NULL, то элементы в выпадающем списке будут отмечены в зависимости от значения атрибута `Show` тэга [`<NullValue>`](checkedcombobox.md#null_value). Если атрибут `Show` равен True, то будут отмечены все элементы в списке, иначе - не будет выбран ни один.

```xml
<Value>Value</Value>
```

## Get-проперти для получения свойств <a href="#get_property_checkedcombobox" id="get_property_checkedcombobox"></a>

### DropDownHeight <a href="#get_drop_down_height" id="get_drop_down_height"></a>

Возвращает высоту выпадающего списка.

```xml
<Object Name="CheckedComboBoxName">
  <Property Name="DropDownHeight" />
</Object>
```

### DropDownWidth <a href="#get_drop_down_width" id="get_drop_down_width"></a>

Возвращает ширину выпадающего списка.

```xml
<Object Name="CheckedComboBoxName">
  <Property Name="DropDownWidth" />
</Object>
```

### InputLanguage <a href="#get_input_language" id="get_input_language"></a>

Возвращает название языка для ограничения по вводимым символам.

```xml
<Object Name="TextBoxName">
  <Property Name="InputLanguage" />
</Object>
```

### InputCase <a href="#get_input_case" id="get_input_case"></a>

Возвращает название типа регистра для ограничения по вводимым символам.

```xml
<Object Name="TextBoxName">
  <Property Name="InputCase" />
</Object>
```

### ValueList <a href="#get_value_list" id="get_value_list"></a>

Возвращает элементы выпадающего списка (таблица с двумя столбцами).

```xml
<Object Name="CheckedComboBoxName">
  <Property Name="ValueList" />
</Object>
```

### ItemsCount <a href="#get_items_count" id="get_items_count"></a>

Возвращает количество элементов в списке.

```xml
<Object Name="CheckedComboBoxName">
  <Property Name="ItemsCount" />
</Object>
```

### SelectedItemsCount <a href="#get_selected_items_count" id="get_selected_items_count"></a>

Возвращает количество выбранных элементов в списке.&#x20;

```xml
<Object Name="CheckedComboBoxName">
  <Property Name="SelectedItemsCount" />
</Object>
```

### VisibleText <a href="#get_visible_text" id="get_visible_text"></a>

Возвращает отображаемое значение поля, текстовый список выбранных элементов.

```xml
<Object Name="CheckedComboBoxName">
  <Property Name="VisibleText" />
</Object>
```

### VisibleTextDelimeter <a href="#get_visible_text_delimeter" id="get_visible_text_delimeter"></a>

Возвращает текстовый список выбранных элементов с заданным разделителем.&#x20;

```xml
<Object Name="CheckedComboBoxName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter-->
  <Property Name="VisibleTextDelimeter" >
    <Parameters>
      <!--Значение тэга Parameter с атрибутом Name, равным Delimeter: ожидается символ или строка, которая будет использоваться как разделитель в выводимом списке выбранных элементов-->
      <Parameter Name="Delimeter">\r</Parameter>
    </Parameters>
  </Property>
</Object>
```

## Set-проперти для динамического задания свойств <a href="#set_property_checkedcombobox" id="set_property_checkedcombobox"></a>

### DropDownHeight <a href="#set_drop_down_height" id="set_drop_down_height"></a>

Задает высоту выпадающего списка.

Ожидается целочисленное значение.

```xml
<Object Name="CheckedComboBoxName">
  <Property Name="DropDownHeight">400</Property>
</Object>
```

### DropDownWidth <a href="#set_drop_down_width" id="set_drop_down_width"></a>

Задает ширину выпадающего списка.

Ожидается целочисленное значение.

```xml
<Object Name="CheckedComboBoxName">
  <Property Name="DropDownWidth">300</Property>
</Object>
```

### InputLanguage <a href="#set_input_language" id="set_input_language"></a>

Задает название языка для ограничения по вводимым символам.

Ожидается один из языков.

```xml
<Object Name="CheckedComboBoxName">
  <Property Name="InputLanguage">Rus</Property>
</Object>
```

### InputCase <a href="#set_input_case" id="set_input_case"></a>

Задает название типа регистра для ограничения по вводимым символам.

Ожидается один из типов регистров.

```xml
<Object Name="CheckedComboBoxName">
  <Property Name="InputCase">Lower</Property>
</Object>
```

### ValueList <a href="#set_value_list" id="set_value_list"></a>

Задает элементы выпадающего списка.

Ожидается таблица с двумя столбцами (например, ссылка на [`GetDataConnection`](../dataconnections/) с указанием двух его полей).

```xml
<Object Name="CheckedComboBoxName">
  <Property Name="ValueList">
    <DataConnection SourceDataConnection="SourceDataConnectionName">
      <Fields>
        <Field Name="Field1Name" />
        <Field Name="Field2Name" />
      </Fields>
    </DataConnection>
  </Property>
</Object>
```
