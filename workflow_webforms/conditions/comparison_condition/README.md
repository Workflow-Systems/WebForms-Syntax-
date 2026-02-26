---
description: Условие; сравнение значений по определенному признаку.
---

# ComparisonCondition

## Описание Condition <a href="#description_comparison_condition" id="description_comparison_condition"></a>

```xml
<Condition Name="ConditionName" Type="ConditionType" Assembly="ConditionAssembly">
  <!--Тэги, общие для всех условий-->
  <!--Тэги, специфичные для ComparisonCondition-->
</Condition>
```

## Тэги, специфичные для ComparisonCondition <a href="#tags_comparison_condition" id="tags_comparison_condition"></a>

### Items <a href="#items" id="items"></a>

Значения для сравнения.

Необязательный тэг. Значение тэга `<Items>`: список тэгов [`<Item>`](./#items_item).

Если тэг `<Items>` отсутствует, то условие всегда будет иметь значение False.

```xml
<Items>
  <Item>Value1</Item>
  <Item>Value2</Item>
</Items>
```

#### Тэг `<Item>` <a href="#items_item" id="items_item"></a>

Значение для сравнения.

Необязательный тэг. Значение тэга `<Item>`: любое значение.

### DataType <a href="#data_type" id="data_type"></a>

Тип, к которому будут приводиться значения для сравнения.

Необязательный тэг. Значение тэга `<DataType>`: не ожидается.

Если тэг `<DataType>` отсутствует, то для атрибута `Type` используется значение StringDataType.

```xml
<DataType Type="DataTypeName" />
```

#### Атрибуты тэга `<DataType>` <a href="#attributes_tag_data_type" id="attributes_tag_data_type"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="514.3333333333333"></th></tr></thead><tbody><tr><td align="center">Type</td><td><p>Тип данных.</p><p></p><p>Обязательный атрибут. Значение атрибута <code>Type</code>: название одного из <a href="/broken/pages/-MaRtBVKMO4VR0KCghVx">типов данных</a>.</p></td></tr></tbody></table>

### Comparison <a href="#comparison" id="comparison"></a>

Настройки вычисления значения условия, если в качестве значения хотя бы одного из операндов выступает массив или матрица.

Необязательный тэг. Значение тэга `<Comparison>`: не ожидается.

Если тэг `<Comparison>` отсутствует, то для атрибута `Type` используется значение Inner.

Если один из операндов условия - массив или матрица, то для сравнения должен быть выбран базовый элемент из списка [`<Items>`](./#items).

Размерность (общее количество элементов массива или матрицы) базового элемента определяет количество сравнений в рамках данного условия.

Если операнд - матрица, то она в рамках условия трансформируется по столбцам в линейный массив.

```xml
<Comparison Type="Inner" Order="1" />
```

#### Пример <a href="#example_comparison" id="example_comparison"></a>

Если в качестве первого [`<Item>`](./#items_item) задан массив размерностью 3, а в качестве второго [`<Item>`](./#items_item) - массив размерностью 2, базовым элементом для сравнения задан первый [`<Item>`](./#items_item), то в рамках данного условия будут происходить следующие внутренние сравнения:

1. Item1\[1] = Item2\[1]
2. Item1\[2] = Item2\[2]
3. Item1\[3] = NULL

Если в качестве первого [`<Item>`](./#items_item) задана массив размерностью 3, а в качестве второго [`<Item>`](./#items_item) - матрица размерностью 2x2, базовым элементом для сравнения задан первый [`<Item>`](./#items_item), то в рамках данного условия будут происходить следующие внутренние сравнения:

1. Item1\[1] = Item2\[1,1]
2. Item1\[2] = Item2\[2,1]
3. Item1\[3] = Item2\[1,2]

#### Атрибуты тэга `<Comparison>` <a href="#attributes_tag_comparison" id="attributes_tag_comparison"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="514.3333333333333"></th></tr></thead><tbody><tr><td align="center">Type</td><td><p><a href="./#comparison_types">Способ определения</a> базового элемента при сравнении.</p><p></p><p>Необязательный атрибут. Значение атрибута <code>Type</code>: название одного из способов определения базового элемента при сравнении.</p></td></tr><tr><td align="center">Order</td><td><p>Индекс базового элемента в списке <a href="./#items"><code>&#x3C;Items></code></a>.</p><p></p><p>Необязательный атрибут. Ожидается целочисленное значение (от 1 и до количества элементов в списке <a href="./#items"><code>&#x3C;Items></code></a>).</p></td></tr></tbody></table>

#### Способы определения базового элемента при сравнении <a href="#comparison_types" id="comparison_types"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="514.3333333333333"></th></tr></thead><tbody><tr><td align="center">Inner</td><td>Базовым элементом является элемент с наименьшей размерностью</td></tr><tr><td align="center">Outer</td><td>Базовым элементом является элемент с наибольшей размерностью</td></tr><tr><td align="center">ByOrder</td><td>Базовым элементом является элемент с определенным индексом (начинается с 1), соответствующим его расположению в списке <a href="./#items"><code>&#x3C;Items></code></a></td></tr></tbody></table>

### Satisfy <a href="#satisfy" id="satisfy"></a>

Настройки вычисления значения условия, если в качестве значения хотя бы одного из операндов выступает массив или матрица.

Необязательный тэг. Значение тэга `<Satisfy>`: не ожидается.

Если тэг `<Satisfy>` отсутствует, то для атрибутов `MinCount` и `MaxCount` используются значения 1 и All соответственно.

```xml
<Satisfy MinCount="1" MaxCount="All" />
```

#### Атрибуты тэга `<Satisfy>` <a href="#attributes_tag_satisfy" id="attributes_tag_satisfy"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="514.3333333333333"></th></tr></thead><tbody><tr><td align="center">MinCount</td><td><p>Минимальное количество сравнений, удовлетворяющих условию, в соответствии с настройками <a href="./#comparison"><code>&#x3C;Comparison></code></a>.</p><p></p><p>Необязательный атрибут. Ожидается целочисленное значение (от 0) или ключевое слово All.</p></td></tr><tr><td align="center">MaxCount</td><td><p>Максимальное количество сравнений, удовлетворяющих условию, в соответствии с настройками <a href="./#comparison"><code>&#x3C;Comparison></code></a>.</p><p></p><p>Необязательный атрибут. Ожидается целочисленное значение (от 0) или ключевое слово All.</p></td></tr></tbody></table>
