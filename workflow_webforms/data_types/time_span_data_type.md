---
description: Тип интервала даты/времени.
---

# TimeSpanDataType

## Шаблон TimeSpanDataType <a href="#template_time_span_data_type" id="template_time_span_data_type"></a>

```xml
<DataType Type="TimeSpanDataType" Format="" />
```

### Атрибуты для форматированного вывода значения <a href="#format_attributes" id="format_attributes"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="473.3333333333333"></th></tr></thead><tbody><tr><td align="center">Format</td><td><p>Форматная строка вывода интервала даты и времени.</p><p></p><p>Необязательный атрибут.</p></td></tr></tbody></table>

#### Поддерживаемые константы <a href="#format_constants" id="format_constants"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="473.3333333333333"></th></tr></thead><tbody><tr><td align="center">d</td><td>Количество дней (не больше 30) в десятичной записи с не менее чем одним разрядом</td></tr><tr><td align="center">dd</td><td>Количество дней (не больше 30) в десятичной записи с не менее чем двумя разрядами</td></tr><tr><td align="center">ddd</td><td>Общее количество дней в десятичной записи с не менее чем одним разрядом</td></tr><tr><td align="center">dddd</td><td>Общее количество дней в десятичной записи с не менее чем двумя разрядами</td></tr><tr><td align="center">ddddd</td><td>Общее количество дней в десятичной записи с не менее чем тремя разрядами</td></tr><tr><td align="center">M</td><td>Количество месяцев (не больше 12) в десятичной записи с не менее чем одним разрядом</td></tr><tr><td align="center">MM</td><td>Количество месяцев (не больше 12) в десятичной записи с не менее чем двумя разрядами</td></tr><tr><td align="center">Y</td><td>Количество лет в десятичной записи с не менее чем одним разрядом</td></tr><tr><td align="center">YY</td><td>Количество лет в десятичной записи с не менее чем двумя разрядами</td></tr><tr><td align="center">s, ss, sss, ...</td><td>Секунды в десятичной записи</td></tr><tr><td align="center">m, mm, mmm, ...</td><td>Минуты в десятичной записи</td></tr><tr><td align="center">h, hh, hhh, ...</td><td>Часы в 12-часовом формате в десятичной записи</td></tr><tr><td align="center">H, HH, HHH, ...</td><td>Часы в 24-часовом формате в десятичной записи</td></tr></tbody></table>

### Поддерживаемые операции <a href="#operations" id="operations"></a>

1. Сложение: сложение интервалов.
2. Вычитание: вычитание интервалов.
3. Умножение: умножение интервала на число.
4. Деление: деление интервала на число.
