---
description: Графический объект; поле для выбора числа.
---

# NumericBox

## Шаблон NumericBox <a href="#template_numericbox" id="template_numericbox"></a>

Перечень всех возможных тэгов объекта:

```xml
<MyObject Name="" Type="NumericBox" Assembly="BaseControls" ChangeForm="">
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
  <!--Тэги, специфичные для NumericBox-->
  <ReadOnly></ReadOnly>
  <Maximum></Maximum>
  <Minimum></Minimum>
  <DecimalPlaces></DecimalPlaces>
  <Value></Value>
</MyObject>
```

## Описание NumericBox <a href="#description_numericbox" id="description_numericbox"></a>

```xml
<MyObject Name="NumericBoxName" Type="NumericBox" Assembly="BaseControls">
  <!--Тэги, общие для всех графических объектов-->
  <!--Тэги, специфичные для NumericBox-->
</MyObject>
```

### Получение значения NumericBox <a href="#get_value_numericbox" id="get_value_numericbox"></a>

Значением NumericBox считается значение числа, указанного в поле.

```xml
<Object Name="NumericBoxName" />
```

### Задание значения NumericBox <a href="#set_value_numericbox" id="set_value_numericbox"></a>

Ожидается числовое значение.

```xml
<Object Name="NumericBoxName"></Object>
```

## Тэги, специфичные для NumericBox <a href="#tags_numericbox" id="tags_numericbox"></a>

### ReadOnly <a href="#read_only" id="read_only"></a>

Признак, определяющий, запрещен ли ввод текста в поле для пользователя.

Необязательный тэг. Ожидается логическое значение.

По умолчанию используется значение False.

```xml
<ReadOnly>False</ReadOnly>
```

### Maximum <a href="#maximum" id="maximum"></a>

Максимально допустимое число для ввода.

Необязательный тэг. Ожидается числовое значение.

Если тэг `<Maximum>` отсутствует, то ограничение на максимум не устанавливается.

```xml
<Maximum>100</Maximum>
```

### Minimum <a href="#minimum" id="minimum"></a>

Минимальное допустимое число для ввода.

Необязательный тэг. Ожидается числовое значение.

Если тэг `<Minimum>` отсутствует, то ограничение на минимум не устанавливается.

```xml
<Minimum>0</Minimum>
```

### DecimalPlaces <a href="#decimal_places" id="decimal_places"></a>

Количество знаков дробной части числа.

Необязательный тэг. Ожидается целочисленное значение.

По умолчанию используется значение 0.

{% hint style="info" %}
Этот тэг также устанавливает шаг инкремента `NumericBox`.

Если для DecimalPlaces установлено значение 2, то шаг будет равен 0.01.

Если для DecimalPlaces установлено значение 0, то шаг будет равен 1.

Если для DecimalPlaces установлено значение 1, то шаг будет равен 0.1.
{% endhint %}

```xml
<DecimalPlaces>0</DecimalPlaces>
```

### Value <a href="#value" id="value"></a>

Число в поле.

Необязательный тэг. Ожидается числовое значение.

По умолчанию используется значение NULL.

```xml
<Value>1</Value>
```

## Get-проперти для получения свойств <a href="#get_property_numericbox" id="get_property_numericbox"></a>

### ReadOnly <a href="#get_read_only" id="get_read_only"></a>

Возвращает признак, определяющий, запрещен ли ввод текста в поле для пользователя.

```xml
<Object Name="NumericBoxName">
  <Property Name="ReadOnly" />
</Object>
```

### Maximum <a href="#get_maximum" id="get_maximum"></a>

Возвращает максимально допустимое число для ввода.

```xml
<Object Name="NumericBoxName">
  <Property Name="Maximum" />
</Object>
```

### Minimum <a href="#get_minimum" id="get_minimum"></a>

Возвращает минимальное допустимое число для ввода.

```xml
<Object Name="NumericBoxName">
  <Property Name="Minimum" />
</Object>
```

### DecimalPlaces <a href="#get_decimal_places" id="get_decimal_places"></a>

Возвращает количество знаков дробной части числа.

```xml
<Object Name="NumericBoxName">
  <Property Name="DecimalPlaces" />
</Object>
```

## Set-проперти для динамического задания свойств <a href="#set_property_numericbox" id="set_property_numericbox"></a>

### ReadOnly <a href="#set_read_only" id="set_read_only"></a>

Задает признак, определяющий, запрещен ли ввод текста в поле для пользователя.

Ожидается логическое значение.

```xml
<Object Name="NumericBoxName">
  <Property Name="ReadOnly">True</Property>
</Object>
```

### Maximum <a href="#set_maximum" id="set_maximum"></a>

Задает максимально допустимое число для ввода.

Ожидается числовое значение.

```xml
<Object Name="NumericBoxName">
  <Property Name="Maximum">1000</Property>
</Object>
```

### Minimum <a href="#set_minimum" id="set_minimum"></a>

Задает минимальное допустимое число для ввода.

Ожидается числовое значение.

```xml
<Object Name="NumericBoxName">
  <Property Name="Minimum">-1000</Property>
</Object>
```

### DecimalPlaces <a href="#set_decimal_places" id="set_decimal_places"></a>

Задает количество знаков дробной части числа.

Ожидается целочисленное значение.

```xml
<Object Name="NumericBoxName">
  <Property Name="DecimalPlaces">3</Property>
</Object>
```
