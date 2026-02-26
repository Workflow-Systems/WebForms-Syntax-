# ColumnNumericBox

## Шаблон DatabaseTableColumnNumericBox <a href="#template_databasetable" id="template_databasetable"></a>

Перечень всех возможных тэгов столбца:

```xml
<Column Name="" Type="DatabaseTableColumnNumericBox" Assembly="DatabaseTableColumnControls" >
  <!--Тэги, общие для всех типов столбцов-->
  <Title></Title> 
  <Width></Width>
  <DisplayIndex></DisplayIndex>
  <WrapMode Value="" />
  <Alignment Value="" />
  <HeaderAlignment Value="" />
  <AutoSizeMode Value="" />
  <HeaderBackColor></HeaderBackColor>
  <BackColor></BackColor>
  <ForeColor></ForeColor>
  <Visible></Visible>
  <Hint></Hint>
  <DataType DataType="" />
  <Substitution SourceColumn="">
    <DataConnection SourceDataConnection="">
      <Fields>
        <Field Name="" />
        <Field Name="" />
      </Fields>
    </DataConnection>
  </Substitution>
  <Filter AutoFill="" FilterNullValue=""></Filter>
  <DefaultNewRowValue></DefaultNewRowValue>
  <AutoFill Type="" />
  <Calculate>
    <Expression></Expression>
    <Items>
      <Item></Item>
      <Item></Item>
    </Items>
  </Calculate>
  <!--Тэги, специфичные для DatabaseTableColumnNumericBox-->
  <Maximum Value="" />
  <Minimum Value="" />
  <DecimalPlaces Value="" />
  <Height Value="" />
</Column>
```

{% hint style="info" %}
Тэги, общие для всех типов столбцов описаны в статье [Column](./).
{% endhint %}

## Тэги, специфичные для столбцов типа DatabaseTableColumnNumericBox <a href="#column_numeric_box_tags" id="column_numeric_box_tags"></a>

### Maximum <a href="#column_increment" id="column_increment"></a>

Максимальное допустимое число для ввода.&#x20;

Необязательный тэг. Значение тэга `<Maximum>`: не ожидается.&#x20;

Если тэг `<Maximum>` отсутствует, то для атрибута `Value` используется значение 100.

```xml
<Maximum Value="100" />
```

#### Атрибуты тэга `<Maximum>` <a href="#attributes_tag_column_maximum" id="attributes_tag_column_maximum"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Value</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается числовое значение.</p></td></tr></tbody></table>

### Minimum <a href="#column_minimum" id="column_minimum"></a>

Минимальное допустимое число для ввода.

Необязательный тэг. Значение тэга `<Minimum>`: не ожидается.

Если тэг `<Minimum>` отсутствует, то для атрибута `Value` используется значение 0.

```xml
<Minimum Value="0" />
```

#### Атрибуты тэга `<Minimum>` <a href="#attributes_tag_column_minimum" id="attributes_tag_column_minimum"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Value</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается числовое значение.</p></td></tr></tbody></table>

### DecimalPlaces <a href="#column_decimal_places" id="column_decimal_places"></a>

Количество знаков дробной части числа.&#x20;

Необязательный тэг. Значение тэга `<DecimalPlaces>`: не ожидается.&#x20;

Если тэг `<DecimalPlaces>` отсутствует, то для атрибута `Value` используется значение 0.

```xml
<DecimalPlaces Value="0" />
```

{% hint style="info" %}
Этот тэг также устанавливает шаг инкремента `NumericBox`.

Если для DecimalPlaces установлено значение 2, то шаг будет равен 0.01.

Если для DecimalPlaces установлено значение 0, то шаг будет равен 1.

Если для DecimalPlaces установлено значение 1, то шаг будет равен 0.1.
{% endhint %}

#### Атрибуты тэга `<DecimalPlaces>` <a href="#attributes_tag_column_decimal_places" id="attributes_tag_column_decimal_places"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Value</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается целочисленное значение.</p></td></tr></tbody></table>

### Height <a href="#column_minimum" id="column_minimum"></a>

Высота поля для ввода внутри ячейки таблицы.

Необязательный тэг. Значение тэга `<Height>`: не ожидается.

Если тэг `<Height>` отсутствует, то поле для ввода будет растянуто на всю высоту ячейки.

```xml
<Height Value="25" />
```

#### Атрибуты тэга `<Minimum>` <a href="#attributes_tag_column_minimum" id="attributes_tag_column_minimum"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Value</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается числовое значение.</p></td></tr></tbody></table>
