---
description: Логический тип данных.
---

# BooleanDataType

## Шаблон BooleanDataType <a href="#template_boolean_data_type" id="template_boolean_data_type"></a>

```xml
<DataType Type="BooleanDataType" TrueTitle="" FalseTitle="" />
```

### Атрибуты для форматированного вывода значения <a href="#format_attributes" id="format_attributes"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="473.3333333333333"></th></tr></thead><tbody><tr><td align="center">TrueTitle</td><td><p>Текстовое значение, соответствующее значению True.</p><p></p><p>Необязательный атрибут.</p></td></tr><tr><td align="center">FalseTitle</td><td><p>Текстовое значение, соответствующее значению False.</p><p></p><p>Необязательный атрибут.</p></td></tr></tbody></table>

### Поддерживаемые операции <a href="#operations" id="operations"></a>

1. Сложение: дизъюнкция.
2. Вычитание: отрицание.
3. Умножение: конъюнкция.
4. Деление: исключающее "или".
