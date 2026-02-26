---
description: Графический объект; поле с датой и временем.
---

# DateTimePicker

## Шаблон DateTimePicker <a href="#template_datetimepicker" id="template_datetimepicker"></a>

Перечень всех возможных тэгов объекта:

```xml
<MyObject Name="" Type="DateTimePicker" Assembly="BaseControls" ChangeForm="">
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
  <!--Тэги, специфичные для DateTimePicker-->
  <FormatType></Format>  
  <ShowCalendar></ShowCalendar> 
  <NullValue Show="" />
  <Value></Value>
</MyObject>
```

## Описание DateTimePicker <a href="#description_datetimepicker" id="description_datetimepicker"></a>

```xml
<MyObject Name="DateTimePickerName" Type="DateTimePicker" Assembly="BaseControls">
  <!--Тэги, общие для всех графических объектов-->
  <!--Тэги, специфичные для DateTimePicker-->
</MyObject>
```

### Получение значения DateTimePicker <a href="#get_value_datetimepicker" id="get_value_datetimepicker"></a>

Значением DateTimePicker считается значение даты, указанной в поле.

В зависимости от формата даты значение DateTimePicker может быть разных типов:

1. Если в формате задана только дата, то значение DateTimePicker будет типа Date.
2. Если в формате задано только время, то значение DateTimePicker будет типа TimeSpan.
3. Если в формате задана и дата, и время, то значение DateTimePicker будет типа DateTime.

```xml
<Object Name="DateTimePickerName" />
```

### Задание значения DateTimePicker <a href="#set_value_datetimepicker" id="set_value_datetimepicker"></a>

Ожидается значение типа дата/время.

```xml
<Object Name="DateTimePickerName"></Object>
```

## Тэги, специфичные для DateTimePicker <a href="#tags_datetimepicker" id="tags_datetimepicker"></a>

### FormatType

Формат даты.

Необязательный тэг. Любое значение будет переведено в текстовое.

Ожидается один из типов формата даты:

<table data-header-hidden><thead><tr><th width="246"></th><th></th></tr></thead><tbody><tr><td>Date</td><td>Дата</td></tr><tr><td>DateTime</td><td>Дата со временем</td></tr><tr><td>Time</td><td>Время</td></tr></tbody></table>

По умолчанию используется значение `Date`.

```xml
<FormatType>DateTime</Format>
```

### ShowCalendar <a href="#show_calendar" id="show_calendar"></a>

Признак, определяющий, будет ли показан календарь.

Необязательный тэг. Ожидается логическое значение.

По умолчанию используется значение True.

```xml
<ShowCalendar>True</ShowCalendar>
```

### NullValue <a href="#null_value" id="null_value"></a>

Настройка отображения NULL-значения объекта.

Необязательный тэг. Значение тэга `<NullValue>`: не ожидается.

Если тэг `<NullValue>` отсутствует, то для атрибута `Show` используется значение True.

```xml
<NullValue Show="True" />
```

#### Атрибуты тэга `<NullValue>` <a href="#attributes_tag_null_value" id="attributes_tag_null_value"></a>

<table data-header-hidden><thead><tr><th></th><th width="435.6666666666667"></th></tr></thead><tbody><tr><td>Show</td><td><p>Признак, определяющий, может ли дата иметь значение NULL.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p></td></tr></tbody></table>

### MinDate <a href="#min_date" id="min_date"></a>

Признак, определяющий минимальное значение даты и времени, которые могут быть выбраны в поле.

Необязательный тэг. Ожидается значения типа дата/время.

По умолчанию используется минимально возможное значение даты.

```xml
<MinDate>1900-01-01</MinDate>
```

### MaxDate <a href="#max_date" id="max_date"></a>

Признак, определяющий максимальное значение даты и времени, которые могут быть выбраны в поле.

Необязательный тэг. Ожидается значения типа дата/время.

По умолчанию используется максимально возможное значение даты.

```xml
<MaxDate>2100-01-01</MaxDate>
```

### Value <a href="#value" id="value"></a>

Значение поля.

Необязательный тэг. Ожидается значения типа дата/время.

```xml
<Value>2012-05-10</Value>
```

## Get-проперти для получения свойств <a href="#get_property_datetimepicker" id="get_property_datetimepicker"></a>

### FormatType <a href="#get_format" id="get_format"></a>

Возвращает тип формата даты в поле.&#x20;

```xml
<Object Name="DateTimePickerName">
  <Property Name="FormatType" />
</Object>
```

### ShowCalendar <a href="#get_show_calendar" id="get_show_calendar"></a>

Возвращает признак, определяющий, будет ли показан календарь.&#x20;

```xml
<Object Name="DateTimePickerName">
  <Property Name="ShowCalendar" />
</Object>
```

### DayOfWeek <a href="#get_day_of_week" id="get_day_of_week"></a>

Возвращает день недели даты, указанной в контроле, в виде числа от 0 до 6.

```xml
<Object Name="DateTimePickerName">
  <Property Name="DayOfWeek" />
</Object>
```

### MinDate <a href="#get_min_date" id="get_min_date"></a>

Возвращает минимальное значение даты.

```xml
<Object Name="DateTimePickerName">
  <Property Name="MinDate" />
</Object>
```

### MaxDate <a href="#get_max_date" id="get_max_date"></a>

Возвращает максимальное значение даты.

```xml
<Object Name="DateTimePickerName">
  <Property Name="MaxDate" />
</Object>
```



## Set-проперти для динамического задания свойств <a href="#set_property_datetimepicker" id="set_property_datetimepicker"></a>

### FormatType <a href="#set_format" id="set_format"></a>

Задает тип формата даты поля.

Ожидается один из типов формата даты. Любое значение будет переведено в текстовое.

```xml
<Object Name="DateTimePickerName">
  <Property Name="FormatType">Date</Property>
</Object>
```

### ShowCalendar <a href="#set_show_calendar" id="set_show_calendar"></a>

Задает признак, определяющий, будет ли показан календарь.

Ожидается логическое значение.

```xml
<Object Name="DateTimePickerName">
  <Property Name="ShowCalendar">False</Property>
</Object>
```

### MinDate <a href="#set_min_date" id="set_min_date"></a>

Задает минимальное значение даты.

```xml
<Object Name="DateTimePickerName">
  <Property Name="MinDate">1900-01-01</Property>
</Object>
```

### MaxDate <a href="#set_max_date" id="set_max_date"></a>

Задает максимальное значение даты.

```xml
<Object Name="DateTimePickerName">
  <Property Name="MaxDate">2100-01-01</Property>
</Object>
```
