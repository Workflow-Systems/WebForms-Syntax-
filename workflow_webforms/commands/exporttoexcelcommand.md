---
description: >-
  Команда; генерирует Excel-файл из шаблона, в котором вместо переменных
  подставляются определенные значения и скачивает его.
---

# ExportToExcelCommand

## Поддерживаемые переменные <a href="#supported_variables" id="supported_variables"></a>

В значениях параметров могут быть использованы тэги для изменения форматирования параметра.

#### Тэги форматирования <a href="#variables_formatting_tags" id="variables_formatting_tags"></a>

<table data-header-hidden><thead><tr><th width="254.84751575458438" align="center"></th><th width="469.3333333333333"></th></tr></thead><tbody><tr><td align="center">[b][/b]</td><td>Задает полужирное начертание отрывка текста.</td></tr><tr><td align="center">[i][/i]</td><td>Выделяет отрывок текста курсивом.</td></tr><tr><td align="center">[u][/u]</td><td>Выделяет отрывок текста подчёркиванием.</td></tr><tr><td align="center">[br]</td><td>Перенос текста на новую строку.</td></tr><tr><td align="center">[size={value}][/size]</td><td><p>Задает отрывку текста размер шрифта.</p><p></p><p>В качестве {value} ожидается целочисленное значение.</p></td></tr></tbody></table>

Тэги форматирования заданные в тексте ячейки так же заменяются на соответвующие форматирование.

### <#variable#> <a href="#variable_scalar" id="variable_scalar"></a>

Служит для отображения скалярного значения.

### <%variable%> <a href="#variable_array" id="variable_array"></a>

Служит для отображения массива (для использования в таблице).

### <\*function\*> <a href="#variable_function" id="variable_function"></a>

Служит для подстановки агрегирующей функции (для использования в конце таблицы).

Строчка с агрегирующей функцией должна добавляться под колонкой таблицы с переменной-массивом, значения которой нужно посчитать.

#### Поддерживаемые агрегирующие функции <a href="#variable_function_types" id="variable_function_types"></a>

<table data-header-hidden><thead><tr><th width="239.22974713362873" align="center"></th><th width="469.3333333333333"></th></tr></thead><tbody><tr><td align="center">sum</td><td>Сумма значений столбца</td></tr><tr><td align="center">avg</td><td>Среднее значение столбца</td></tr><tr><td align="center">min</td><td>Минимальное значение столбца</td></tr><tr><td align="center">max</td><td>Максимальное значение столбца</td></tr><tr><td align="center">count</td><td>Количество значений столбца (число строк в таблице)</td></tr></tbody></table>

### <@PATH@> <a href="#variable_image" id="variable_image"></a>

Служит для вставки изображения.

Например, для вставки изображения с параметризованным путем следует указать выражения вида <@<#variable#>@> - для скалярных значений и <@<%variable%>@> - для массивов.

Выражение PATH имеет следующий формат: PATH\[?width=INT]\[?height=INT]\[?mode=MODE]\[?rotation=INT], где:

* PATH - полный путь до файла изображения;
* width - необязательный параметр ширины изображения; в качестве значения INT ожидается положительное целочисленное значение;
* height - необязательный параметр высоты изображения; в качестве значения INT ожидается положительное целочисленное значение;
* mode - необязательный параметр типа размера; в качестве значения MODE ожидается [тип размера изображения](exporttoexcelcommand.md#image_mode_types) (по умолчанию "Zoom");
* rotation - необязательный параметр поворота изображения; в качестве значения INT ожидается целочисленное значение в диапазоне от -360 до 360 градусов.

Если явно не указаны width и height, то изображение будет вписываться в размеры ячейки (высота строки и ширина колонки).

{% hint style="warning" %}
Если высота строки имеет значение по умолчанию, то оно воспринимается, как null. В таком случае размер картинки будет зависить только от ширины колонки, и итоговое изображение будет перекрывать другие строки.
{% endhint %}

#### Типы размера изображения <a href="#image_mode_types" id="image_mode_types"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="469.3333333333333"></th></tr></thead><tbody><tr><td align="center">Zoom</td><td>Растягивание изображения до указанной ширины и высоты (в большую или меньшую сторону), сохраняя пропорции изображения</td></tr><tr><td align="center">ZoomLess</td><td>Растягивание изображения до указанной ширины и высоты (только в меньшую сторону), сохраняя пропорции изображения</td></tr><tr><td align="center">Stretch</td><td>Растягивание изображения до указанной ширины и высоты без сохранения пропорций изображения</td></tr></tbody></table>

### Динамические колоноки <a href="#variable_dynamic" id="variable_dynamic"></a>

Для заголовков в динамических колонках используется <\[#variable#]>.

Для значений в динамических колонках используется <\[%variable%]>.

Для динамических колонок в качестве параметра ожидается матрица из 3-х столбцов:

1. Идентификатор строки - является вспомогательным полем, необходимым для корректного определения кол-ва динамических колонок;
2. Название столбца;
3. Значение столбца.

К примеру, в команде определён следующий параметр:

```xml
<Parameter Name="Work">
  <DataConnection SourceDataConnection="WorkPrimaryGetDataConnection">
    <Fields>
      <Field Name="RowNumber" />
      <Field Name="ColumnTitle" />
      <Field Name="CellValue" />
    </Fields>
  </DataConnection>
</Parameter>
```

`DataConnection` возвращает следующие данные:

| RowNumber | ColumnTitle | CellValue |
| :-------: | :---------: | :-------: |
|     1     |  'Column1'  |     11    |
|     1     |  'Column2'  |     12    |
|     1     |  'Column3'  |     13    |
|     1     |  'Column4'  |     14    |
|     2     |  'Column1'  |     21    |
|     2     |  'Column2'  |     22    |
|     2     |  'Column3'  |     23    |
|     2     |  'Column4'  |     24    |
|     3     |  'Column1'  |     31    |
|     3     |  'Column2'  |     32    |
|     3     |  'Column3'  |     33    |
|     3     |  'Column4'  |     34    |

В итоге будет сформирована следующая таблица:

<table><thead><tr><th width="180.51958438933713" align="center">'Column1'</th><th width="175.18373891943955" align="center">'Column2'</th><th width="188.41579748992586" align="center">'Column3'</th><th align="center">'Column4'</th></tr></thead><tbody><tr><td align="center">11</td><td align="center">12</td><td align="center">13</td><td align="center">14</td></tr><tr><td align="center">21</td><td align="center">22</td><td align="center">23</td><td align="center">24</td></tr><tr><td align="center">31</td><td align="center">32</td><td align="center">33</td><td align="center">34</td></tr></tbody></table>

{% hint style="info" %}
При задании имен параметров команды необходимо соблюдать их уникальность, т.к. при формировании динамических колонок тэги <\[#variable#]> и <\[%variable%]> будут заменены на временные тэги по количеству колонок:

<\[#variable#]> - <#variableTitle0#>, <#variableTitle1#>, <#variableTitle2#>...<#variableTitleN#>;

<\[%variable%]> - <%variableValue0%>, <%variableValue1%>, <%variableValue2%>...<%variableValueN%>.
{% endhint %}

## Шаблон ExportToExcelCommand <a href="#template_export_to_excel_command" id="template_export_to_excel_command"></a>

```xml
<Command Name="" Type="ExportToExcelCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <Condition Name="" />
  <Lock Value="" />
  <!--Тэги, специфичные для ExportToExcelCommand-->
  <TemplateFileName></TemplateFileName>
  <Parameters>
    <Parameter Name=""></Parameter>
  </Parameters>
  <GroupTags></GroupTags>
  <ExportFileName Ask=""></ExportFileName>
  <InsertPictures Value="" />
  <UseRawTags Value="" />
</Command>
```

## Описание ExportToExcelCommand <a href="#description_export_to_excel_command" id="description_export_to_excel_command"></a>

```xml
<Command Name="ExportToExcelCommandName" Type="ExportToExcelCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <!--Тэги, специфичные для ExportToExcelCommand-->
</Command>
```

### Результат выполнения ExportToExcelCommand <a href="#result_export_to_excel_command" id="result_export_to_excel_command"></a>

#### Value <a href="#result_value" id="result_value"></a>

Команда не имеет результата.

## Тэги, специфичные для ExportToExcelCommand <a href="#tags_export_to_excel_command" id="tags_export_to_excel_command"></a>

### TemplateFileName <a href="#template_file_name" id="template_file_name"></a>

Путь до Excel-файла шаблона. Поддерживается формат .xlsx.

Обязательный тэг. Любое значение будет переведено в текстовое.

```xml
<TemplateFileName>TemplateFileName.xlsx</TemplateFileName>
```

### Parameters <a href="#parameters" id="parameters"></a>

Параметры, которые будут переданы в файл шаблона для замены.

Необязательный тэг. Значение тэга `<Parameters>`: список тэгов [`<Parameter>`](exporttoexcelcommand.md#parameters_parameter).

```xml
<Parameters>
  <Parameter Name="ParameterName1">ParameterValue1</Parameter>
  <Parameter Name="ParameterName2">ParameterValue2</Parameter>
</Parameters>
```

#### Тэг `<Parameter>` <a href="#parameters_parameter" id="parameters_parameter"></a>

Параметр, который будет передан в файл шаблона для замены.

Необязательный тэг. Значение тэга `<Parameter>`: любое значение.

#### Атрибуты тэга `<Parameter>` <a href="#attributes_tag_parameters_parameter" id="attributes_tag_parameters_parameter"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Название параметра.</p><p></p><p>Обязательный атрибут. Значение атрибута <code>Name</code>: название одной из <a href="exporttoexcelcommand.md#supported_variables">переменных</a>, использующихся в файле шаблона.</p><p></p><p>Переменные в шаблоне задаются как &#x3C;#ParameterName1#> - для отображения скалярного значения или &#x3C;%ParameterName1%> - для отображения массива при использовании в таблице.</p></td></tr></tbody></table>

### ExportFileName <a href="#export_file_name" id="export_file_name"></a>

Имя файла, с которым он будет скачан у пользователя.

Необязательный тэг. Любое значение будет переведено в текстовое.

Если указан полный путь, то из него будет извлечено имя файла, а остальное проигнорировано.

Если тэг `<ExportFileName>` отсутствует, то используется автоматически сгенерированное значение, а для атрибута `Ask` используется значение False.

```xml
<ExportFileName Ask="False">ExportFileName</ExportFileName>
```

#### Атрибуты тэга `<ExportFileName>` <a href="#attributes_tag_export_file_name" id="attributes_tag_export_file_name"></a>

<table data-header-hidden><thead><tr><th width="228.6296484971982" align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Ask</td><td><p>Признак, определяющий, будет ли задан вопрос о пути сохранения файлов. Диалоговое окно выбора пути показывается только при наличии на странице сертификата и  при наличии разрешения от пользователя на работу с файлами (в браузере). Если диалоговое окно не удалось показать, то загрузка будет выполнена без диалогового окна.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>Если атрибут <code>Ask</code> отсутствует, то используется значение False.</p></td></tr></tbody></table>

### InsertPictures <a href="#insert_pictures" id="insert_pictures"></a>

Признак, определяющий, будет ли выполнена замена в файле шаблона тэгов вставки изображений.

Необязательный тэг. Значение тэга `<InsertPictures>`: не ожидается.

Если тэг `<InsertPictures>` отсутствует, то для атрибута `Value` используется значение True.

Если атрибут `Value` в тэге `<InsertPictures>` имеет значение False, то замена в файле шаблона тэгов вставки изображений не произойдет и тэги останутся без изменений.

```xml
<InsertPictures Value="" />
```

#### Атрибуты тэга `<InsertPictures>` <a href="#attributes_tag_insert_pictures" id="attributes_tag_insert_pictures"></a>

<table data-header-hidden><thead><tr><th width="228.6296484971982" align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Value</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается логическое значение.</p></td></tr></tbody></table>

### UseRawTags <a href="#use_raw_tags" id="use_raw_tags"></a>

Признак, определяющий, будет ли выполнена замена в файле шаблона тэгов вставки скалярных, табличных значений и изображений.

Необязательный тэг. Значение тэга `<UseRawTags>`: не ожидается.

Если тэг `<UseRawTags>` отсутствует, то для атрибута `Value` используется значение False.

Если атрибут `Value` в тэге `<UseRawTags>` имеет значение True, то замена в файле шаблона тэгов вставки скалярных и табличных значений и изображений не произойдет и тэги останутся без изменений.

```xml
<UseRawTags Value="" />
```

#### Атрибуты тэга `<UseRawTags>` <a href="#attributes_tag_use_raw_tags" id="attributes_tag_use_raw_tags"></a>

<table data-header-hidden><thead><tr><th width="231.32842626519306" align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Value</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается логическое значение.</p></td></tr></tbody></table>
