---
description: Команда; экспортирует данные из таблицы в файл формата CSV и скачивает его.
---

# ExportTableToCsvCommand

## Шаблон ExportTableToCsvCommand <a href="#template_export_table_to_csv_command" id="template_export_table_to_csv_command"></a>

```xml
<Command Name="" Type="ExportTableToCsvCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <Condition Name="" />
  <Lock Value="" />
  <!--Тэги, специфичные для ExportTableToCsvCommand-->
  <Table Name="TableName" />
  <ExcludeColumnHeaders Value="" />
  <Columns>
    <Column Name=""></Column>
    <Column Name=""></Column>
  </Columns>
  <FilterRows ColumnName=""></FilterRows>
  <ExportPath Ask=""></ExportPath>
</Command>
```

## Описание ExportTableToCsvCommand <a href="#description_export_table_to_csv_command" id="description_export_table_to_csv_command"></a>

```xml
<Command Name="ExportTableToCsvCommandName" Type="ExportTableToCsvCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <!--Тэги, специфичные для ExportTableToCsvCommand-->
</Command>
```

### Результат выполнения ExportTableToCsvCommand <a href="#result_export_table_to_csv_command" id="result_export_table_to_csv_command"></a>

#### Value <a href="#result_value" id="result_value"></a>

Команда не имеет результата.

## Тэги, специфичные для ExportTableToCsvCommand <a href="#tags_export_table_to_csv_command" id="tags_export_table_to_csv_command"></a>

### Table <a href="#table" id="table"></a>

Таблица, данные которой будут выгружаться в файл.

Обязательный тэг. Значение тэга `<Table>`: не ожидается.

```xml
<Table Name="TableName" />
```

#### Атрибуты тэга `<Table>` <a href="#attributes_tag_table" id="attributes_tag_table"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Название одной из таблиц, описанных в форме.</p><p></p><p>Обязательный атрибут. Ожидается название одной из таблиц, описанных в форме.</p></td></tr></tbody></table>

### ExcludeColumnHeaders <a href="#exclude_column_headers" id="exclude_column_headers"></a>

Признак, определяющий, экспортировать ли заголовки столбцов.

Необязательный тэг. Значение тэга `<ExcludeColumnHeaders>`: не ожидается.

Если тэг `<ExcludeColumnHeaders>` отсутствует, то для атрибута `Value` используется значение False.

```xml
<ExcludeColumnHeaders Value="False" />
```

#### Атрибуты тэга `<ExcludeColumnHeaders>` <a href="#attributes_tag_exclude_column_headers" id="attributes_tag_exclude_column_headers"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Value</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается логическое значение.</p></td></tr></tbody></table>

### Columns <a href="#columns" id="columns"></a>

Экспортируемые столбцы.

Необязательный тэг. Значение тэга `<Columns>`: список тэгов [`<Column>`](exporttabletocsvcommand.md#columns_column).

Если тэг `<Columns>` отсутствует, то экспортируются все видимые столбцы таблицы.

```xml
<Columns>
  <Column Name="ColumnName1">True</Column>
  <Column Name="ColumnName2">False</Column>
  <Column Name="ColumnName3" />
</Columns>
```

#### Тэг `<Column>` <a href="#columns_column" id="columns_column"></a>

Экспортируемый столбец с признаком, задаваемым в значении тэга `<Column>`, следует ли его экспортировать.

Необязательный тэг. Ожидается логическое значение.

Если значение тэга `<Column>` равно NULL, то столбец считается экспортируемым.

#### Атрибуты тэга `<Column>` <a href="#attributes_tag_columns_column" id="attributes_tag_columns_column"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Имя столбца.</p><p></p><p>Обязательный атрибут. Значение атрибута <code>Name</code>: имя одного из столбцов указанной таблицы.</p></td></tr></tbody></table>

### FilterRows <a href="#filter_rows" id="filter_rows"></a>

Фильтрация экспортируемых строк по соответствию значений определенного столбца набору определенных значений.

Необязательный тэг. Ожидается любое скалярное значение или линейный масси&#x432;**.**

Если тэг `<FilterRows>` отсутствует, то экспортируются все видимые строки таблицы.

```xml
<FilterRows ColumnName=""></FilterRows>
```

#### Атрибуты тэга `<FilterRows>` <a href="#attributes_tag_filter_rows" id="attributes_tag_filter_rows"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">ColumnName</td><td><p>Имя столбца, значения которого будут сравниваться с набором значений из тэга <code>&#x3C;FilterRows></code>.</p><p></p><p>Обязательный атрибут. Значение атрибута <code>ColumnName</code>: имя одного из столбцов указанной таблицы.</p></td></tr></tbody></table>

### ExportPath <a href="#export_path" id="export_path"></a>

Имя файла, с которым он будет скачан у пользователя.

Необязательный тэг. Любое значение будет переведено в текстовое.

Если указан полный путь, то из него будет извлечено имя файла, а остальное проигнорировано.

Если тэг `<ExportPath>` отсутствует, то используется автоматически сгенерированное значение, а для атрибута `Ask` используется значение False.

```xml
<ExportPath Ask="False">ExportPath</ExportPath>
```

#### Атрибуты тэга `<ExportPath>` <a href="#attributes_tag_export_path" id="attributes_tag_export_path"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Ask</td><td><p>Признак, определяющий, будет ли задан вопрос о пути сохранения файлов. Диалоговое окно выбора пути показывается только при наличии на странице сертификата и  при наличии разрешения от пользователя на работу с файлами (в браузере). Если диалоговое окно не удалось показать, то загрузка будет выполнена без диалогового окна.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>Если атрибут <code>Ask</code> отсутствует, то используется значение False.</p></td></tr></tbody></table>
