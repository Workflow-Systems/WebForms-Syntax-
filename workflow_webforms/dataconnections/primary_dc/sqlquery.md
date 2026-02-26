---
description: Запрос для получения данных с сервера.
---

# SqlQuery

## Шаблон SqlQuery <a href="#template_primary_dc" id="template_primary_dc"></a>

```xml
<SqlQuery Name="" Type="Select">
  <ManualLoad></ManualLoad> 
  <Workflow Name="" />
  <Fields>
    <Field Name="" NativeName="" />
    <Field Name="" Type="FormatField" FormatString="">
      <Field NativeName="" />
      <Field NativeName="" />
    </Field>
  </Fields>
  <Parameters>
    <Parameter NativeName="" RefreshQuery="" SendAsArray="">
      <Value></Value>
      <IfNull></IfNull>
      <IfEmpty></IfEmpty>
    </Parameter>
  </Parameters>
  <Filter>
    <And RefreshFilter="">
      <Or RefreshFilter="">
        <Filter Type="" FilterByNullValue="" RefreshFilter="" Reverse="">
          <Field NativeName="" />
          <Value></Value>
          <DataType Type="" />
          <Enabled></Enabled>
        </Filter>
        <Filter Type="" FilterByNullValue="" RefreshFilter="" Reverse="">
          <Field NativeName="" />
          <Value></Value>
          <DataType Type="" />
          <Enabled></Enabled>
        </Filter>
      </Or>
      <Not RefreshFilter="">
        <Filter Type="" FilterByNullValue="" RefreshFilter="" Reverse="">
          <Field NativeName="" />
          <Value></Value>
          <DataType Type="" />
          <Enabled></Enabled>
        </Filter>
      </Not>
    </And>
  </Filter>
</SqlQuery>
```

## Описание SqlQuery <a href="#description_primary_dc" id="description_primary_dc"></a>

```xml
<SqlQuery Name="">
  <ManualLoad></ManualLoad> 
  <Workflow Name="" />
  <Fields> </Fields>
  <Parameters></Parameters>
  <Filter></Filter>
</SqlQuery>
```

## Тэги, специфичные для SqlQuery <a href="#option_1_tags_primary_dc" id="option_1_tags_primary_dc"></a>

### ManualLoad <a href="#sql_query_manual_load" id="sql_query_manual_load"></a>

Признак, определяющий, будет ли загрузка данных происходить только после ручного обновления соединения с данными, а не вместе с загрузкой формы.

Необязательный тэг. Ожидается логическое значение.

Если тэг `<ManualLoad>` отсутствует, то используется значение тэга [`<ManualLoad>`](sqlquery.md#manual_load) соединения с данными.

```xml
<ManualLoad>False</ManualLoad>
```

### Workflow <a href="#sql_query_workflow" id="sql_query_workflow"></a>

Процесс, в рамках которого происходит запрос.

Обязательный тэг. Значение тэга не ожидается.

```xml
<Workflow Name="WorkflowName" />
```

В качестве значения атрибута `Name` ожидается название одного из процессов, расположенных на сервере и заголовочно описанных в базе данных в таблице public.workflow\_type.

### Fields <a href="#sql_query_fields" id="sql_query_fields"></a>

Список полей запроса.

Обязательный тэг. Ожидается список тегов `<Field>`.

```xml
<Fields>
  <Field Name="field_name1" />
  <Field Name="FieldName2" NativeName="field_name2" />
  <Field Name="FieldName3" Type="FormatField" FormatString="{0} ({1})">
    <Field NativeName="field_name3" />
    <Field NativeName="field_name4" />
  </Field>
</Fields>
```

#### Атрибуты тэга `<Field>` <a href="#attributes_tag_sql_query_fields_field" id="attributes_tag_sql_query_fields_field"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="459.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Название поля запроса, которое будет использоваться на форме.</p><p></p><p>Обязательный атрибут. Ожидается любое значение, если атрибут <code>NativeName</code> присутствует, или ожидается название одного из полей, возвращаемых запросом, если атрибут <code>NativeName</code> отсутствует.</p></td></tr><tr><td align="center">NativeName</td><td><p>Название поля запроса, описанного на сервере.</p><p></p><p>Необязательный атрибут. Ожидается название одного из полей, возвращаемых запросом.</p><p></p><p>Суть связи атрибутов <code>Name</code> и <code>NativeName</code> - переименование полей запроса.</p></td></tr><tr><td align="center">Type</td><td><p>Тип поля.</p><p></p><p>Необязательный атрибут. Ожидается тип FormatField.</p></td></tr><tr><td align="center">FormatString</td><td><p>Задает формат строки для объединения значений нескольких полей.</p><p></p><p>Необязательный атрибут. Значение атрибута любая строка, поддерживающая выражения вида "{n}", где n - индекс (начиная с 0) вложенного поля.</p></td></tr></tbody></table>

### Parameters <a href="#sql_query_parameters" id="sql_query_parameters"></a>

Параметры, передаваемые в запрос.

Необязательный тэг. Ожидается список тэгов `<Parameter>`.

```xml
<Parameters>
  <Parameter NativeName="NativeName" RefreshQuery="False" SendAsArray="True">
    <Value>Value</Value>
    <IfNull>Value</IfNull>
    <IfEmpty>Value</IfEmpty>
  </Parameter>
</Parameters>
```

#### Атрибуты тэга `<Parameter>` <a href="#attributes_tag_sql_query_parameters_parameter" id="attributes_tag_sql_query_parameters_parameter"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="459.3333333333333"></th></tr></thead><tbody><tr><td align="center">NativeName</td><td><p>Название параметра, которое используется в описании запроса на сервере.</p><p></p><p>Обязательный атрибут. Ожидается название одного из параметров, использующихся в описании запроса на сервере.</p></td></tr><tr><td align="center">RefreshQuery</td><td><p>Признак, определяющий, будут ли обновлены данные запроса при изменении параметра.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>Если атрибут <code>RefreshQuery</code> отсутствует, то используется значение True.</p></td></tr><tr><td align="center">SendAsArray</td><td><p>Признак, определяющий будет ли значение передаваться как массив.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>Если атрибут <code>SendAsArray</code> отсутствует, то используется значение False.</p></td></tr></tbody></table>

{% hint style="info" %}
Применять значение False для атрибута `RefreshQuery` имеет смысл тогда, когда обновляется более одного параметра запроса одновременно, но при этом нет необходимости выполнять запросы отдельно при обновлении каждого параметра.
{% endhint %}

#### Вложенные тэги тэга `<Parameter>` <a href="#tags_sql_query_parameters_parameter" id="tags_sql_query_parameters_parameter"></a>

* **Value** - значение параметра. Обязательный тэг. Ожидается любое значение;
* **IfNull** - значение, которое будет передано в качестве значение параметра, если последний в тэге `<Value>` имеет значение NULL. Необязательный тэг. Ожидается любое значение;
* **IfEmpty** - значение, которое будет передано в качестве значение параметра, если последний в тэге `<Value>` имеет значение "". Необязательный тэг. Ожидается любое значение.

### Filter <a href="#sql_query_filter" id="sql_query_filter"></a>

Фильтр полученных данных.

Фильтрация происходит без повторных запросов в базу данных.

Необязательный тэг. Значение тэга `<Filter>`: список тэгов [`<And>`](sqlquery.md#sql_query_filter_and), [`<Or>`](sqlquery.md#sql_query_filter_or) и [`<Not>`](sqlquery.md#sql_query_filter_not) или тэги [`<Field>`](sqlquery.md#sql_query_filter_field), [`<Value>`](sqlquery.md#sql_query_filter_value) и [`<DataType>`](sqlquery.md#sql_query_filter_data_type).

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

#### Атрибуты тэга `<Filter>` <a href="#attributes_tag_sql_query_filter" id="attributes_tag_sql_query_filter"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="459.3333333333333"></th></tr></thead><tbody><tr><td align="center">Type</td><td><p>Тип сравнения значений.</p><p></p><p>Необязательный атрибут. Ожидается название одного из <a href="sqlquery.md#filter_types">типов сравнения</a> значений.</p><p></p><p>Если атрибут <code>Type</code> отсутствует, то используется значение Equal.</p></td></tr><tr><td align="center">FilterByNullValue</td><td><p>Признак, определяющий, будет ли осуществляться фильтрация для очередной строки соединения с данными, если значение фильтра будет равно NULL.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>Если атрибут <code>FilterByNullValue</code> отсутствует, то используется значение True.</p></td></tr><tr><td align="center">RefreshFilter</td><td><p>Признак, определяющий, будут ли данные сразу же отфильтрованы при изменении параметра фильтра.</p><p>Признак не работает для фильтров, содержащих внутри себя тэги <a href="sqlquery.md#sql_query_filter_and"><code>&#x3C;And></code></a>, <a href="sqlquery.md#sql_query_filter_or"><code>&#x3C;Or></code></a> или <a href="sqlquery.md#sql_query_filter_not"><code>&#x3C;Not></code></a>, для таких фильтров данные обновляются всегда.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>Если атрибут <code>RefreshFilter</code> отсутствует, то используется значение True.</p></td></tr><tr><td align="center">Reverse</td><td><p>Признак, определяющий, будет ли изменён порядок аргументов фильтра на обратный.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>Если атрибут <code>Reverse</code> отсутствует, то используется значение False.</p></td></tr></tbody></table>

#### Типы сравнения значений <a href="#filter_types" id="filter_types"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="459.3333333333333"></th></tr></thead><tbody><tr><td align="center">Equal</td><td>Сравнение значений на равенство</td></tr><tr><td align="center">NotEqual</td><td>Сравнение значений на неравенство</td></tr><tr><td align="center">Greater</td><td>Сравнение значений на "больше": значение из соединения с данными больше указанного значения</td></tr><tr><td align="center">NotGreater</td><td>Сравнение значений на "не больше": значение из соединения с данными не больше указанного значения</td></tr><tr><td align="center">Less</td><td>Сравнение значений на "меньше": значение из соединения с данными меньше указанного значения</td></tr><tr><td align="center">NotLess</td><td>Сравнение значений на "не меньше": значение из соединения с данными не меньше указанного значения</td></tr><tr><td align="center">Contains</td><td>Сравнение значений на "содержит": значение из соединения с данными содержит указанное значение (значения любых типов данных преобразуются к строковому типу)</td></tr><tr><td align="center">NotContains</td><td>Сравнение значений на "не содержит": значение из соединения с данными не содержит указанное значение (значения любых типов данных преобразуются к строковому типу)</td></tr><tr><td align="center">In</td><td>Сравнение значений на "входит": значение из соединения с данными входит в указанный массив</td></tr><tr><td align="center">NotIn</td><td>Сравнение значений на "не входит": значение из соединения с данными не входит в указанный массив</td></tr><tr><td align="center">Overlap</td><td>Сравнение значений на "пересекается": массив из соединения с данными имеет общие элементы с указанным массивом</td></tr><tr><td align="center">NotOverlap</td><td>Сравнение значений на "не пересекается": массив из соединения с данными не имеет общих элементов с указанным массивом</td></tr><tr><td align="center">MatchSearch</td><td>Сравнение значений на "удовлетворяет поисковой строке": поисковая строка может состоять из слов, разделенных пробелами и знаками "+", "*" и "?"<em>,</em> пробел означает "ИЛИ", "+" означает "И", "*" означает любое количество любых символов, "?" означат ровно один символ</td></tr><tr><td align="center">NotMatchSearch</td><td>Сравнение значений на "не удовлетворяет поисковой строке": поисковая строка может состоять из слов, разделенных пробелами и знаками "+", "*" и "?"<em>,</em> пробел означает "ИЛИ", "+" означает "И", "*" означает любое количество любых символов, "?" означат ровно один символ</td></tr><tr><td align="center">ContainedIn</td><td>Сравнение значений на "входит": значение из соединения с данными входит в указанное значение (значения любых типов данных преобразуются к строковому типу)</td></tr><tr><td align="center">NotContainedIn</td><td>Сравнение значений на "не входит": значение из соединения с данными не входит в указанное значение (значения любых типов данных преобразуются к строковому типу)</td></tr></tbody></table>

#### Тэг `<And>` <a href="#sql_query_filter_and" id="sql_query_filter_and"></a>

Логическое умножение нескольких фильтров.

Необязательный тэг. Значение тэга `<And>`: список тэгов [`<Filter>`](sqlquery.md#sql_query_filter), `<And>`, [`<Or>`](sqlquery.md#sql_query_filter_or) и [`<Not>`](sqlquery.md#sql_query_filter_not).

#### Атрибуты тэга `<And>` <a href="#attributes_tag_sql_query_filter_and" id="attributes_tag_sql_query_filter_and"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="459.3333333333333"></th></tr></thead><tbody><tr><td align="center">RefreshFilter</td><td><p>Признак, определяющий, будут ли данные сразу же отфильтрованы при изменении вложенного фильтра.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>Если атрибут <code>RefreshFilter</code> отсутствует, то используется значение True.</p></td></tr></tbody></table>

#### Тэг `<Or>` <a href="#sql_query_filter_or" id="sql_query_filter_or"></a>

Логическое сложение нескольких фильтров.

Необязательный тэг. Значение тэга `<Or>`: список тэгов [`<Filter>`](sqlquery.md#sql_query_filter), [`<And>`](sqlquery.md#sql_query_filter_and), `<Or>` и [`<Not>`](sqlquery.md#sql_query_filter_not).

#### Атрибуты тэга `<Or>` <a href="#attributes_tag_sql_query_filter_or" id="attributes_tag_sql_query_filter_or"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="459.3333333333333"></th></tr></thead><tbody><tr><td align="center">RefreshFilter</td><td><p>Признак, определяющий, будут ли данные сразу же отфильтрованы при изменении вложенного фильтра.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>Если атрибут <code>RefreshFilter</code> отсутствует, то используется значение True.</p></td></tr></tbody></table>

#### Тэг `<Not>` <a href="#sql_query_filter_not" id="sql_query_filter_not"></a>

Логическое отрицание одного фильтра.

Необязательный тэг. Значение тэга `<Not>`: тэг [`<Filter>`](sqlquery.md#sql_query_filter), [`<And>`](sqlquery.md#sql_query_filter_and), [`<Or>`](sqlquery.md#sql_query_filter_or) и `<Not>`.

#### Атрибуты тэга `<Not>` <a href="#attributes_tag_sql_query_filter_not" id="attributes_tag_sql_query_filter_not"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="459.3333333333333"></th></tr></thead><tbody><tr><td align="center">RefreshFilter</td><td><p>Признак, определяющий, будут ли данные сразу же отфильтрованы при изменении вложенного фильтра.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>Если атрибут <code>RefreshFilter</code> отсутствует, то используется значение True.</p></td></tr></tbody></table>

#### Тэг `<Field>` <a href="#sql_query_filter_field" id="sql_query_filter_field"></a>

Поле, по значению которого полученные данные фильтруются.

Обязательный тэг. Значение тэга `<Field>`: не ожидается.

#### Атрибуты тэга `<Field>` <a href="#attributes_tag_sql_query_filter_field" id="attributes_tag_sql_query_filter_field"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="459.3333333333333"></th></tr></thead><tbody><tr><td align="center">NativeName</td><td><p>Название поля, по значению которого полученные данные фильтруются.</p><p></p><p>Обязательный атрибут. Ожидается название одного из полей, описанных в тэге <a href="sqlquery.md#sql_query_fields"><code>&#x3C;Fields></code></a>.</p></td></tr></tbody></table>

#### Тэг `<Value>` <a href="#sql_query_filter_value" id="sql_query_filter_value"></a>

Значение, по которому полученные данные фильтруются.

Обязательный тэг. Ожидается любое значение.

#### Тэг `<DataType>` <a href="#sql_query_filter_data_type" id="sql_query_filter_data_type"></a>

[Тип данных](/broken/pages/-MaRtBVKMO4VR0KCghVx), к которому приводятся сравниваемые значения.

Необязательный тэг. Значение тэга `<DataType>`: не ожидается.

Если тэг `<DataType>` отсутствует, то для атрибута `Type` используется значение StringDataType.

#### Атрибуты тэга `<DataType>` <a href="#attributes_tag_sql_query_filter_data_type" id="attributes_tag_sql_query_filter_data_type"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="459.3333333333333"></th></tr></thead><tbody><tr><td align="center">Type</td><td><p>Название типа данных.</p><p></p><p>Обязательный атрибут. Ожидается название одного из типов данных, поддерживаемых формой.</p></td></tr></tbody></table>

#### Тэг `<Enabled>` <a href="#sql_query_filter_enabled" id="sql_query_filter_enabled"></a>

Признак, определяющий, будет ли использоваться данный фильтр.

Необязательный тэг. Ожидается логическое значение.
