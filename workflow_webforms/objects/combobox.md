---
description: Графический объект; поле с выпадающим списком.
---

# ComboBox

## Шаблон ComboBox <a href="#template_combobox" id="template_combobox"></a>

Перечень всех возможных тэгов объекта:

```xml
<MyObject Name="" Type="ComboBox" Assembly="BaseControls" ChangeForm="">
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
  <EnterText></EnterText>
  <MaxLength></MaxLength>
  <DropDownHeight></DropDownHeight>
  <DropDownWidth></DropDownWidth>
  <InputLanguage></InputLanguage>
  <InputCase></InputCase>
  <NullValue Show="" Title="" />
  <NullValueTitle></NullValueTitle>
  <AllowOutOfList Value="" />
  <Text></Text>
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

## Описание ComboBox <a href="#description_combobox" id="description_combobox"></a>

```xml
<MyObject Name="ComboBoxName" Type="ComboBox" Assembly="BaseControls">
  <!--Тэги, общие для всех графических объектов-->
  <!--Тэги, специфичные для ComboBox-->
</MyObject>
```

### Получение значения ComboBox <a href="#get_value_combobox" id="get_value_combobox"></a>

Значением ComboBox считается реальное значение выбранного элемента из списка.

```xml
<Object Name="ComboBoxName" />
```

### Задание значения ComboBox <a href="#set_value_combobox" id="set_value_combobox"></a>

Значение объекта: любое значение.

```xml
<Object Name="ComboBoxName"></Object>
```

## Тэги, специфичные для ComboBox <a href="#tags_combobox" id="tags_combobox"></a>

### EnterText <a href="#enter_text" id="enter_text"></a>

Признак, определяющий, может ли пользователь вводить текст внутри поля.

Необязательный тэг. Ожидается логическое значение.

По умолчанию используется значение False.

```xml
<EnterText>False</EnterText>
```

### MaxLength <a href="#max_length" id="max_length"></a>

Задает максимальное число символов, которое разрешается вводить или вставлять в поле.

Необязательный тэг. Ожидается положительное целочисленное значение.

По умолчанию используется значение 0, показывающее, что ограничения нет.

```xml
<MaxLength>0</MaxLength>
```

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

### Text

Текст поля (доступно в случае, если [`<EnterText>`](combobox.md#enter_text) имеет значение True).

Необязательный тэг. Любое значение будет переведено в текстовое.

Текстовое значение может быть присвоено, только если основное значение [`<Value>`](combobox.md#value) равно NULL.

```xml
<Text>Текст</Text>
```

### NullValue <a href="#null_value" id="null_value"></a>

Настройка отображения NULL-значения объекта.

Необязательный тэг. Значение тэга `<NullValue>`: не ожидается.

Если тэг `<NullValue>` отсутствует, то для атрибута `Show` используется значение False.

```xml
<NullValue Show="False" Title="[не выбрано]" />
```

#### Атрибуты тэга `<NullValue>` <a href="#attributes_tag_null_value" id="attributes_tag_null_value"></a>

<table data-header-hidden><thead><tr><th width="150" align="center"></th><th width="435.6666666666667"></th></tr></thead><tbody><tr><td align="center">Show</td><td><p>Признак, определяющий, будет ли в выпадающем списке элемент, имеющий реальное значение NULL.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>По умолчанию используется значение False.</p></td></tr><tr><td align="center">Title</td><td><p>Отображаемое значение элемента, имеющего реальное значение NULL.</p><p></p><p>Необязательный атрибут. Любое значение будет переведено в текстовое.</p><p></p><p>По умолчанию используется пустое значение.</p></td></tr></tbody></table>

### NullValueTitle <a href="#null_value_title" id="null_value_title"></a>

Отображаемое значение элемента, имеющего реальное значение NULL.

Необязательный тэг. Любое значение будет переведено в текстовое.

По умолчанию используется пустое значение.

Игнорируется при наличии атрибута `Title` в тэге [`<NullValue>`](combobox.md#null_value).

```xml
<NullValueTitle>[не выбрано]</NullValueTitle>
```

### AllowOutOfList <a href="#allow_out_of_list" id="allow_out_of_list"></a>

Признак, разрешающий полю принимать и хранить значение даже если это значение отсутствует в списке элементов поля.

Необязательный тэг. Значение тэга `<AllowOutOfList>`: не ожидается.

Если тэг `<AllowOutOfList>` отсутствует, то для атрибута `Value` используется значение False.

```xml
<AllowOutOfList Value="False" />
```

#### Атрибуты тэга `<AllowOutOfList>` <a href="#attributes_tag_allow_out_of_list" id="attributes_tag_allow_out_of_list"></a>

<table data-header-hidden><thead><tr><th width="190" align="center"></th><th width="453.6666666666667"></th></tr></thead><tbody><tr><td align="center">Value</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается логическое значение.</p></td></tr></tbody></table>

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

Значение, соответствующее реальному значению выбранного элемента.

Необязательный тэг. Значение тэга `<Value>`: любое значение.

Если введенное в поле текстовое значение совпадает по отображаемому значению с одним из элементов выпадающего списка, то значение объекта равно реальному значению соответствующего элемента выпадающего списка, иначе - введенному в поле значению.

```xml
<Value>Value</Value>
```

## Get-проперти для получения свойств <a href="#get_property_combobox" id="get_property_combobox"></a>

### EnterText <a href="#get_enter_text" id="get_enter_text"></a>

Возвращает признак, определяющий, может ли пользователь вводить текст внутри поля.

```xml
<Object Name="ComboBoxName">
  <Property Name="EnterText" />
</Object>
```

### MaxLength <a href="#get_max_length" id="get_max_length"></a>

Возвращает количество символов, которые пользователь может ввести внутри поля.

```xml
<Object Name="ComboBoxName">
  <Property Name="MaxLength" />
</Object>
```

### DropDownHeight <a href="#get_drop_down_height" id="get_drop_down_height"></a>

Возвращает высоту выпадающего списка.

```xml
<Object Name="ComboBoxName">
  <Property Name="DropDownHeight" />
</Object>
```

### DropDownWidth <a href="#get_drop_down_width" id="get_drop_down_width"></a>

Возвращает ширину выпадающего списка.

```xml
<Object Name="ComboBoxName">
  <Property Name="DropDownWidth" />
</Object>
```

### InputLanguage <a href="#get_input_language" id="get_input_language"></a>

Возвращает название языка для ограничения по вводимым символам.

```xml
<Object Name="ComboBoxName">
  <Property Name="InputLanguage" />
</Object>
```

### InputCase <a href="#get_input_case" id="get_input_case"></a>

Возвращает название типа регистра для ограничения по вводимым символам.

```xml
<Object Name="ComboBoxName">
  <Property Name="InputCase" />
</Object>
```

### Text <a href="#get_text" id="get_text"></a>

Возвращает отображаемое значение поля только в том случае, если реальное значение [`<Value>`](combobox.md#value) возвращает NULL.

```xml
<Object Name="ComboBoxName">
  <Property Name="Text" />
</Object>
```

### VisibleText <a href="#get_visible_text" id="get_visible_text"></a>

Возвращает отображаемое значение поля.

```xml
<Object Name="ComboBoxName">
  <Property Name="VisibleText" />
</Object>
```

### ValueList <a href="#get_value_list" id="get_value_list"></a>

Возвращает элементы выпадающего списка (таблица с двумя столбцами).

```xml
<Object Name="ComboBoxName">
  <Property Name="ValueList" />
</Object>
```

## Set-проперти для динамического задания свойств <a href="#set_property_combobox" id="set_property_combobox"></a>

### EnterText <a href="#set_enter_text" id="set_enter_text"></a>

Задает признак, определяющий, может ли пользователь вводить текст внутри поля.

Ожидается логическое значение.

```xml
<Object Name="ComboBoxName">
  <Property Name="EnterText">True</Property>
</Object>
```

### MaxLength <a href="#set_max_length" id="set_max_length"></a>

Задает количество символов, которые пользователь может ввести внутри поля.

Ожидается целочисленное значение.

```xml
<Object Name="ComboBoxName">
  <Property Name="MaxLength">200</Property>
</Object>
```

### DropDownHeight <a href="#set_drop_down_height" id="set_drop_down_height"></a>

Задает высоту выпадающего списка.

Ожидается целочисленное значение.

```xml
<Object Name="ComboBoxName">
  <Property Name="DropDownHeight">400</Property>
</Object>
```

### DropDownWidth <a href="#set_drop_down_width" id="set_drop_down_width"></a>

Задает ширину выпадающего списка.

Ожидается целочисленное значение.

```xml
<Object Name="ComboBoxName">
  <Property Name="DropDownWidth">300</Property>
</Object>
```

### InputLanguage <a href="#set_input_language" id="set_input_language"></a>

Задает название языка для ограничения по вводимым символам.

Ожидается один из языков.

```xml
<Object Name="ComboBoxName">
  <Property Name="InputLanguage">Rus</Property>
</Object>
```

### InputCase <a href="#set_input_case" id="set_input_case"></a>

Задает название типа регистра для ограничения по вводимым символам.

Ожидается один из типов регистров.

```xml
<Object Name="ComboBoxName">
  <Property Name="InputCase">Lower</Property>
</Object>
```

### Text <a href="#set_text" id="set_text"></a>

Задает отображаемое значение поля.

Любое значение будет переведено в текстовое.

Текстовое значение может быть присвоено только если основное значение [`<Value>`](combobox.md#value) равно NULL.

```xml
<Object Name="ComboBoxName">
  <Property Name="Text">Текст</Property>
</Object>
```

### ValueList <a href="#set_value_list" id="set_value_list"></a>

Задает элементы выпадающего списка.

Ожидается таблица с двумя столбцами (например, ссылка на [`GetDataConnection`](../dataconnections/) с указанием двух его полей).

```xml
<Object Name="ComboBoxName">
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
