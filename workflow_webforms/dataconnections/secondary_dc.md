---
description: >-
  Вторично загружающее соединение с данными; получает данные из другого
  загружающего соединения с данными и фильтрует их.
---

# SecondaryGetDataConnection

## Шаблон SecondaryGetDataConnection <a href="#template_secondary_dc" id="template_secondary_dc"></a>

```xml
<DataConnection Name="" Type="SecondaryGetDataConnection" Assembly="DataConnections">
  <SourceDataConnection Name="" SqlQuery="" />
  <ManualRefresh></ManualRefresh> 
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
  <StartPosition></StartPosition>
  <MaxCount></MaxCount>
</DataConnection>
```

## Описание SecondaryGetDataConnection <a href="#description_secondary_dc" id="description_secondary_dc"></a>

```xml
<DataConnection Name="SecondaryGetDataConnectionName" Type="SecondaryGetDataConnection" Assembly="DataConnections">
  <!--Тэги, специфичные для SecondaryGetDataConnection-->
</DataConnection>
```

## Тэги, специфичные для SecondaryGetDataConnection <a href="#tags_secondary_dc" id="tags_secondary_dc"></a>

### SourceDataConnection <a href="#source_data_connection" id="source_data_connection"></a>

Первично загружающее [соединение с данными](primary_dc/), данные которого будут фильтроваться.

Обязательный тэг. Значение тэга `<SourceDataConnection>`: не ожидается.

```xml
<SourceDataConnection Name="SourceDataConnectionName" SqlQuery="SqlQueryName" />
```

#### Атрибуты тэга `<SourceDataConnection>` <a href="#attributes_tag_source_data_connection" id="attributes_tag_source_data_connection"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="465.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Имя первично загружающего соединения с данными.</p><p></p><p>Обязательный атрибут. Ожидается имя одного из первично загружающих соединений с данными, описанных в форме.</p></td></tr><tr><td align="center">SqlQuery</td><td><p>Имя запроса из загружающего соединения.</p><p></p><p>Необязательный атрибут. Ожидается имя одного из запросов из загружающего соединения с данными.</p></td></tr></tbody></table>

### ManualRefresh <a href="#manual_refresh" id="manual_refresh"></a>

Признак, определяющий, будет ли загрузка данных автоматически производиться при изменении первичного загружающего соединения-источника.

Необязательный тэг. Ожидается логическое значение.

Если тэг `<ManualRefresh>` отсутствует, то используется значение True.

```xml
<ManualRefresh>True</ManualRefresh>
```

### Filter <a href="#filter" id="filter"></a>

Фильтр полученных данных.

Фильтрация происходит без повторных запросов в базу данных.

Необязательный тэг. Значение тэга `<Filter>`: список тэгов [`<And>`](secondary_dc.md#filter_and), [`<Or>`](secondary_dc.md#filter_or) и [`<Not>`](secondary_dc.md#filter_not) или тэги [`<Field>`](secondary_dc.md#filter_field), [`<Value>`](secondary_dc.md#filter_value) и [`<DataType>`](secondary_dc.md#filter_data_type).

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

<table data-header-hidden><thead><tr><th align="center"></th><th width="459.3333333333333"></th></tr></thead><tbody><tr><td align="center">Type</td><td><p>Тип сравнения значений.</p><p></p><p>Необязательный атрибут. Ожидается название одного из <a href="secondary_dc.md#filter_types">типов сравнения</a> значений.</p><p></p><p>Если атрибут <code>Type</code> отсутствует, то используется значение Equal.</p></td></tr><tr><td align="center">FilterByNullValue</td><td><p>Признак, определяющий, будет ли осуществляться фильтрация для очередной строки соединения с данными, если значение фильтра будет равно NULL.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>Если атрибут <code>FilterByNullValue</code> отсутствует, то используется значение True.</p></td></tr><tr><td align="center">RefreshFilter</td><td><p>Признак, определяющий, будут ли данные сразу же отфильтрованы при изменении параметра фильтра.</p><p>Признак не работает для фильтров, содержащих внутри себя тэги <a href="secondary_dc.md#filter_and"><code>&#x3C;And></code></a>, <a href="secondary_dc.md#filter_or"><code>&#x3C;Or></code></a> или <a href="secondary_dc.md#filter_not"><code>&#x3C;Not></code></a>, для таких фильтров данные обновляются всегда.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>Если атрибут <code>RefreshFilter</code> отсутствует, то используется значение True.</p></td></tr><tr><td align="center">Reverse</td><td><p>Признак, определяющий, будет ли изменён порядок аргументов фильтра на обратный.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>Если атрибут <code>Reverse</code> отсутствует, то используется значение False.</p></td></tr></tbody></table>

#### Типы сравнения значений <a href="#filter_types" id="filter_types"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="459.3333333333333"></th></tr></thead><tbody><tr><td align="center">Equal</td><td>Сравнение значений на равенство</td></tr><tr><td align="center">NotEqual</td><td>Сравнение значений на неравенство</td></tr><tr><td align="center">Greater</td><td>Сравнение значений на "больше": значение из соединения с данными больше указанного значения</td></tr><tr><td align="center">NotGreater</td><td>Сравнение значений на "не больше": значение из соединения с данными не больше указанного значения</td></tr><tr><td align="center">Less</td><td>Сравнение значений на "меньше": значение из соединения с данными меньше указанного значения</td></tr><tr><td align="center">NotLess</td><td>Сравнение значений на "не меньше": значение из соединения с данными не меньше указанного значения</td></tr><tr><td align="center">Contains</td><td>Сравнение значений на "содержит": значение из соединения с данными содержит указанное значение (значения любых типов данных преобразуются к строковому типу)</td></tr><tr><td align="center">NotContains</td><td>Сравнение значений на "не содержит": значение из соединения с данными не содержит указанное значение (значения любых типов данных преобразуются к строковому типу)</td></tr><tr><td align="center">In</td><td>Сравнение значений на "входит": значение из соединения с данными входит в указанный массив</td></tr><tr><td align="center">NotIn</td><td>Сравнение значений на "не входит": значение из соединения с данными не входит в указанный массив</td></tr><tr><td align="center">Overlap</td><td>Сравнение значений на "пересекается": массив из соединения с данными имеет общие элементы с указанным массивом</td></tr><tr><td align="center">NotOverlap</td><td>Сравнение значений на "не пересекается": массив из соединения с данными не имеет общих элементов с указанным массивом</td></tr><tr><td align="center">MatchSearch</td><td>Сравнение значений на "удовлетворяет поисковой строке": поисковая строка может состоять из слов, разделенных пробелами и знаками "+", "*" и "?"<em>,</em> пробел означает "ИЛИ", "+" означает "И", "*" означает любое количество любых символов, "?" означат ровно один символ</td></tr><tr><td align="center">NotMatchSearch</td><td>Сравнение значений на "не удовлетворяет поисковой строке": поисковая строка может состоять из слов, разделенных пробелами и знаками "+", "*" и "?"<em>,</em> пробел означает "ИЛИ", "+" означает "И", "*" означает любое количество любых символов, "?" означат ровно один символ</td></tr><tr><td align="center">ContainedIn</td><td>Сравнение значений на "входит": значение из соединения с данными входит в указанное значение (значения любых типов данных преобразуются к строковому типу)</td></tr><tr><td align="center">NotContainedIn</td><td>Сравнение значений на "не входит": значение из соединения с данными не входит в указанное значение (значения любых типов данных преобразуются к строковому типу)</td></tr></tbody></table>

#### Тэг `<And>` <a href="#filter_and" id="filter_and"></a>

Логическое умножение нескольких фильтров.

Необязательный тэг. Значение тэга `<And>`: список тэгов [`<Filter>`](secondary_dc.md#filter), `<And>`, [`<Or>`](secondary_dc.md#filter_or) и [`<Not>`](secondary_dc.md#filter_not).

#### Атрибуты тэга `<And>` <a href="#attributes_tag_filter_and" id="attributes_tag_filter_and"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="459.3333333333333"></th></tr></thead><tbody><tr><td align="center">RefreshFilter</td><td><p>Признак, определяющий, будут ли данные сразу же отфильтрованы при изменении вложенного фильтра.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>Если атрибут <code>RefreshFilter</code> отсутствует, то используется значение True.</p></td></tr></tbody></table>

#### Тэг `<Or>` <a href="#filter_or" id="filter_or"></a>

Логическое сложение нескольких фильтров.

Необязательный тэг. Значение тэга `<Or>`: список тэгов [`<Filter>`](secondary_dc.md#filter), [`<And>`](secondary_dc.md#filter_and), `<Or>` и [`<Not>`](secondary_dc.md#filter_not).

#### Атрибуты тэга `<Or>` <a href="#attributes_tag_filter_or" id="attributes_tag_filter_or"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="459.3333333333333"></th></tr></thead><tbody><tr><td align="center">RefreshFilter</td><td><p>Признак, определяющий, будут ли данные сразу же отфильтрованы при изменении вложенного фильтра.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>Если атрибут <code>RefreshFilter</code> отсутствует, то используется значение True.</p></td></tr></tbody></table>

#### Тэг `<Not>` <a href="#filter_not" id="filter_not"></a>

Логическое отрицание одного фильтра.

Необязательный тэг. Значение тэга `<Not>`: тэг [`<Filter>`](secondary_dc.md#filter), [`<And>`](secondary_dc.md#filter_and), [`<Or>`](secondary_dc.md#filter_or) и `<Not>`.

#### Атрибуты тэга `<Not>` <a href="#attributes_tag_filter_not" id="attributes_tag_filter_not"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="459.3333333333333"></th></tr></thead><tbody><tr><td align="center">RefreshFilter</td><td><p>Признак, определяющий, будут ли данные сразу же отфильтрованы при изменении вложенного фильтра.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>Если атрибут <code>RefreshFilter</code> отсутствует, то используется значение True.</p></td></tr></tbody></table>

#### Тэг `<Field>` <a href="#filter_field" id="filter_field"></a>

Поле, по значению которого полученные данные фильтруются.

Обязательный тэг. Значение тэга `<Field>`: не ожидается.

#### Атрибуты тэга `<Field>` <a href="#attributes_tag_filter_field" id="attributes_tag_filter_field"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="459.3333333333333"></th></tr></thead><tbody><tr><td align="center">NativeName</td><td><p>Название поля, по значению которого полученные данные фильтруются.</p><p></p><p>Обязательный атрибут. Ожидается название одного из полей, описанных в тэге <code>&#x3C;Fields></code>.</p></td></tr></tbody></table>

#### Тэг `<Value>` <a href="#filter_value" id="filter_value"></a>

Значение, по которому полученные данные фильтруются.

Обязательный тэг. Ожидается любое значение.

#### Тэг `<DataType>` <a href="#filter_data_type" id="filter_data_type"></a>

[Тип данных](/broken/pages/-MaRtBVKMO4VR0KCghVx), к которому приводятся сравниваемые значения.

Необязательный тэг. Значение тэга `<DataType>`: не ожидается.

Если тэг `<DataType>` отсутствует, то для атрибута `Type` используется значение StringDataType.

#### Атрибуты тэга `<DataType>` <a href="#attributes_tag_filter_data_type" id="attributes_tag_filter_data_type"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="459.3333333333333"></th></tr></thead><tbody><tr><td align="center">Type</td><td><p>Название типа данных.</p><p></p><p>Обязательный атрибут. Ожидается название одного из типов данных, поддерживаемых формой.</p></td></tr></tbody></table>

#### Тэг `<Enabled>` <a href="#filter_enabled" id="filter_enabled"></a>

Признак, определяющий, будет ли использоваться данный фильтр.

Необязательный тэг. Ожидается логическое значение.

### StartPosition <a href="#start_position" id="start_position"></a>

Номер строки (первая строка имеет номер 1), начиная с которой данные будут входить в результирующую таблицу текущего вторичного соединения с данными.

Пустое значение или значение меньше 1 соответствуют тому, что строки будут выведены начиная с 1-ой.

Необязательный тэг. Ожидается положительное целочисленное значение.

Если тэг `<StartPosition>` отсутствует, то используется значение 1.

```xml
<StartPosition>1</StartPosition>
```

### MaxCount <a href="#max_count" id="max_count"></a>

Максимальное количество строк, которые будут входить в результирующую таблицу текущего вторичного соединения с данными.

Пустое значение или значение меньше 0 соответствуют тому, что ограничения по количеству строк нет.

Необязательный тэг. Ожидается положительное целочисленное значение.

Если тэг `<MaxCount>` отсутствует, то используется значение 0.

```xml
<MaxCount>100</MaxCount>
```

## Get-проперти для получения свойств <a href="#get_property_primary_dc" id="get_property_primary_dc"></a>

### Count <a href="#get_count" id="get_count"></a>

Возвращает количество строк в указанном запроса загружающего соединения с данными.

Ожидается имя одного из запросов, описанных в загружающем соединении с данными. Если имя запроса не указано, то используется первый запрос (в порядке описания запросов).

```xml
<DataConnection SourceDataConnection="SecondaryGetDataConnectionName">
  <Property Name="Count">SqlQueryName</Property>
</DataConnection>
```

### ValueChanged <a href="#get_value_changed" id="get_value_changed"></a>

Возвращает признак изменения данных DataConnection.

```xml
<DataConnection SourceDataConnection="SecondaryGetDataConnectionName">
  <Property Name="ValueChanged" />
</DataConnection>
```

### RowIndexOf <a href="#get_row_index_of" id="get_row_index_of"></a>

Возвращает индекс строки, удовлетворяющей условиям соответствия названий столбцов и значений в этих столбцах.

```xml
<DataConnection SourceDataConnection="SecondaryGetDataConnectionName">
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
<DataConnection SourceDataConnection="SecondaryGetDataConnectionName">
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
<DataConnection SourceDataConnection="SecondaryGetDataConnectionName">
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
<DataConnection Name="SecondaryGetDataConnectionName">
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
<DataConnection Name="SecondaryGetDataConnectionName">
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
<DataConnection Name="SecondaryGetDataConnectionName">
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
<DataConnection Name="SecondaryGetDataConnectionName">
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
<DataConnection Name="SecondaryGetDataConnectionName">
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
<DataConnection Name="SecondaryGetDataConnectionName">
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
<DataConnection Name="SecondaryGetDataConnectionName">
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
<DataConnection Name="SecondaryGetDataConnectionName">
  <Property Name="FireChanged" />
</DataConnection>
```

### ValueChanged <a href="#set_value_changed" id="set_value_changed"></a>

Задает признак изменения значения соединения с данными.

Ожидается логическое значение.

```xml
<DataConnection Name="SecondaryGetDataConnectionName">
  <Property Name="ValueChanged">False</Property>
</DataConnection>
```
