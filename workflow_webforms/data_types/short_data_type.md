---
description: Тип целого числа (16 бит).
---

# ShortDataType



## Шаблон ShortDataType <a href="#template_short_data_type" id="template_short_data_type"></a>

```xml
<DataType Type="ShortDataType" Format="" MinValue="" MaxValue="" Precision="" AllowNull="" />
```

### Атрибуты для форматированного вывода значения <a href="#format_attributes" id="format_attributes"></a>

<table data-header-hidden><thead><tr><th width="203.6583615302477" align="center"></th><th width="473.3333333333333"></th></tr></thead><tbody><tr><td align="center">Format</td><td><p>Форматная строка вывода целого числа.</p><p></p><p>Необязательный атрибут.</p></td></tr></tbody></table>

#### Поддерживаемые константы <a href="#format_constants" id="format_constants"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="473.3333333333333"></th></tr></thead><tbody><tr><td align="center">"0"</td><td>Разряд; например, число 1 при форматной строке "000" будет выведено как "001"</td></tr><tr><td align="center">"N2"</td><td>Отображение в формате "0 000,00" с разделителями между триадами цифр; например, число 1234,567 будет выведено как "1 234,58"</td></tr></tbody></table>

### Атрибуты для проверки корректности задания значения <a href="#check_attributes" id="check_attributes"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="473.3333333333333"></th></tr></thead><tbody><tr><td align="center">MinValue</td><td><p>Минимально допустимое значение целого числа.</p><p></p><p>Необязательный атрибут.</p></td></tr><tr><td align="center">MaxValue</td><td><p>Максимально допустимое значение целого числа.</p><p></p><p>Необязательный атрибут.</p></td></tr><tr><td align="center">Precision</td><td><p>Количество разрядов, начиная с младших, незначимых при сравнении чисел.</p><p></p><p>Необязательный атрибут.</p></td></tr><tr><td align="center">AllowNull</td><td><p>Разрешить ввод и хранение пустого значения типа (если атрибут отсутствует или равен False, то пустая строка конвертируется в 0).</p><p></p><p>Необязательный атрибут.</p></td></tr></tbody></table>

### Поддерживаемые операции <a href="#operations" id="operations"></a>

1. Сложение: сложение целых чисел.
2. Вычитание: вычитание целых чисел.
3. Умножение: умножение целых чисел.
4. Деление: деление целых чисел.
