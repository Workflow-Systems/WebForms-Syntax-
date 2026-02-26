---
description: >-
  Команда; генерирует DOCX-файл из шаблона, в котором вместо переменных
  подставляются определенные значения и скачивает его
---

# ExportToDocxCommand

## Поддерживаемые переменные <a href="#supported_variables" id="supported_variables"></a>

В значениях параметров могут быть использованы тэги для изменения форматирования параметра.

#### Тэги форматирования <a href="#variables_formatting_tags" id="variables_formatting_tags"></a>

<table data-header-hidden><thead><tr><th width="254.84751575458438" align="center"></th><th width="469.3333333333333"></th></tr></thead><tbody><tr><td align="center">[b][/b]</td><td>Задает полужирное начертание отрывка текста.</td></tr><tr><td align="center">[i][/i]</td><td>Выделяет отрывок текста курсивом.</td></tr><tr><td align="center">[u][/u]</td><td>Выделяет отрывок текста подчёркиванием.</td></tr><tr><td align="center">[br]</td><td>Перенос текста на новую строку.</td></tr><tr><td align="center">[size={value}][/size]</td><td><p>Задает отрывку текста размер шрифта.</p><p></p><p>В качестве {value} ожидается целочисленное значение.</p></td></tr></tbody></table>

Тэги форматирования заданные в тексте шаблона не заменяются.

### <#variable#> <a href="#variable_scalar" id="variable_scalar"></a>

Служит для отображения скалярного значения.

### <%variable%> <a href="#variable_array" id="variable_array"></a>

Служит для отображения массива (для использования в таблице).

### <\~variable\~> <a href="#variable_document" id="variable_document"></a>

Служит для полного переноса содержимого другого документа (подшаблона) в шаблон.

В тексте используемого подшаблона могут использоваться переменные, после вставки текста в шаблон они также будут заменены.

В качестве значения переменной должен передаваться либо полный путь до вставляемого файла, либо относительный к текущей форме.

Выражение может быть дополнено параметрами: <\~variable\[?pageBreakBefore]\[?pageBreakAfter]\~>, где:

* pageBreakBefore - вставить символ переноса на новую страницу перед текстом подшаблона;
* pageBreakAfter - вставить символ переноса на новую страницу после текста подшаблона.

### <@PATH@> <a href="#variable_image" id="variable_image"></a>

Служит для вставки изображения.

Например, для вставки изображения с параметризованным путем следует указать выражения вида <@<#variable#>@> - для скалярных значений и <@<%variable%>@> - для массивов.

Выражение PATH имеет следующий формат: PATH\[?width=INT]\[?height=INT]\[?mode=MODE]\[?rotation=INT], где:

* PATH - полный путь до файла изображения;
* width - необязательный параметр ширины изображения; в качестве значения INT ожидается положительное целочисленное значение;
* height - необязательный параметр высоты изображения; в качестве значения INT ожидается положительное целочисленное значение;
* mode - необязательный параметр типа размера; в качестве значения MODE ожидается [тип размера изображения](exporttodocxcommand.md#image_mode_types) (по умолчанию "Zoom");
* rotation - необязательный параметр поворота изображения; в качестве значения INT ожидается целочисленное значение в диапазоне от -360 до 360 градусов.

#### Типы размера изображения <a href="#image_mode_types" id="image_mode_types"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="469.3333333333333"></th></tr></thead><tbody><tr><td align="center">Zoom</td><td>Растягивание изображения до указанной ширины и высоты (в большую или меньшую сторону), сохраняя пропорции изображения</td></tr><tr><td align="center">ZoomLess</td><td>Растягивание изображения до указанной ширины и высоты (только в меньшую сторону), сохраняя пропорции изображения</td></tr><tr><td align="center">Stretch</td><td>Растягивание изображения до указанной ширины и высоты без сохранения пропорций изображения</td></tr></tbody></table>

## Шаблон ExportToDocxCommand <a href="#template_export_to_docx_command" id="template_export_to_docx_command"></a>

```xml
<Command Name="" Type="ExportToDocxCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <Condition Name="" />
  <Lock Value="" />
  <!--Тэги, специфичные для ExportToDocxCommand-->
  <TemplateFileName></TemplateFileName>
  <Parameters>
    <Parameter Name=""></Parameter>
  </Parameters>
  <GroupTags SingleFile=""></GroupTags>
  <ExportFileName Ask=""></ExportFileName>
  <InsertPictures Value="" />
  <UseRawTags Value="" />
</Command>
```

## Описание ExportToDocxCommand <a href="#description_export_to_docx_command" id="description_export_to_docx_command"></a>

```xml
<Command Name="ExportToDocxCommandName" Type="ExportToDocxCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <!--Тэги, специфичные для ExportToDocxCommand-->
</Command>
```

### Результат выполнения ExportToDocxCommand <a href="#result_export_to_docx_command" id="result_export_to_docx_command"></a>

#### Value <a href="#result_value" id="result_value"></a>

Команда не имеет результата.

## Тэги, специфичные для ExportToDocxCommand <a href="#tags_export_to_docx_command" id="tags_export_to_docx_command"></a>

### TemplateFileName <a href="#template_file_name" id="template_file_name"></a>

Путь до DOCX-файла шаблона.

Обязательный тэг. Любое значение будет переведено в текстовое.

```xml
<TemplateFileName>TemplateFileName.docx</TemplateFileName>
```

### Parameters <a href="#parameters" id="parameters"></a>

Параметры, которые будут переданы в файл шаблона для замены.

Необязательный тэг. Значение тэга `<Parameters>`: список тэгов [`<Parameter>`](exporttodocxcommand.md#parameters_parameter).

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

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Название параметра.</p><p></p><p>Обязательный атрибут. Значение атрибута <code>Name</code>: название одной из <a href="exporttodocxcommand.md#supported_variables">переменных</a>, использующихся в файле шаблона.</p><p></p><p>Переменные в шаблоне задаются как &#x3C;#ParameterName1#> - для отображения скалярного значения или &#x3C;%ParameterName1%> - для отображения массива при использовании в таблице.</p></td></tr></tbody></table>

### GroupTags <a href="#group_tags" id="group_tags"></a>

Группировочные признаки параметров (экспорт в несколько файлов одновременно).

Необязательный тэг. Ожидается линейный массив значений.

Если тэг `<GroupTags>` отсутствует, то экспорт происходит только в 1 файл.

```xml
<GroupTags SingleFile="False"></GroupTags>
```

#### Атрибуты тэга `<GroupTags>` <a href="#attributes_tag_group_tags" id="attributes_tag_group_tags"></a>

<table data-header-hidden><thead><tr><th width="228.6296484971982" align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">SingleFile</td><td><p>Признак, определяющий, будут ли экспортируемые файлы объединены в один документ.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>Если атрибут <code>SingleFile</code> отсутствует, то используется значение False.</p></td></tr></tbody></table>

#### Пример <a href="#example_group_tags" id="example_group_tags"></a>

Значение тэга `<GroupTags>` - массив некоторых значений: "Значение A; Значение B; Значение C". Это уже означает, что будет создано 3 DOCX-файла (по количеству значений в массиве `<GroupTags>`). Нужно только распределить значения параметров по этим файлам. Правила распределения следующие:

1\. Если параметр представляет собой матрицу значений, то первый ее столбец будет использоваться как указание на то, к какому файлу следует соотнести значение из второго столбца.

Например, рассмотрим в качестве значения параметра "Prm1" следующую матрицу:

<table data-header-hidden><thead><tr><th width="364.21182266009856" align="center"></th><th width="363" align="center"></th></tr></thead><tbody><tr><td align="center">Значение A</td><td align="center">Значение A1</td></tr><tr><td align="center">Значение B</td><td align="center">Значение B1</td></tr><tr><td align="center">Значение B</td><td align="center">Значение B2</td></tr><tr><td align="center">Значение C</td><td align="center">Значение C1</td></tr><tr><td align="center">Значение D</td><td align="center">Значение D1</td></tr></tbody></table>

В соответствии с этим правилом, для выгружаемого файла, соответствующему группировочному признаку "Значение A", значение параметра "Prm1" будет "Значение A1"; для файла "Значение B" - массив значений "Значение B1; Значение B2"; для файла "Значение C" - "Значение C1". Последняя строка матрицы "Значение D; Значение D1" не будет адресована ни в один файл, т.к. значение в первом столбце не соответствует ни одному из группировочных значений.

2\. Если параметр не является матрицей (массив или скалярное значение), то данный параметр будет адресован во все создаваемые файлы без изменений.

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
