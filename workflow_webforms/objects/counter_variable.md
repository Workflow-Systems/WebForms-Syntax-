---
description: Переменная-счетчик
---

# CounterVariable

## Шаблон CounterVariable <a href="#template_variable" id="template_variable"></a>

Перечень всех возможных тэгов объекта:

```xml
<MyObject Name="" Type="CounterVariable" Assembly="WorkflowServer" ChangeForm="">
  <!--Тэги, общие для всех объектов-->
  <Change User="" Source="" ValueSet="" />
  <Value></Value>
  <!--Тэги, специфичные для CounterVariable-->
  <!--Отсутствуют-->
</MyObject>
```

## Описание CounterVariable <a href="#description_variable" id="description_variable"></a>

```xml
<MyObject Name="" Type="CounterVariable" Assembly="WorkflowServer">
  <!--Тэги, общие для всех объектов-->
  <!--Тэги, специфичные для CounterVariable-->
</MyObject>
```

Значением объекта CounterVariable считается текущее значение последовательности. В тэге [`<Value>`](counter_variable.md#value) указывается начальное значение счетчика. По умолчанию счет начинается с 0.

### Получение значения CounterVariable <a href="#get_value_variable" id="get_value_variable"></a>

Для получения текущего значения счетчика используется get-проперти [Value](counter_variable.md#get_value):

```xml
<Object Name="CounterVariableName">
  <Property Name="Value" />
</Object>
```

Рекомендуется использовать сокращенный вариант записи:

```xml
<Object Name="CounterVariableName" />
```

### Задание значения CounterVariable <a href="#set_value_variable" id="set_value_variable"></a>

Для задания текущего значения счетчика используется set-проперти [Value](counter_variable.md#set_value):

```xml
<Object Name="CounterVariableName">
  <Property Name="Value">Новое значение</Property>
</Object>
```

Рекомендуется использовать сокращенный вариант записи:

```xml
<Object Name="CounterVariableName">Новое значение</Object>
```

## Get-проперти для получения свойств <a href="#get_property_variable" id="get_property_variable"></a>

### Value <a href="#get_value" id="get_value"></a>

Возвращает текущее значение счетчика.

```xml
<Object Name="CounterVariableName">
  <Property Name="Value" />
</Object>
```

### ValueChanged <a href="#get_value_changed" id="get_value_changed"></a>

Возвращает признак того, было ли изменено значение объекта Variable в процессе работы.

```xml
<Object Name="CounterVariableName">
  <Property Name="ValueChanged" />
</Object>
```

## Set-проперти для динамического задания свойств <a href="#set_property_variable" id="set_property_variable"></a>

### Value <a href="#set_value" id="set_value"></a>

Задает текущее значение счетчика.

Ожидается неотрицательное целое значение.

```xml
<Object Name="CounterVariableName">
  <Property Name="Value">Value</Property>
</Object>
```

### Reset

Сбрасывает значение счетчика до 0.

```xml
<Object Name="CounterVariableName">
  <Property Name="Reset" />
</Object>
```

### ValueChanged <a href="#set_value_changed" id="set_value_changed"></a>

Задает признак изменения значения объекта Variable.

Ожидается логическое значение.

```xml
<Object Name="CounterVariableName">
  <Property Name="ValueChanged">False</Property>
</Object>
```

### Refresh

Обновляет значение объекта Variable.

```xml
<Object Name="CounterVariableName">
  <Property Name="Refresh" />
</Object>
```
