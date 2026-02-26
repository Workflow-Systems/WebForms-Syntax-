---
description: Описание структуры xml-файла формы, основных тэгов и свойств формы
---

# Form.xml

## Краткий шаблон Form <a href="#short_template" id="short_template"></a>

```xml
<?xml version="1.0"?>
<Form Name="" Title="" FontStyle="" ForeColor="" StartPage="">
  <!--Тэги, специфичные для Form-->
  <Appearance></Appearance>
  <Parameters></Parameters>
  <DataConnections></DataConnections>
  <Conditions></Conditions>
  <Commands></Commands>
  <Executions></Executions>
  <Checkings></Checkings>
  <MyObjects></MyObjects>
</Form>
```

## Полный шаблон Form <a href="#full_template" id="full_template"></a>

```xml
<?xml version="1.0"?>
<Form Name="" Title="" FontStyle="" ForeColor="" BackColor="" ValidationType=""
      StartPage="" MinWidth="" MaxWidth=""
      IssueAddButton="" IssueListButton="">
  <!--Тэги, специфичные для Form-->
  <Appearance></Appearance>
  <Parameters></Parameters>
  <DataConnections></DataConnections>
  <Conditions></Conditions>
  <Commands></Commands>
  <Executions></Executions>
  <Checkings></Checkings>
  <MyObjects></MyObjects>
</Form>
```

## Описание Form <a href="#description" id="description"></a>

Тэг `<Form>` - корневой элемент файла формы.

```xml
<Form Name=""
      Title=""
      FontStyle=""
      ForeColor=""
      BackColor=""
      ValidationType=""
      StartPage=""
      MinWidth=""
      MaxWidth=""
      IssueAddButton=""
      IssueListButton="">
  <!--Тэги, специфичные для Form-->
</Form>
```

## Атрибуты Form <a href="#attributes" id="attributes"></a>

### Name

Системное имя формы. Задает url-адрес web-страницы формы.

Обязательный атрибут. Любое значение будет переведено в текстовое.

### Title

Заголовок формы.

Необязательный атрибут. Любое значение будет переведено в текстовое.

### FontStyle <a href="#font_style" id="font_style"></a>

Имя стиля шрифта формы по умолчанию.

Необязательный атрибут. Ожидается имя одного из стилей шрифтов, описанных в форме.

По умолчанию используется стандартное значение WebForms.

### ForeColor <a href="#fore_color" id="fore_color"></a>

Имя цвета текста формы по умолчанию.

Необязательный атрибут. Ожидается имя одного из цветов, описанных в форме или описание цвета в формате HTML (#rrggbb).

По умолчанию используется стандартное значение WebForms.

### BackColor <a href="#back_color" id="back_color"></a>

Имя цвета фона формы.

Необязательный атрибут. Ожидается имя одного из цветов, описанных в форме или описание цвета в формате HTML (#rrggbb).

По умолчанию используется стандартное значение WebForms.

### ValidationType <a href="#validation_type" id="validation_type"></a>

Задает вид `Checking` формы.

Необязательный атрибут. Ожидается название одного из типов `Checking`:

<table data-header-hidden><thead><tr><th align="center"></th><th width="471.3333333333333"></th></tr></thead><tbody><tr><td align="center">Asterisk</td><td>"Звёздочка" справа от объекта</td></tr><tr><td align="center">Flat</td><td>Полоска слева от объекта</td></tr></tbody></table>

По умолчанию используется значение Asterisk.

### StartPage <a href="#start_page" id="start_page"></a>

Признак, определяющий, является ли форма стартовой страницей приложения.

Необязательный атрибут. Ожидается логическое значение.

По умолчанию используется значение `False`.

### MinWidth <a href="#min_width" id="min_width"></a>

Задает минимально допустимое значение для ширины формы.

Необязательный атрибут.  Ожидается положительное целочисленное значение.

По умолчанию используется значение 0.

### MaxWidth <a href="#max_width" id="max_width"></a>

Задает максимально допустимое значение для ширины формы.

Необязательный атрибут.  Ожидается положительное целочисленное значение.

По умолчанию используется значение 1400.

### IssueAddButton <a href="#issue_add_button" id="issue_add_button"></a>

Признак, включающий отображение кнопки для создания обращения в HelpDesk.

Необязательный атрибут. Ожидается логическое значение.

По умолчанию используется значение `True`.

### IssueListButton <a href="#issue_list_button" id="issue_list_button"></a>

Признак, включающий отображение кнопки просмотра списка обращений в HelpDesk.

Необязательный атрибут. Ожидается логическое значение.

По умолчанию используется значение `True`.



## Тэги, специфичные для Form <a href="#specific-tags" id="specific-tags"></a>

### Appearance <a href="#appearance" id="appearance"></a>

Содержит графические настройки отображения формы.

Необязательный тэг. Значение тэга `<Appearance>`: см. в разделе [Appearance](./#appearance).

```xml
<Appearance></Appearance>
```

### Parameters <a href="#parameters" id="parameters"></a>

Содержит описание параметров формы.

Необязательный тэг. Значение тэга `<Parameters>`: см. в разделе [Parameters](workflow_webforms/parameters.md).

```xml
<Parameters></Parameters>
```

### DataConnections <a href="#data_connections" id="data_connections"></a>

Содержит описание соединений с данными.

Необязательный тэг. Значение тэга `<DataConnections>`: см. в разделе [DataConnections](workflow_webforms/dataconnections/).

```xml
<DataConnections></DataConnections>
```

### Conditions <a href="#conditions" id="conditions"></a>

Содержит описание условий.

Необязательный тэг. Значение тэга `<Conditions>`: см. в разделе [Conditions](workflow_webforms/conditions/).

```xml
<Conditions></Conditions>
```

### Commands <a href="#commands" id="commands"></a>

Содержит описание команд.

Необязательный тэг. Значение тэга `<Commands>`: см. в разделе [Commands](workflow_webforms/commands/).

```xml
<Commands></Commands>
```

### Executions <a href="#executions" id="executions"></a>

Содержит описание действий.

Необязательный тэг. Значение тэга `<Executions>`: см. в разделе [Executions](workflow_webforms/executions.md).

```xml
<Executions></Executions>
```

### Checkings <a href="#checkings" id="checkings"></a>

Содержит описание проверок.

Необязательный тэг. Значение тэга `<Checkings>`: см. в разделе [Checkings](workflow_webforms/checkings.md).

```xml
<Checkings></Checkings>
```

### MyObjects <a href="#my_objects" id="my_objects"></a>

Содержит описание объектов формы.

Необязательный тэг. Значение тэга `<MyObjects>`: см. в разделе [Objects](workflow_webforms/objects/).

```xml
<MyObjects></MyObjects>
```

## Get-проперти для получения свойств <a href="#get_properties" id="get_properties"></a>

### Title <a href="#get_title" id="get_title"></a>

Возвращает заголовок формы.

```xml
<Form>
  <Property Name="Title" />
</Form>
```

### FontStyle <a href="#get_font_style" id="get_font_style"></a>

Возвращает имя стиля шрифта формы по умолчанию.

```xml
<Form>
  <Property Name="FontStyle" />
</Form>
```

### ForeColor <a href="#get_fore_color" id="get_fore_color"></a>

Возвращает имя цвета текста формы по умолчанию.

```xml
<Form>
  <Property Name="ForeColor" />
</Form>
```

### BackColor <a href="#get_back_color" id="get_back_color"></a>

Возвращает имя цвета фона формы.

```xml
<Form>
  <Property Name="BackColor" />
</Form>
```

### DateTimeNow <a href="#get_date_time_now" id="get_date_time_now"></a>

Возвращает рабочую дату и время формы, определенную первый раз в момент открытия формы.

```xml
<Form>
  <Property Name="DateTimeNow" />
</Form>
```

### FormChanged <a href="#get_form_changed" id="get_form_changed"></a>

Возвращает признак изменения формы (определяется как совокупность get-проперти `ValueChanged` объектов на форме).

```xml
<Form>
  <Property Name="FormChanged" />
</Form>
```

### ChangedObjects <a href="#get_changed_objects" id="get_changed_objects"></a>

Возвращает список изменённых объектов.

```xml
<Form>
  <Property Name="ChangedObjects" />
</Form>
```

### CheckingFired <a href="#get_checking_fired" id="get_checking_fired"></a>

Возвращает признак, определяющий, сработал ли хоть один [`<Checking>`](./#checkings).

Если в качестве параметра передано имя группы, то возвращает признак, определяющий, сработал ли хоть один [`<Checking>`](./#checkings) в группе.

```xml
<Form>
  <Property Name="CheckingFired" />
</Form>
```

```xml
<Form>
  <Property Name="CheckingFired">Group</Property>
</Form>
```

### MinWidth <a href="#get_min_width" id="get_min_width"></a>

Возвращает минимальное допустимое значение ширины формы.

```xml
<Form>
  <Property Name="MinWidth" />
</Form>
```

### MaxWidth <a href="#get_max_width" id="get_max_width"></a>

Возвращает максимально допустимое значение ширины формы.

```xml
<Form>
  <Property Name="MaxWidth" />
</Form>
```

### WindowWidth <a href="#get_window_width" id="get_window_width"></a>

Возвращает внутреннюю ширину окна в пикселях (то есть ширину области просмотра макета окна).\
Значение _учитывает_ ширину вертикальной полосы прокрутки, если она присутствует.

```xml
<Form>
  <Property Name="WindowWidth" />
</Form>
```

### WindowHeight <a href="#get_window_height" id="get_window_height"></a>

Возвращает внутреннюю высоту окна в пикселях (то есть высоту области просмотра макета окна).\
Значение _учитывает_ высоту горизонтальной полосы прокрутки, если она присутствует.

```xml
<Form>
  <Property Name="WindowHeight" />
</Form>
```

### ClientWidth <a href="#get_client_width" id="get_client_width"></a>

Возвращает внутреннюю ширину окна в пикселях (то есть ширину области просмотра макета окна).\
Значение _исключает_ ширину вертикальной полосы прокрутки, если она присутствует.

```xml
<Form>
  <Property Name="ClientWidth" />
</Form>
```

### ClientHeight <a href="#get_client_height" id="get_client_height"></a>

Возвращает внутреннюю высоту окна в пикселях (то есть высоту области просмотра макета окна).\
Значение _исключает_ высоту горизонтальной полосы прокрутки, если она присутствует.

```xml
<Form>
  <Property Name="ClientHeight" />
</Form>
```

### LoadMode <a href="#get_load_mode" id="get_load_mode"></a>

Возвращает идентификатор выбранного режима загрузки данных.

```xml
<Form>
  <Property Name="LoadMode" />
</Form>
```

Возвращает одно из значений:

<table data-header-hidden><thead><tr><th width="106" align="center"></th><th></th></tr></thead><tbody><tr><td align="center">0</td><td><p>Последовательный режим - загрузка соединений с данными будет происходить по очереди.</p><p>Обеспечивает минимальную скорость загрузки форм, при этом требует минимальное количество ресурсов со стороны сервера.</p></td></tr><tr><td align="center">1</td><td><p>Пакетный режим.</p><p>Обеспечивает стандартную скорость загрузки форм, при этом не требует значительного количества ресурсов со стороны сервера.</p></td></tr><tr><td align="center">2</td><td><p>Параллельный режим. Режим по умолчанию.</p><p>Обеспечивает увеличенную скорость загрузки форм, однако при этом требует максимальное количество ресурсов со стороны сервера. </p></td></tr></tbody></table>

### IssueCount <a href="#get_issue_count" id="get_issue_count"></a>

Возвращает количество обращений в HelpDesk.

```xml
<Form>
  <Property Name="IssueCount" />
</Form>
```

### ValidationType

Возвращает название вида `Checking` формы..

```xml
<Form>
  <Property Name="IssueCount" />
</Form>
```

## Set-проперти для динамического задания свойств <a href="#set_properties" id="set_properties"></a>

### Title <a href="#set_title" id="set_title"></a>

Задает заголовок формы.

Любое значение будет переведено в текстовое.

```xml
<Form>
  <Property Name="Title">Заголовок</Property>
</Form>
```

### DateTimeNow <a href="#set_date_time_now" id="set_date_time_now"></a>

Задает рабочую дату и время формы, определенную первый раз в момент открытия формы.

Ожидается значение типа дата/время.

```xml
<Form>
  <Property Name="DateTimeNow">2015-11-04 23:42:50</Property>
</Form>
```

### RefreshDateTimeNow <a href="#set_refresh_date_time_now" id="set_refresh_date_time_now"></a>

Задает рабочую дату и время формы, равную текущей дате и времени.

Значение тэга `<Property>`: не ожидается.

```xml
<Form>
  <Property Name="RefreshDateTimeNow" />
</Form>
```

### FormChanged <a href="#set_form_changed" id="set_form_changed"></a>

Задает признак изменения формы (определяется как совокупность get-проперти `ValueChanged` объектов на форме).

Если `FormChanged` присваивается значение False, то проперти `ValueChanged` всех объектов формы тоже приобретут значение False.

Ожидается логическое значение.

```xml
<Form>
  <Property Name="FormChanged">False</Property>
</Form>
```

### MinWidth <a href="#set_min_width" id="set_min_width"></a>

Задает минимальное допустимое значение ширины формы.

Ожидается положительное целочисленное значение.

```xml
<Form>
  <Property Name="FormChanged">200</Property>
</Form>
```

### MaxWidth <a href="#set_max_width" id="set_max_width"></a>

Задает максимально допустимое значение ширины формы.

Ожидается положительное целочисленное значение.

```xml
<Form>
  <Property Name="MaxWidth">1000</Property>
</Form>
```

### ValidationType <a href="#set_validation_type" id="set_validation_type"></a>

Задает вид `Checking` формы.

Ожидается название одного из видов `Checking` формы.

```xml
<Form>
  <Property Name="ValidationType">Flat</Property>
</Form>
```
