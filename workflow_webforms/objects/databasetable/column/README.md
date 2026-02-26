# Column

## Шаблон столбцов DatabaseTable <a href="#template_databasetable" id="template_databasetable"></a>

Перечень возможных общих тэгов для всех типов столбцов:

```xml
<Column Name="" Type="" Assembly="DatabaseTableColumnControls" ><Column Name="" Type="DatabaseTableColumnTextBox" Assembly="DatabaseTableColumnControls" >
  <!--Тэги, общие для всех типов столбцов-->    
  <Title></Title> 
  <Width></Width>
  <DisplayIndex></DisplayIndex>
  <WrapMode Value="" />
  <Alignment Value="" />
  <HeaderAlignment Value="" />
  <AutoSizeMode Value="" />
  <HeaderBackColor></HeaderBackColor>
  <BackColor></BackColor>
  <ForeColor></ForeColor>
  <Visible></Visible>
  <Hint></Hint>
  <DataType DataType="" />
  <Substitution SourceColumn="">
    <DataConnection SourceDataConnection="">
      <Fields>
        <Field Name="" />
        <Field Name="" />
      </Fields>
    </DataConnection>
  </Substitution>
  <Filter AutoFill="" FilterNullValue=""></Filter>
  <DefaultNewRowValue></DefaultNewRowValue>
  <AutoFill Type="" />
  <Calculate>
    <Expression></Expression>
    <Items>
      <Item></Item>
      <Item></Item>
    </Items>
  </Calculate>
  <!--Тэги, специфичные для определенного типа столбца-->
</Column>
```

### Атрибуты столбцов DatabaseTable <a href="#attributes_columns" id="attributes_columns"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Название столбца (обязательно должно совпадать с именем поля, указанным в соединении с данными из тэга <a href="./#source_data_connection"><code>&#x3C;SourceDataConnection></code></a>).</p><p></p><p>Обязательный атрибут.</p></td></tr><tr><td align="center">Type</td><td><p>Название типа столбца в сборке.</p><p></p><p>Обязательный атрибут.</p></td></tr><tr><td align="center">Assembly</td><td><p>Название сборки (библиотека).</p><p></p><p>Обязательный атрибут.</p></td></tr></tbody></table>

## Тэги, общие для всех столбцов таблицы <a href="#common_columns_tags" id="common_columns_tags"></a>

### Title <a href="#column_title" id="column_title"></a>

Заголовок столбца.

Необязательный тэг. Любое значение будет переведено в текстовое.

Если тэг `<Title>` отсутствует, то используется название столбца.

```xml
<Title>Заголовок</Title>
```

### Width <a href="#column_width" id="column_width"></a>

Ширина столбца.

Необязательный тэг. Ожидается целочисленное значение.

Если тэг `<Width>` отсутствует, то используется стандартное значение .NET.

```xml
<Width>100</Width>
```

### DisplayIndex <a href="#column_display_index" id="column_display_index"></a>

Порядок отображения столбца.

Необязательный тэг. Ожидается неотрицательное целочисленное значение.

Если тэг `<DisplayIndex>` отсутствует, то используется значение от 0 до N-1, где N - количество столбцов таблицы (видимых и невидимых), в зависимости от порядка описания столбцов в таблице.

```xml
<DisplayIndex>0</DisplayIndex>
```

### WrapMode <a href="#column_wrap_mode" id="column_wrap_mode"></a>

Признак, определяющий, будут ли в содержании ячеек столбца переносы на новую строку, если все содержание ячейки не входит в ее видимую область.

Необязательный тэг. Значение тэга `<WrapMode>`: не ожидается.

Если тэг `<WrapMode>` отсутствует, то для атрибута `Value` используется значение False.

```xml
<WrapMode Value="False" />
```

{% hint style="warning" %}
Если значение атрибута `Value` тэга `<WrapMode>` установлено в `True`, то высота строк может увеличиться в зависимости от содержимого ячейки.
{% endhint %}

#### Атрибуты тэга `<WrapMode>` <a href="#attributes_tag_column_wrap_mode" id="attributes_tag_column_wrap_mode"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Value</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается логическое значение.</p></td></tr></tbody></table>

### Alignment <a href="#column_alignment" id="column_alignment"></a>

Название типа положения содержимого ячейки столбца.

Необязательный тэг. Значение тэга `<Alignment>`: не ожидается.

Если тэг `<Alignment>` отсутствует, то для атрибута `Value` используется значение NotSet.

Не распространяется на столбец типа `DatabaseTableCheckBoxColumn`.

```xml
<Alignment Value="NotSet" />
```

#### Атрибуты тэга `<Alignment>` <a href="#attributes_tag_column_alignment" id="attributes_tag_column_alignment"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Value</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается название одного из <a href="./#column_headers_alignment_types">типов положения содержимого ячейки столбца таблицы</a>.</p></td></tr></tbody></table>

### HeaderAlignment <a href="#column_header_alignment" id="column_header_alignment"></a>

Название типа положения содержимого заголовка столбца.

Необязательный тэг. Значение тэга `<HeaderAlignment>`: не ожидается.

Если тэг `<HeaderAlignment>` отсутствует, то для атрибута `Value` используется значение NotSet.

```xml
<HeaderAlignment Value="NotSet" />
```

#### Атрибуты тэга `<HeaderAlignment>` <a href="#attributes_tag_column_header_alignment" id="attributes_tag_column_header_alignment"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Value</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается название одного из <a href="./#column_header_alignment_types">типов положения содержимого ячейки столбца</a>.</p></td></tr></tbody></table>

#### Типы положения содержимого ячейки столбца <a href="#column_header_alignment_types" id="column_header_alignment_types"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">NotSet</td><td>Значение наследуется от свойства <a href="./#column_headers_alignment"><code>&#x3C;ColumnHeadersAlignment></code></a> таблицы</td></tr><tr><td align="center">TopLeft</td><td>Содержимое выравнивается по верхнему краю в вертикальном направлении и по левому краю ячейки в горизонтальном направлении</td></tr><tr><td align="center">TopCenter</td><td>Содержимое выравнивается по верхнему краю в вертикальном направлении и по центру ячейки</td></tr><tr><td align="center">TopRight</td><td>Содержимое выравнивается по верхнему краю в вертикальном направлении и по правому краю ячейки в горизонтальном направлении</td></tr><tr><td align="center">MiddleLeft</td><td>Содержимое выравнивается вертикально по середине и горизонтально по левому краю ячейки в горизонтальном направлении</td></tr><tr><td align="center">MiddleCenter</td><td>Содержимое выравнивается по вертикальному и горизонтальному центру ячейки</td></tr><tr><td align="center">MiddleRight</td><td>Содержимое выравнивается вертикально по середине и горизонтально по правому краю ячейки в горизонтальном направлении</td></tr><tr><td align="center">BottomLeft</td><td>Содержимое выравнивается по нижнему краю в вертикальном направлении и по левому краю ячейки в горизонтальном направлении</td></tr><tr><td align="center">BottomCenter</td><td>Содержимое выравнивается по нижнему краю в вертикальном направлении и по центру ячейки</td></tr><tr><td align="center">BottomRight</td><td>Содержимое выравнивается по нижнему краю в вертикальном направлении и по правому краю ячейки в горизонтальном направлении</td></tr></tbody></table>

### AutoSizeMode <a href="#column_auto_size_mode" id="column_auto_size_mode"></a>

Название типа автоматического изменения ширины столбца.

Необязательный тэг. Значение тэга `<AutoSizeMode>`: не ожидается.

Если тэг `<AutoSizeMode>` отсутствует, то для атрибута `Value` используется значение None.

```xml
<AutoSizeMode Value="NotSet" />
```

#### Атрибуты тэга `<AutoSizeMode>` <a href="#attributes_tag_column_auto_size_mode" id="attributes_tag_column_auto_size_mode"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Value</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается название одного из <a href="./#column_auto_size_mode_types">типов автоматического изменения ширины столбцов таблицы</a>.</p></td></tr></tbody></table>

#### Типы автоматического изменения ширины столбцов таблицы <a href="#column_auto_size_mode_types" id="column_auto_size_mode_types"></a>

<table data-header-hidden><thead><tr><th width="286.7376913646473" align="center"></th><th width="488.3333333333333"></th></tr></thead><tbody><tr><td align="center">None</td><td>Нет автоматического изменения ширины столбца</td></tr><tr><td align="center">Fill</td><td>Ширина столбца изменяется так, чтобы точно заполнить ширину всей отображаемой области таблицы, с учетом наличия или отсутствия полосы горизонтальной прокрутки</td></tr></tbody></table>

### HeaderBackColor <a href="#column_header_back_color" id="column_header_back_color"></a>

Цвет фона заголовка столбца.

Необязательный тэг. Ожидается имя одного из цветов, описанных в форме или описание цвета в формате HTML (#rrggbb).

Если тэг `<HeaderBackColor>` отсутствует, то используется стандартное значение .NET.

```xml
<HeaderBackColor>HeaderBackColor</HeaderBackColor>
```

### BackColor <a href="#column_back_color" id="column_back_color"></a>

Цвет фона ячеек столбца.

Необязательный тэг. Ожидается имя одного из цветов, описанных в форме или описание цвета в формате HTML (#rrggbb).

Если тэг `<BackColor>` отсутствует, то используется стандартное значение .NET.

```xml
<BackColor>BackColor</BackColor>
```

### ForeColor <a href="#column_fore_color" id="column_fore_color"></a>

Цвет шрифта ячеек столбца.

Необязательный тэг. Ожидается имя одного из цветов, описанных в форме или описание цвета в формате HTML (#rrggbb).

Если тэг `<ForeColor>` отсутствует, то используется стандартное значение .NET.

```xml
<ForeColor>ForeColor</ForeColor>
```

### Visible <a href="#column_visible" id="column_visible"></a>

Признак видимости столбца.

Необязательный тэг. Ожидается логическое значение.

Если тэг `<Visible>` отсутствует, то используется значение True.

```xml
<Visible>True</Visible>
```

### Hint <a href="#column_hint" id="column_hint"></a>

Подсказка, всплывающая на заголовке столбца.

Необязательный тэг. Любое значение будет переведено в текстовое.

```xml
<Hint>Подсказка</Hint>
```

### ToolTipColumnName <a href="#tool_tip_column_name" id="tool_tip_column_name"></a>

Имя столбца, значение которого будет использовано для всплывающей подсказки при наведении курсора мыши на ячейку таблицы.\
Для каждой ячейки настраиваемого столбца в подсказке будет значение из ячейки той же строки столбца, имя которого задано в тэге `<ToolTipColumnName>`.

Необязательный тэг. Любое значение будет переведено в текстовое.

Если тэг `<ToolTipColumnName>` отсутствует, то используется значение из текущего столбца.

```xml
<ToolTipColumnName>ColumnName</ToolTipColumnName>
```

### DataType <a href="#column_data_type" id="column_data_type"></a>

Настройки форматированного вывода значений в ячейках столбца.

Необязательный тэг. Значение тэга `<DataType>`: не ожидается.

```xml
<DataType Type="DataType" />
```

#### Атрибуты тэга `<DataType>` <a href="#attributes_tag_column_data_type" id="attributes_tag_column_data_type"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Type</td><td><p>Тип данных, к которому приводятся значения.</p><p></p><p>Обязательный атрибут. Значение атрибута <code>Type</code>: название одного из <a href="/broken/pages/-MaRtBVKMO4VR0KCghVx">типов данных</a>.</p></td></tr></tbody></table>

Замечание. Остальные атрибуты зависят от указанного типа данных.

### Filter <a href="#column_filter" id="column_filter"></a>

Правила фильтрации (отображения) строк в таблице.

Необязательный тэг. Значение тэга `<Filter>`: любое значение.

```xml
<Filter AutoFill="True" FilterNullValue="False">
  <Object Name="ObjectComboBox" />
</Filter>
```

#### Атрибуты тэга `<Filter>` <a href="#attributes_tag_column_filter" id="attributes_tag_column_filter"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">AutoFill</td><td><p>Признак, определяющий, будет ли передан список уникальных значений ячеек данного столбца в проперти <code>&#x3C;ValueList></code> объекта, указанного в тэге <code>&#x3C;Filter></code>.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение. </p><p></p><p>Если атрибут <code>AutoFill</code> не задан, то используется значение True.</p><p></p><p>Замечание. Список уникальных значений будет отправлен только в том случае, если в качестве значения тэга <code>&#x3C;Filter></code> объект формы, который имеет проперти для <code>&#x3C;ValueList></code>. То есть во всех остальных случаях атрибут <code>AutoFill</code> ни на что не влияет.</p></td></tr><tr><td align="center">FilterNullValue</td><td><p>Признак, определяющий, будет ли осуществляться фильтрация столбца, если значение фильтра будет равно NULL.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение. </p><p></p><p>Если атрибут <code>FilterNullValue</code> не задан, то используется значение False.</p></td></tr></tbody></table>

### Substitution <a href="#column_substitution" id="column_substitution"></a>

Подстановка в ячейки столбца значений, зависящих от значений в других столбцах.

Необязательный тэг. Ожидается таблица с двумя столбцами (например, ссылка на [GetDataConnection](../../../dataconnections/) с указанием двух его полей).

Для каждой ячейки данного столбца подстановка происходит следующим образом:

1. В этой же строке таблицы в столбце SourceColumnName находится определенное значение.
2. Данный столбец ищет строку в матрице, указанной в тэге `<Substitution>`, первая колонка которой имеет именно это значение.
3. Значение второй колонки найденной строки substitution-матрицы подставляется в качестве значения в ячейку данного столбца.

```xml
<Substitution SourceColumn="SourceColumnName">
  <DataConnection SourceDataConnection="SourceDataConnectionName">
    <Fields>
      <Field Name="Field1Name" />
      <Field Name="Field2Name" />
    </Fields>
  </DataConnection>
</Substitution>
```

#### Атрибуты тэга `<Substitution>` <a href="#attributes_tag_column_substitution" id="attributes_tag_column_substitution"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">SourceColumn</td><td><p>Столбец, от значений ячеек которого зависят значения ячеек данного столбца.</p><p></p><p>Обязательный атрибут. Ожидается имя одного из столбцов, описанных в этой же таблице.</p></td></tr></tbody></table>

### DefaultNewRowValue <a href="#column_default_new_row_value" id="column_default_new_row_value"></a>

Значение по умолчанию для ячейки столбца при добавлении новой строке в таблицу.

Необязательный тэг. Значение тэга `<DefaultNewRowValue>`: любое значение.

```xml
<DefaultNewRowValue>Value</DefaultNewRowValue>
```

### AutoFill <a href="#column_auto_fill" id="column_auto_fill"></a>

Автоматическое заполнение значений в ячейках столбца.

Необязательный тэг. Значение тэга `<AutoFill>`: не ожидается.

```xml
<AutoFill Type="RowNumber" />
```

#### Атрибуты тэга `<AutoFill>` <a href="#attributes_tag_column_auto_fill" id="attributes_tag_column_auto_fill"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Type</td><td><p>Тип автоматического заполнения.</p><p></p><p>Обязательный атрибут. Ожидается название <a href="./#column_auto_fill_types">одного из типов автоматического заполнения столбца таблицы</a>.</p></td></tr></tbody></table>

#### Типы автоматического заполнения столбца таблицы <a href="#column_auto_fill_types" id="column_auto_fill_types"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">RowNumber</td><td>Номер по порядку</td></tr></tbody></table>

### Calculate <a href="#column_calculate" id="column_calculate"></a>

Настройки вычисляемого столбца.

Необязательный тэг. Значение тэга `<Calculate>`: два тэга - [`<Expression>`](./#column_calculate_expression) и [`<Items>`](./#column_calculate_items).

```xml
<Calculate>
  <Expression>(Field1 * Field2 + {1}) * {2}</Expression>
  <Items>
    <Item>100</Item>
    <Item>
      <Object Name="ObjectTextBox" />
    </Item>
  </Items>
</Calculate>
```

### Тэг `<Expression>` <a href="#column_calculate_expression" id="column_calculate_expression"></a>

Выражение для вычисляемого столбца.

Обязательный тэг. Значение тэга `<Expression>`: любое значение.

Выражение для вычисляемого столбца поддерживает выражения вида "ColumnName", где ColumnName - название одного из столбцов данной таблицы, и выражения вида "{N}" для подстановки значений (N+1)-ого элемента, то есть {0}, {1} и т. д.

Все поддерживаемые в выражении для вычисляемого столбца конструкции смотрите по ссылке "[http://msdn.microsoft.com/en-us/library/system.data.datacolumn.expression.aspx](http://msdn.microsoft.com/en-us/library/system.data.datacolumn.expression.aspx)".

### Тэг `<Items>` <a href="#column_calculate_items" id="column_calculate_items"></a>

Переменные для подстановки в выражение для вычисляемого столбца.

Необязательный тэг. Значение тэга `<Items>`: список тэгов [`<Item>`](./#column_calculate_items_item).

#### Тэг `<Item>` <a href="#column_calculate_items_item" id="column_calculate_items_item"></a>

Переменная для подстановки в выражение для вычисляемого столбца.

Необязательный тэг. Значение тэга `<Item>`: любое значение.

