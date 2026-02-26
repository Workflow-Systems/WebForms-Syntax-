---
description: Тип даты/времени.
---

# DateTimeDataType

## Шаблон DateTimeDataType <a href="#template_date_time_data_type" id="template_date_time_data_type"></a>

```xml
<DataType Type="DateTimeDataType" Format="" ParseFormat="" />
```

### Атрибуты для форматированного вывода значения <a href="#format_attributes" id="format_attributes"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="473.3333333333333"></th></tr></thead><tbody><tr><td align="center">Format</td><td><p>Форматная строка вывода даты и времени.</p><p></p><p>Необязательный атрибут.</p></td></tr></tbody></table>

#### Поддерживаемые константы <a href="#format_constants" id="format_constants"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="473.3333333333333"></th></tr></thead><tbody><tr><td align="center">d, dd, ddd, ...</td><td>День месяца в десятичной записи (количество разрядов совпадает с количеством букв "d")</td></tr><tr><td align="center">M</td><td>Месяц года в десятичной записи одним или двумя разрядами</td></tr><tr><td align="center">MM</td><td>Месяц года в десятичной записи двумя разрядами</td></tr><tr><td align="center">MMM</td><td>Месяц года в текстовой записи тремя буквами</td></tr><tr><td align="center">MMMM</td><td>Месяц года в текстовой записи полностью название</td></tr><tr><td align="center">y, yy</td><td>Год в десятичной записи двумя разрядами</td></tr><tr><td align="center">yyy, yyyy, yyyyy, ...</td><td>Год в десятичной записи четыремя разрядами и более (количество разрядов совпадает с количеством букв "y")</td></tr><tr><td align="center">s, ss, sss, ...</td><td>Секунды в десятичной записи двумя разрядами</td></tr><tr><td align="center">m, mm, mmm, ...</td><td>Минуты в десятичной записи двумя разрядами</td></tr><tr><td align="center">h, hh, hhh, ...</td><td>Часы в 12-часовом формате в десятичной записи двумя разрядами</td></tr><tr><td align="center">H, HH, HHH, ...</td><td>Часы в 24-часовом формате в десятичной записи двумя разрядами</td></tr></tbody></table>

### Атрибуты для проверки корректности задания значения <a href="#check_attributes" id="check_attributes"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="473.3333333333333"></th></tr></thead><tbody><tr><td align="center">ParseFormat</td><td><p>Формат даты и времени для распознавания.</p><p></p><p>Необязательный атрибут.</p></td></tr></tbody></table>

#### Поддерживаемые константы <a href="#parse_format_constants" id="parse_format_constants"></a>

Аналогично [поддерживаемым константам](date_time_data_type.md#format_constants) атрибута `Format`.

### Поддерживаемые операции <a href="#operations" id="operations"></a>

1. Сложение: сложение даты и интервала времени.
2. Вычитание: вычитание из даты интервала времени.
3. Умножение: нет.
4. Деление: нет.
