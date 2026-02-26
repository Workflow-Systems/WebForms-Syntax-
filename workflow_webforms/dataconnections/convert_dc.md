---
description: >-
  Преобразующее загружающее соединение с данными; получает данные из другого
  загружающего соединения с данными и фильтрует их.
---

# ConvertDataConnection



## Шаблон ConvertDataConnection <a href="#template_convert_data_connection" id="template_convert_data_connection"></a>

```xml
<DataConnection Name="" Type="ConvertDataConnection" Assembly="WorkflowServer">
  <SourceDataConnection Name="" Query=""/>
  <ManualRefresh></ManualRefresh>
  <Fields>
    <Field Name="" Field=""/>
    <Field Field="" Type="Object">
      <Field Name="" />
    </Field>
    <Field Name="" Type="SubField" SubField="" Field=""/>
    <Field Name="" Field="" Type="Array">
      <Field Name="" />
    </Field>
    <Field Name="" Type="Value" DataType=""></Field>
    <Field Name="" Type="Format"></Field>
    <Field Name="" Type="Substitution" Field=""></Field>
    <Field Name="" Type="Replace" Field=""></Field>
    <Field Name="" Type="Action" Field=""></Field>
    <Field Name="" Type="TemplateFormat" Evaluate=""></Field>
  </Fields>
  <Filter>
    <And RefreshFilter="">
      <Or RefreshFilter="">
        <Filter Type="" FilterByNullValue="" RefreshFilter="" Reverse="">
          <Field NativeName="" />
          <Value></Value>
          <DataType Type="" />
          <Enabled>True</Enabled>
        </Filter>
        <Filter Type="" FilterByNullValue="" RefreshFilter="" Reverse="">
          <Field NativeName="" />
          <Value></Value>
          <DataType Type="" />
          <Enabled>True</Enabled>
        </Filter>
      </Or>
      <Not RefreshFilter="">
        <Filter Type="" FilterByNullValue="" RefreshFilter="" Reverse="">
          <Field NativeName="" />
          <Value></Value>
          <DataType Type="" />
          <Enabled>True</Enabled>
        </Filter>
      </Not>
    </And>
  </Filter>
</DataConnection>
```

## Описание ConvertDataConnection <a href="#description_convert_data_connection" id="description_convert_data_connection"></a>

```xml
<DataConnection Name="ConvertDataConnectionName" Type="ConvertDataConnection" Assembly="DataConnections">
  <!--Тэги, специфичные для ConvertDataConnection-->
</DataConnection>
```

## Тэги, специфичные для ConvertDataConnection <a href="#tags_convert_data_connection" id="tags_convert_data_connection"></a>

### SourceDataConnection <a href="#source_data_connection" id="source_data_connection"></a>

Соединение с данными, данные которого будут преобразованы и отфильтрованы.

Обязательный тэг. Значение тэга `<SourceDataConnection>`: не ожидается.

```xml
<SourceDataConnection Name="SourceDataConnectionName" Query="SqlQueryName" />
```

#### Атрибуты тэга `<SourceDataConnection>` <a href="#attributes_tag_source_data_connection" id="attributes_tag_source_data_connection"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="460.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Имя соединения с данными.</p><p></p><p>Обязательный атрибут. Ожидается имя одного из соединений с данными, описанных в форме.</p></td></tr><tr><td align="center">Query</td><td><p>Имя запроса из соединения с данными.</p><p></p><p>Необязательный атрибут. Ожидается имя одного из запросов из соединения с данными.</p></td></tr></tbody></table>

### ManualRefresh <a href="#manual_refresh" id="manual_refresh"></a>

Признак, определяющий, будет ли загрузка данных автоматически производиться при изменении первичного загружающего соединения-источника.

Необязательный тэг. Ожидается логическое значение.

По умолчанию используется значение True.

```xml
<ManualRefresh>True</ManualRefresh>
```

### Fields <a href="#fields" id="fields"></a>

[Список селекторов](convert_dc.md#selector_types) для выбора данных из соединения с данными.

Обязательный тэг. Значение тэга `<Fields>`: список тэгов [`<Field>`](convert_dc.md#fields_field).

Селекторы последовательно (в порядке объявления) преобразуют каждую строку исходного соединения с данными в результат соединения с данными.

На данный момент реализованы следующие селекторы:

1. Поле соединения с данными ([Field](convert_dc.md#selector_field));
2. Поля объекта ([Object](convert_dc.md#selector_object));
3. Вложенное поле объекта ([SubField](convert_dc.md#selector_sub_field));
4. Соединение массивов объектов ([Array](convert_dc.md#selector_array));
5. Значение ([Value](convert_dc.md#selector_value));
6. Форматирование строки ([Format](convert_dc.md#selector_format));
7. Подстановка значений ([Substitution](convert_dc.md#selector_substitution));
8. Замена значений ([Replace](convert_dc.md#selector_replace));
9. Работа с массивами ([Action](convert_dc.md#selector_action));
10. Форматирование строки по шаблону ([TemplateFormat](convert_dc.md#selector_template_format)).

```xml
<Fields>
  <Field Name="FieldName" Field="SourceFieldName"/>
  <Field Field="FieldName" Type="Object">
    <Field Name="SubFieldName" />
  </Field>
  <Field Name="FieldName" Type="SubField" Field="FieldName" SubField="SubFieldName"/>
  <Field Name="FieldName" Field="FieldName" Type="Array">
    <Field Name="FieldName" />
  </Field>
  <Field Name="FieldName" Type="Value" DataType="StringDataType">Value</Field>
  <Field Name="FieldName" Type="Format">{FieldName}</Field>
  <Field Name="FieldName" Type="Substitution" Field="FieldName"></Field>
  <Field Name="FieldName" Type="Replace" Field="FieldName"></Field>
  <Field Name="FieldName" Type="Action" Field="FieldName">Array Operations</Field>
  <Field Name="FieldName" Type="TemplateFormat" Evaluate="True">Template</Field>
</Fields>
```

#### Тэг `<Field>` <a href="#fields_field" id="fields_field"></a>

Селектор значения строки.

Необязательный тэг.&#x20;

#### Атрибуты тэга `<Field>, общие для всех селекторов` <a href="#attributes_tag_fields_field" id="attributes_tag_fields_field"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="483.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Название поля запроса, которое будет использоваться на форме.</p><p></p><p>Обязательный атрибут. Ожидается название одного из полей, которое будет использоваться на форме.</p></td></tr></tbody></table>

### Filter <a href="#filter" id="filter"></a>

Фильтр полученных данных.

Необязательный тэг. Значение тэга `<Filter>`: список тэгов [`<And>`](convert_dc.md#filter_and), [`<Or>`](convert_dc.md#filter_or) и [`<Not>`](convert_dc.md#filter_not) или тэги [`<Field>`](convert_dc.md#filter_field), [`<Value>`](convert_dc.md#filter_value), [`<DataType>`](convert_dc.md#filter_data_type) и [`<Enabled>`](convert_dc.md#filter_enabled).

```xml
<Filter>
  <And RefreshFilter="True">
    <Or RefreshFilter="True">
      <Filter Type="Equal" FilterByNullValue="True" RefreshFilter="True" Reverse="True">
        <Field NativeName="FieldName1" />
        <Value>Value</Value>
        <DataType Type="DataTypeName" />
        <Enabled>True</Enabled>
      </Filter>
      <Filter Type="Equal" FilterByNullValue="True" RefreshFilter="True" Reverse="True">
        <Field NativeName="FieldName2" />
        <Value>Value</Value>
        <Enabled>True</Enabled>
      </Filter>
    </Or>
    <Not RefreshFilter="True">
      <Filter Type="Equal" FilterByNullValue="True" RefreshFilter="True" Reverse="True">
        <Field NativeName="FieldName3" />
        <Value>Value</Value>
        <DataType Type="DataTypeName" />
        <Enabled>True</Enabled>
      </Filter>
    </Not>
  </And>
</Filter>
```

#### Атрибуты тэга `<Filter>` <a href="#attributes_tag_filter" id="attributes_tag_filter"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="483.3333333333333"></th></tr></thead><tbody><tr><td align="center">Type</td><td><p>Тип сравнения значений.</p><p></p><p>Необязательный атрибут. Ожидается название одного из <a href="convert_dc.md#filter_types">типов сравнения значений</a>.</p><p></p><p>Если атрибут <code>Type</code> отсутствует, то используется значение Equal.</p></td></tr><tr><td align="center">FilterByNullValue</td><td><p>Признак, определяющий, будет ли осуществляться фильтрация для очередной строки соединения с данными, если значение фильтра будет равно NULL.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>Если атрибут <code>FilterByNullValue</code> отсутствует, то используется значение True.</p></td></tr><tr><td align="center">RefreshFilter</td><td><p>Признак, определяющий, будут ли данные сразу же отфильтрованы при изменении параметра фильтра.</p><p>Признак не работает для фильтров, содержащих внутри себя тэги <code>&#x3C;And></code>, <code>&#x3C;Or></code> или <code>&#x3C;Not</code>>, для таких фильтров данные обновляются всегда.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>Если атрибут <code>RefreshFilter</code> отсутствует, то используется значение True.</p></td></tr><tr><td align="center">Reverse</td><td><p>Признак, определяющий, будет ли изменён порядок аргументов фильтра на обратный.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>Если атрибут <code>Reverse</code> отсутствует, то используется значение False.</p></td></tr></tbody></table>

#### Типы сравнения значений <a href="#filter_types" id="filter_types"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="483.3333333333333"></th></tr></thead><tbody><tr><td align="center">Equal</td><td>Сравнение значений на равенство</td></tr><tr><td align="center">NotEqual</td><td>Сравнение значений на неравенство</td></tr><tr><td align="center">Greater</td><td>Сравнение значений на "больше": значение из соединения с данными больше указанного значения</td></tr><tr><td align="center">NotGreater</td><td>Сравнение значений на "не больше": значение из соединения с данными не больше указанного значения</td></tr><tr><td align="center">Less</td><td>Сравнение значений на "меньше": значение из соединения с данными меньше указанного значения</td></tr><tr><td align="center">NotLess</td><td>Сравнение значений на "не меньше": значение из соединения с данными не меньше указанного значения</td></tr><tr><td align="center">Contains</td><td>Сравнение значений на "содержит": значение из соединения с данными содержит указанное значение (значения любых типов данных преобразуются к строковому типу)</td></tr><tr><td align="center">NotContains</td><td>Сравнение значений на "не содержит": значение из соединения с данными не содержит указанное значение (значения любых типов данных преобразуются к строковому типу)</td></tr><tr><td align="center">In</td><td>Сравнение значений на "входит": значение из соединения с данными входит в указанный массив</td></tr><tr><td align="center">NotIn</td><td>Сравнение значений на "не входит": значение из соединения с данными не входит в указанный массив</td></tr><tr><td align="center">Overlap</td><td>Сравнение значений на "пересекается": массив из соединения с данными имеет общие элементы с указанным массивом</td></tr><tr><td align="center">NotOverlap</td><td>Сравнение значений на "не пересекается": массив из соединения с данными не имеет общих элементов с указанным массивом</td></tr><tr><td align="center">MatchSearch</td><td>Сравнение значений на "удовлетворяет поисковой строке": поисковая строка может состоять из слов, разделенных пробелами и знаками "+", "*" и "?". Пробел означает "ИЛИ", "+" означает "И", "*" означает любое количество любых символов, "?" означат ровно один символ</td></tr><tr><td align="center">NotMatchSearch</td><td>Сравнение значений на "не удовлетворяет поисковой строке": поисковая строка может состоять из слов, разделенных пробелами и знаками "+", "*" и "?". Пробел означает "ИЛИ", "+" означает "И", "*" означает любое количество любых символов, "?" означат ровно один символ</td></tr><tr><td align="center">ContainedIn</td><td>Сравнение значений на "входит": значение из соединения с данными входит в указанное значение (значения любых типов данных преобразуются к строковому типу)</td></tr><tr><td align="center">NotContainedIn</td><td>Сравнение значений на "не входит": значение из соединения с данными не входит в указанное значение (значения любых типов данных преобразуются к строковому типу)</td></tr></tbody></table>

#### Тэг `<And>` <a href="#filter_and" id="filter_and"></a>

Логическое умножение нескольких фильтров.

Необязательный тэг. Значение тэга `<And>`: список тэгов [`<Filter>`](convert_dc.md#filter), [`<And>`](convert_dc.md#filter_and), [`<Or>`](convert_dc.md#filter_or) и [`<Not>`](convert_dc.md#filter_not).

#### Атрибуты тэга `<And>` <a href="#attributes_tag_filter_and" id="attributes_tag_filter_and"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="483.3333333333333"></th></tr></thead><tbody><tr><td align="center">RefreshFilter</td><td><p>Признак, определяющий, будут ли данные сразу же отфильтрованы при изменении вложенного фильтра.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>Если атрибут <code>RefreshFilter</code> отсутствует, то используется значение True.</p></td></tr></tbody></table>

#### Тэг `<Or>` <a href="#filter_or" id="filter_or"></a>

Логическое сложение нескольких фильтров.

Необязательный тэг. Значение тэга `<Or>`: список тэгов [`<Filter>`](convert_dc.md#filter), [`<And>`](convert_dc.md#filter_and), [`<Or>`](convert_dc.md#filter_or) и [`<Not>`](convert_dc.md#filter_not).

#### Атрибуты тэга `<Or>` <a href="#attributes_tag_filter_or" id="attributes_tag_filter_or"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="483.3333333333333"></th></tr></thead><tbody><tr><td align="center">RefreshFilter</td><td><p>Признак, определяющий, будут ли данные сразу же отфильтрованы при изменении вложенного фильтра.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>Если атрибут <code>RefreshFilter</code> отсутствует, то используется значение True.</p></td></tr></tbody></table>

#### Тэг `<Not>` <a href="#filter_not" id="filter_not"></a>

Логическое отрицание одного фильтра.

Необязательный тэг. Значение тэга `<Not>`: тэг [`<Filter>`](convert_dc.md#filter), [`<And>`](convert_dc.md#filter_and), [`<Or>`](convert_dc.md#filter_or) или [`<Not>`](convert_dc.md#filter_not).

#### Атрибуты тэга `<Not>` <a href="#attributes_tag_filter_not" id="attributes_tag_filter_not"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="483.3333333333333"></th></tr></thead><tbody><tr><td align="center">RefreshFilter</td><td><p>Признак, определяющий, будут ли данные сразу же отфильтрованы при изменении вложенного фильтра.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>Если атрибут <code>RefreshFilter</code> отсутствует, то используется значение True.</p></td></tr></tbody></table>

#### Тэг `<Field>` <a href="#filter_field" id="filter_field"></a>

Поле, по значению которого полученные данные фильтруются.

Обязательный тэг. Значение тэга `<Field>`: не ожидается.

#### Атрибуты тэга `<Field>` <a href="#attributes_tag_filter_field" id="attributes_tag_filter_field"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="483.3333333333333"></th></tr></thead><tbody><tr><td align="center">NativeName</td><td><p>Название поля, по значению которого полученные данные фильтруются.</p><p></p><p>Обязательный атрибут. Ожидается название одного из полей, описанных в теге Fields.</p></td></tr></tbody></table>

#### Тэг `<Value>` <a href="#filter_value" id="filter_value"></a>

Значение, по которому полученные данные фильтруются.

Обязательный тэг. Ожидается любое значение.

#### Тэг `<DataType>` <a href="#filter_data_type" id="filter_data_type"></a>

[Тип данных](/broken/pages/-MaRtBVKMO4VR0KCghVx), к которому приводятся сравниваемые значения.

Необязательный тэг. Значение тэга `<DataType>`: не ожидается.

Если тэг `<DataType>` отсутствует, то для атрибута `Type` используется значение StringDataType.

#### Атрибуты тэга `<DataType>` <a href="#attributes_tag_filter_data_type" id="attributes_tag_filter_data_type"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="483.3333333333333"></th></tr></thead><tbody><tr><td align="center">Type</td><td><p>Название типа данных.</p><p></p><p>Обязательный атрибут. Ожидается название одного из типов данных, поддерживаемых формой.</p></td></tr></tbody></table>

#### Тэг `<Enabled>` <a href="#filter_enabled" id="filter_enabled"></a>

Признак, определяющий, будет ли использоваться данный фильтр.

Необязательный тэг. Ожидается логическое значение.

## Список селекторов <a href="#selector_types" id="selector_types"></a>

### Поле соединения с данными (Field) <a href="#selector_field" id="selector_field"></a>

Селектор поля соединения с данными.

Значение тэга `<Field>`: не ожидается.

```xml
<Field Name="FieldName" Field="SourceFieldName"/>
```

#### Атрибуты тэга `<Field>`, специфичные для селектора Field <a href="#attributes_tag_selector_field" id="attributes_tag_selector_field"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="483.3333333333333"></th></tr></thead><tbody><tr><td align="center">Field</td><td><p>Название поля исходного соединения с данными.</p><p></p><p>Необязательный атрибут.<br><br>Если атрибут <code>Field</code> отсутствует, то используется значение из атрибута <code>Name</code>.</p></td></tr></tbody></table>

### Поля объекта (Object) <a href="#selector_object" id="selector_object"></a>

Селектор полей объекта. В результиующую таблицу будут добавлены поля вложенных селекторов.

Значение тэга `<Field>`: список тэгов [`<Field>`](convert_dc.md#fields_field).

```xml
<Field Field="FieldName" Type="Object">
  <Field Name="SubFieldName" />
</Field>
```

{% hint style="warning" %}
Поле исходного соединения должно быть словарём.
{% endhint %}

#### Атрибуты тэга `<Field>`, специфичные для селектора Object <a href="#attributes_tag_selector_object" id="attributes_tag_selector_object"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="483.3333333333333"></th></tr></thead><tbody><tr><td align="center">Field</td><td><p>Название поля исходного соединения с данными, из которого будут выбираться данные.</p><p></p><p>Обязательный атрибут.</p></td></tr><tr><td align="center">Type</td><td>Тип селектора.<br><br>Обязательный атрибут. Значение атрибута <code>Type</code>: фиксированное значение Object.</td></tr></tbody></table>

### Вложенное поле объекта (SubField) <a href="#selector_sub_field" id="selector_sub_field"></a>

Селектор вложенного поля.

В результат добавится значение поля вложенного объекта. Является короткой версий селектора полей объекта.

Значение тэга `<Field>`: не ожидается.

```xml
<Field Name="FieldName" Type="SubField" Field="FieldName" SubField="SubFieldName"/>
```

{% hint style="warning" %}
Поле исходного соединения должно быть словарём.
{% endhint %}

#### Атрибуты тэга `<Field>`, специфичные для селектора SubField <a href="#attributes_tag_selector_sub_field" id="attributes_tag_selector_sub_field"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="483.3333333333333"></th></tr></thead><tbody><tr><td align="center">Type</td><td>Тип селектора.<br><br>Обязательный атрибут. Значение атрибута <code>Type</code>: фиксированное значение SubField.</td></tr><tr><td align="center">Field</td><td><p>Название поля исходного соединения с данными.</p><p></p><p>Необязательный атрибут.</p><p></p><p>Если атрибут <code>Field</code> отсутствует, то используется значение из атрибута <code>Name</code>.</p></td></tr><tr><td align="center">SubField</td><td>Название вложенного поля.<br><br>Обязательный атрибут. Ожидается одно из полей объекта с названием заданным в атрибуте <code>Field</code> или <code>Name</code> (если атрибут <code>Field</code> отсутствует).</td></tr></tbody></table>

### Соединение массивов объектов (Array) <a href="#selector_array" id="selector_array"></a>

Селектор соединения массива объектов.

Может содержать любые селекторы. В результиующую таблицу будут добавлены поля вложенных селекторов.

Значение тэга `<Field>`: список тэгов [`<Field>`](convert_dc.md#fields_field).

```xml
<Field Name="FieldName" Field="FieldName" Type="Array">
  <Field Name="FieldName" />
</Field>
```

{% hint style="warning" %}
Поле исходного соединения должно быть словарём.
{% endhint %}

#### Атрибуты тэга `<Field>`, специфичные для селектора Array <a href="#attributes_tag_selector_array" id="attributes_tag_selector_array"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="483.3333333333333"></th></tr></thead><tbody><tr><td align="center">Type</td><td>Тип селектора.<br><br>Обязательный атрибут. Значение атрибута <code>Type</code>: фиксированное значение Array.</td></tr><tr><td align="center">Field</td><td><p>Название поля исходного соединения с данными.</p><p></p><p>Необязательный атрибут.</p><p></p><p>Если атрибут <code>Field</code> отсутствует, то используется значение из атрибута <code>Name</code>.</p></td></tr></tbody></table>

### Значение (Value) <a href="#selector_value" id="selector_value"></a>

Селектор значения.

Добавляет в результат столбец с заданным значением.

Значение тэга `<Field>`: любое значение.

```xml
<Field Name="FieldName" Type="Value" DataType="StringDataType">Value</Field>
```

#### Атрибуты тэга `<Field>`, специфичные для селектора Value <a href="#attributes_tag_selector_value" id="attributes_tag_selector_value"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="483.3333333333333"></th></tr></thead><tbody><tr><td align="center">Type</td><td>Тип селектора.<br><br>Обязательный атрибут. Значение атрибута <code>Type</code>: фиксированное значение Value.</td></tr><tr><td align="center">DataType</td><td>Тип данных, в который будет преобразовано значение.<br><br>Необязательный атрибут. Значение атрибута <code>DataType</code>: один из доступных <a href="/broken/pages/-MaRtBVKMO4VR0KCghVx">типов данных</a>.<br><br>Если атрибут <code>DataType</code> отсутствует, то используется значение StringDataType.</td></tr></tbody></table>

### Форматирование строки (Format) <a href="#selector_format" id="selector_format"></a>

Селектор форматирования строки.

Добавляет в результат столбец с результатом форматирования полей исходного соединения с данными.

Значение тэга `<Field>`: строка с форматом. В строке можно использовать значения полей в фигурных скобках - {FieldName}.

```xml
<Field Name="FieldName" Type="Format">{FieldName}</Field>
```

#### Атрибуты тэга `<Field>`, специфичные для селектора Format <a href="#attributes_tag_selector_format" id="attributes_tag_selector_format"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="483.3333333333333"></th></tr></thead><tbody><tr><td align="center">Type</td><td>Тип селектора.<br><br>Обязательный атрибут. Значение атрибута <code>Type</code>: фиксированное значение Format.</td></tr></tbody></table>

### Подстановка значений (Substitution) <a href="#selector_substitution" id="selector_substitution"></a>

Селектор подстановки значений.

Добавляет в результат значение выбранное из таблицы подстановки.

Ожидается матрица из 2-х столбцов.

```xml
<Field Name="FieldName" Type="Substitution" Field="FieldName"></Field>
```

#### Атрибуты тэга `<Field>`, специфичные для селектора Substitution <a href="#attributes_tag_selector_substitution" id="attributes_tag_selector_substitution"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="483.3333333333333"></th></tr></thead><tbody><tr><td align="center">Type</td><td>Тип селектора.<br><br>Обязательный атрибут. Значение атрибута <code>Type</code>: фиксированное значение Substitution.</td></tr><tr><td align="center">Field</td><td><p>Название поля исходного соединения с данными.</p><p></p><p>Необязательный атрибут.</p><p></p><p>Если атрибут <code>Field</code> отсутствует, то используется значение из атрибута <code>Name</code>.</p></td></tr></tbody></table>

### Замена значений (Replace) <a href="#selector_replace" id="selector_replace"></a>

Селектор замены значений.

Добавляет в результат столбец со значением исходного соединения с данными с заменой в нём подсрок с использованием таблицы замены.

Замена происходит следующим образом: исходное значение преобразуется в текстовое, затем в строке последовательно заменяется значение из первого столбца таблицы замены на значение второго столбца таблицы замены.

Ожидается матрица из 2-х столбцов.

```xml
<Field Name="FieldName" Type="Replace" Field="FieldName"></Field>
```

#### Атрибуты тэга `<Field>`, специфичные для селектора Replace <a href="#attributes_tag_selector_replace" id="attributes_tag_selector_replace"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="483.3333333333333"></th></tr></thead><tbody><tr><td align="center">Type</td><td>Тип селектора.<br><br>Обязательный атрибут. Значение атрибута <code>Type</code>: фиксированное значение Replace.</td></tr><tr><td align="center">Field</td><td><p>Название поля исходного соединения с данными.</p><p></p><p>Необязательный атрибут.</p><p></p><p>Если атрибут <code>Field</code> отсутствует, то используется значение из атрибута <code>Name</code>.</p></td></tr></tbody></table>

### Работа с массивами (Action) <a href="#selector_action" id="selector_action"></a>

Селектор работы с массивами.

Добавляет в результат соединения столбец с результатом преобразования массива из исходного соединения с данными.

Ожидается описание операций по работе с массивами.

```xml
<Field Name="FieldName" Type="Action" Field="FieldName">Array Operations</Field>
```

{% hint style="warning" %}
Поле исходнодного соединения должно быть массивом.
{% endhint %}

#### Атрибуты тэга `<Field>`, специфичные для селектора Action <a href="#attributes_tag_selector_action" id="attributes_tag_selector_action"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="483.3333333333333"></th></tr></thead><tbody><tr><td align="center">Type</td><td>Тип селектора.<br><br>Обязательный атрибут. Значение атрибута <code>Type</code>: фиксированное значение Action.</td></tr><tr><td align="center">Field</td><td><p>Название поля исходного соединения с данными.</p><p></p><p>Необязательный атрибут.</p><p></p><p>Если атрибут <code>Field</code> отсутствует, то используется значение из атрибута <code>Name</code>.</p></td></tr></tbody></table>

### Форматирование строки по шаблону (TemplateFormat) <a href="#selector_template_format" id="selector_template_format"></a>

Селектор форматирования строки по шаблону.

Добавляет в результат столбец с результатом форматирования полей исходного соединения с данными на основе заданного шаблона.

В качестве шаблонизатора используется Scriban. Подробнее по [ссылке](https://github.com/lunet-io/scriban).

Ожидается строка с шаблоном.

```xml
<Field Name="FieldName" Type="TemplateFormat" Evaluate="True">Template</Field>
```

#### Атрибуты тэга `<Field>`, специфичные для селектора TemplateFormat <a href="#attributes_tag_selector_template_format" id="attributes_tag_selector_template_format"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="483.3333333333333"></th></tr></thead><tbody><tr><td align="center">Type</td><td>Тип селектора.<br><br>Обязательный атрибут. Значение атрибута <code>Type</code>: фиксированное значение Action.</td></tr><tr><td align="center">Evaluate</td><td><p>Признак, определяющий что нужно вычислить выражение.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p></td></tr></tbody></table>

## Get-проперти для получения свойств <a href="#get_property_primary_dc" id="get_property_primary_dc"></a>

### Count <a href="#get_count" id="get_count"></a>

Возвращает количество строк в указанном запроса загружающего соединения с данными.

Ожидается имя одного из запросов, описанных в загружающем соединении с данными. Если имя запроса не указано, то используется первый запрос (в порядке описания запросов).

```xml
<DataConnection SourceDataConnection="ConvertDataConnectionName">
  <Property Name="Count">SqlQueryName</Property>
</DataConnection>
```

### ValueChanged <a href="#get_value_changed" id="get_value_changed"></a>

Возвращает признак изменения данных DataConnection.

```xml
<DataConnection SourceDataConnection="ConvertDataConnectionName">
  <Property Name="ValueChanged" />
</DataConnection>
```

### RowIndexOf <a href="#get_row_index_of" id="get_row_index_of"></a>

Возвращает индекс строки, удовлетворяющей условиям соответствия названий столбцов и значений в этих столбцах.

```xml
<DataConnection SourceDataConnection="ConvertDataConnectionName">
  <Property Name="RowIndexOf">
    <Parameters>
      <Parameter Name="ColumnNames">
        <Structure Type="List">
          <Item>ColumnName1</Item>
          <Item>ColumnName2</Item>
        </Structure>
      </Parameter>
      <Parameter Name="Values">
        <Structure Type="List">
          <Item>Value1</Item>
          <Item>Value2</Item>
        </Structure>
      </Parameter>
    </Parameters>
  </Property>
</DataConnection>
```

Параметр **ColumnNames** ожидает линейный массив названий полей DataConnection.

Параметр **Values** ожидает линейный массив любых значений, по которым будет произведен поиск в соответствующих полях.

### RowsIndicesOf <a href="#get_rows_indices_of" id="get_rows_indices_of"></a>

Возвращает массив индексов строки, удовлетворяющих условиям соответствия названий столбцов и значений в этих столбцах.

```xml
<DataConnection SourceDataConnection="ConvertDataConnectionName">
  <Property Name="RowsIndicesOf">
    <Parameters>
      <Parameter Name="ColumnNames">
        <Structure Type="List">
          <Item>ColumnName1</Item>
          <Item>ColumnName2</Item>
        </Structure>
      </Parameter>
      <Parameter Name="Values">
        <Structure Type="List">
          <Item>Value1</Item>
          <Item>
            <Structure Type="List">
              <Item>Value2</Item>
              <Item>Value3</Item>
            </Structure>
          </Item>
        </Structure>
      </Parameter>
      <Parameter Name="SearchWithArrays">False</Parameter>
    </Parameters>
  </Property>
</DataConnection>
```

Параметр **ColumnNames** ожидает линейный массив названий полей DataConnection.

Параметр **Values** ожидает линейный массив любых значений, по которым будет произведен поиск в соответствующих полях.

Необязательный параметр **SearchWithArrays** разрешает для каждого столбца использовать линейный массив значений, с элементами которого будет сравниваться значения из каждой строки соответствующего столбца. Ожидается логическое значение. По умолчанию используется значение False.

### Column

Возвращает линейный массив значений, содержащихся в определенном столбце таблицы.

```xml
<DataConnection SourceDataConnection="ConvertDataConnectionName">
  <Property Name="Column">
    <Parameters>
      <Parameter Name="ColumnName">ColumnName</Parameter>
    </Parameters>
  </Property>  
</DataConnection>
```

Параметр **ColumnName** ожидает название одного из полей DataConnection.

## Set-проперти для динамического задания свойств

### AddRow <a href="#set_add_row" id="set_add_row"></a>

Добавляет новую строку в таблицу DataConnection.

```xml
<DataConnection Name="ConvertDataConnectionName">
  <Property Name="AddRow">
    <Parameters>
      <Parameter Name="ColumnNames">
        <Structure Type="List">
          <Item>ColumnName1</Item>
          <Item>ColumnName2</Item>
        </Structure>
      </Parameter>
      <Parameter Name="Values">
        <Structure Type="List">
          <Item>Value1</Item>
          <Item>Value2</Item>
        </Structure>
      </Parameter>
      <Parameter Name="Index">0</Parameter>
      <Parameter Name="FireChanged">False</Parameter>
    </Parameters>
  </Property>
</DataConnection>
```

Параметр **ColumnNames** ожидает линейный массив названий полей DataConnection.

Параметр **Values** ожидает линейный массив любых значений, которые будут записаны в соответствующие поля новой строки.

Необязательный параметр **Index** ожидает неотрицательное целочисленное значение, указывающее место вставки новой строки. Если параметр отсутствует, то строка добавляется в конец таблицы DataConnection.

Необязательный параметр **FireChanged** - признак того, что соединение с данными будет рассылать событие об изменении данных при выполнении set-проперти. Ожидается логическое значение. По умолчанию используется значение True.

### AddRows <a href="#set_add_rows" id="set_add_rows"></a>

Добавляет новые строки в таблицу DataConnection.

```xml
<DataConnection Name="ConvertDataConnectionName">
  <Property Name="AddRows">
    <Parameters>
      <Parameter Name="ColumnNames">
        <Structure Type="List">
          <Item>ColumnName1</Item>
          <Item>ColumnName2</Item>
        </Structure>
      </Parameter>
      <Parameter Name="Values">
        <DataConnection SourceDataConnection="SourceDataConnectionName">
          <Fields>
            <Field Name="ColumnName1" />
            <Field Name="ColumnName2" />
          </Fields>
        </DataConnection>
      </Parameter>
      <Parameter Name="Index">0</Parameter>
      <Parameter Name="RawValues">True</Parameter>
      <Parameter Name="FireChanged">False</Parameter>
    </Parameters>
  </Property>
</DataConnection>
```

Параметр **ColumnNames** ожидает линейный массив названий полей DataConnection.

Параметр **Values** ожидает таблицу (например, ссылка на GetDataConnection) с числом столбцов равным числу имен столбцов, указанных в параметре ColumnNames. Допустимо указывать линейный массив, который будет соответствовать одной строке.

Необязательный параметр **Index** ожидает неотрицательное целочисленное значение, указывающее место вставки новой строки. Если параметр отсутствует, то строка добавляется в конец таблицы DataConnection.

Необязательный параметр **RawValues** - признак того, что значения необходимо подставлять "как они есть" - без преобразования в массив скалярных значений. Ожидается логическое значение. По умолчанию используется значение False.

Необязательный параметр **FireChanged** - признак того, что соединение с данными будет рассылать событие об изменении данных при выполнении set-проперти. Ожидается логическое значение. По умолчанию используется значение True.

### UpdateRow <a href="#set_update_row" id="set_update_row"></a>

Изменяет значения полей в строке с указанным индексом.

```xml
<DataConnection Name="ConvertDataConnectionName">
  <Property Name="UpdateRow">
    <Parameters>
      <Parameter Name="RowIndex">0</Parameter>
      <Parameter Name="ColumnNames">
        <Structure Type="List">
          <Item>ColumnName1</Item>
          <Item>ColumnName2</Item>
        </Structure>
      </Parameter>
      <Parameter Name="Values">
        <Structure Type="List">
          <Item>Value1</Item>
          <Item>Value2</Item>
        </Structure>
      </Parameter>
      <Parameter Name="RawValues">True</Parameter>
      <Parameter Name="FireChanged">False</Parameter>
    </Parameters>
  </Property>
</DataConnection>
```

Параметр **ColumnNames** ожидает линейный массив названий полей DataConnection.

Параметр **Values** ожидает линейный массив любых значений.

Параметр **RowIndex** ожидает неотрицательное целочисленное значение, указывающее на индекс строки для изменения.

Необязательный параметр **RawValues** - признак того, что значения необходимо подставлять "как они есть" - без преобразования в массив скалярных значений. Ожидается логическое значение. По умолчанию используется значение False.

Необязательный параметр **FireChanged** - признак того, что соединение с данными будет рассылать событие об изменении данных при выполнении set-проперти. Ожидается логическое значение. По умолчанию используется значение True.

### UpdateRows <a href="#set_update_rows" id="set_update_rows"></a>

Изменяет значения полей в строках с указанными индексами на соответствующее значение из массива.

```xml
<DataConnection Name="ConvertDataConnectionName">
  <Property Name="UpdateRows">
    <Parameters>
      <Parameter Name="RowIndices">
        <Structure Type="List">
          <Item>1</Item>
          <Item>2</Item>
        </Structure>
      </Parameter>
      <Parameter Name="ColumnNames">
        <Structure Type="List">
          <Item>ColumnName1</Item>
          <Item>ColumnName2</Item>
        </Structure>
      </Parameter>
      <Parameter Name="Values">
        <Structure Type="List">
          <Item>Value1</Item>
          <Item>Value2</Item>
        </Structure>
      </Parameter>
      <Parameter Name="ReplicateValues">False</Parameter>
      <Parameter Name="RawValues">True</Parameter>
      <Parameter Name="FireChanged">False</Parameter>
    </Parameters>
  </Property>
</DataConnection>
```

Параметр **ColumnNames** ожидает линейный массив названий полей DataConnection.

Параметр **Values** ожидает линейный массив или матрицу любых значений.

Параметр **RowIndices** ожидает линейный массив неотрицательных целочисленных значений, указывающих на индексы строк для изменения.

Необязательный параметр **ReplicateValues** - признак, определяющий каким образом обрабатывать значение параметра Values. Ожидает логическое значение. По умолчанию используется значение True.

Если значение параметра _False_, то значение параметра Values рассматривается как _матрица значений_, которые будут записаны в строки с индексами, указанными в параметре RowIndices. При этом:

* если количество элементов строки матрицы не совпадает с количеством полей, указанных в параметре ColumnNames, то в соответствующие ячейки ставится значение NULL;&#x20;
* если количество строк матрицы не совпадает с количеством индексов, указанных в параметре RowIndices, то в ячейки строки, у которых отсутствует строка в матрице, ставится значение NULL.

Если значение параметра _True_, то значение параметра Values рассматривается как _линейный массив значений_, который заполняет каждую строку, подставляя элементы в соответствующие колонки.

Необязательный параметр **RawValues** - признак того, что значения необходимо подставлять "как они есть" - без преобразования в массив скалярных значений. Ожидается логическое значение. По умолчанию используется значение False.

Необязательный параметр **FireChanged** - признак того, что соединение с данными будет рассылать событие об изменении данных при выполнении set-проперти. Ожидается логическое значение. По умолчанию используется значение True.

### UpdateColumn <a href="#set_update_column" id="set_update_column"></a>

Построчно изменяет значения строк в заданном поле на соответствующие значения из массива.

```xml
<DataConnection Name="ConvertDataConnectionName">
  <Property Name="UpdateColumn">
    <Parameters>
      <Parameter Name="ColumnName">ColumnName</Parameter>
      <Parameter Name="Values">
        <Structure Type="List">
          <Item>Value1</Item>
          <Item>Value2</Item>
        </Structure>
      </Parameter>
      <Parameter Name="RawValues">True</Parameter>
      <Parameter Name="FireChanged">False</Parameter>
    </Parameters>
  </Property>
</DataConnection>
```

Параметр **ColumnName** ожидает название поля DataConnection.

Параметр **Values** ожидает линейный массив любых значений. Если длина массива меньше количества строк в соединении с данными, то оставшиеся строки не будут изменяться. Если длина массива больше, то оставшиеся значения будут отброшены.

Необязательный параметр **RawValues** - признак того, что значения необходимо подставлять "как они есть" - без преобразования в массив скалярных значений. Ожидается логическое значение. По умолчанию используется значение False.

Необязательный параметр **FireChanged** - признак того, что соединение с данными будет рассылать событие об изменении данных при выполнении set-проперти. Ожидается логическое значение. По умолчанию используется значение True.

### UpdateColumnCellsValues <a href="#set_update_column_cells_values" id="set_update_column_cells_values"></a>

Изменяет значение поля в строках с указанными индексами на заданное значение.

```xml
<DataConnection Name="ConvertDataConnectionName">
  <Property Name="UpdateColumnCellsValues">
    <Parameters>
      <Parameter Name="ColumnName">ColumnName</Parameter>
      <Parameter Name="RowIndices">
        <Structure Type="List">
          <Item>1</Item>
          <Item>2</Item>
        </Structure>
      </Parameter>
      <Parameter Name="Value">Value</Parameter>
      <Parameter Name="RawValues">True</Parameter>
      <Parameter Name="FireChanged">False</Parameter>
    </Parameters>
  </Property>
</DataConnection>
```

Параметр **ColumnName** ожидает название поля DataConnection.

Параметр **Value** ожидает значение, которое будет подставляться в поле.

Необязательный параметр **RowIndices** ожидает линейный массив неотрицательных целочисленных значений, указывающих на индексы строк. Если параметр не указан, то обновятся все строки.

Необязательный параметр **FireChanged** - признак того, что соединение с данными будет рассылать событие об изменении данных при выполнении set-проперти. Ожидается логическое значение. По умолчанию используется значение True.

### DeleteRowsByIndices <a href="#set_delete_rows_by_indices" id="set_delete_rows_by_indices"></a>

Удаляет строки с указанными индексами.

```xml
<DataConnection Name="ConvertDataConnectionName">
  <Property Name="UpdateColumnCellsValues">
    <Parameters>
      <Parameter Name="Value">
        <Structure Type="List">
          <Item>1</Item>
          <Item>2</Item>
        </Structure>
      </Parameter>
      <Parameter Name="FireChanged">False</Parameter>
    </Parameters>
  </Property>
</DataConnection>
```

Необязательный параметр **Value** ожидает линейный массив неотрицательных целочисленных значений. Если параметр отсутствует, то удаляются все строки.

Необязательный параметр **FireChanged** - признак того, что соединение с данными будет рассылать событие об изменении данных при выполнении set-проперти, а так же будет изменяться свойство ValueChanged. Ожидается логическое значение. По умолчанию используется значение True.

### FireChanged <a href="#set_fire_changed" id="set_fire_changed"></a>

Рассылает событие об изменении данных.

Значение не ожидается.

```xml
<DataConnection Name="ConvertDataConnectionName">
  <Property Name="FireChanged" />
</DataConnection>
```

### ValueChanged <a href="#set_value_changed" id="set_value_changed"></a>

Задает признак изменения значения соединения с данными.

Ожидается логическое значение.

```xml
<DataConnection Name="ConvertDataConnectionName">
  <Property Name="ValueChanged">False</Property>
</DataConnection>
```
