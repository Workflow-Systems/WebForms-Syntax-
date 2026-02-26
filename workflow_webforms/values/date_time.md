---
description: Константы даты/времени.
---

# DateTime

## Шаблон DateTime <a href="#template_date_time" id="template_date_time"></a>

```xml
<DateTime Variable="" />
```

Обновляются при вызове set-свойства [RefreshDateTimeNow](/broken/pages/-MaRrLvqMdBI-ceJPvyX#set_refresh_date_time_now) формы.

#### Возможные значения атрибута `Variable` <a href="#variable_values" id="variable_values"></a>

<table data-header-hidden><thead><tr><th width="230.74116669769973" align="center">Значение</th><th width="506.76793031130524">Описание</th></tr></thead><tbody><tr><td align="center">Interval</td><td><p>Интервал времени, заданный в формате </p><p>[{Years}y][ {Month}M][ {Days}d][ {Hours}h][ {Minutes}m][ {Seconds}s] </p><p>Например, "10y" - 10 лет, "1M 2d 3h" - 1 месяц 2 дня и 3 часа</p></td></tr><tr><td align="center">Now</td><td>Текущая дата и время</td></tr><tr><td align="center">NowDate</td><td>Текущая дата (на момент открытия формы)</td></tr><tr><td align="center">NowDateHour</td><td>Текущая дата и время с точностью до часа (на момент открытия формы)</td></tr><tr><td align="center">ActualNow</td><td>Текущая дата и время (на момент обращения)</td></tr><tr><td align="center">ActualNowDate</td><td>Текущая дата (на момент обращения)</td></tr><tr><td align="center">ActualNowDateHour</td><td>Текущая дата и время с точностью до часа (на момент обращения)</td></tr><tr><td align="center">FirstDayOfCurrWeek</td><td>Первый день текущей недели</td></tr><tr><td align="center">LastDayOfCurrWeek</td><td>Последний день текущей недели</td></tr><tr><td align="center">FirstDayOfCurrMonth</td><td>Первый день текущего месяца</td></tr><tr><td align="center">LastDayOfCurrMonth</td><td>Последний день текущего месяца</td></tr><tr><td align="center">LastDayOfPrevMonth</td><td>Последний день предыдущего месяца</td></tr><tr><td align="center">FirstDayOfNextMonth</td><td>Первый день следующего месяца</td></tr><tr><td align="center">FirstDayOfCurrYear</td><td>Первый день текущего года</td></tr><tr><td align="center">LastDayOfCurrYear</td><td>Последний день текущего года</td></tr></tbody></table>
