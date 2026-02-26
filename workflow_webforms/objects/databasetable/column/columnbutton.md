# ColumnButtonBox

## Шаблон DatabaseTableColumnButtonBox <a href="#template_databasetable" id="template_databasetable"></a>

Перечень всех возможных тэгов столбца:

```xml
<Column Name="" Type="DatabaseTableColumnButtonBox" Assembly="DatabaseTableColumnControls" >
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
  <!--Тэги, специфичные для DatabaseTableColumnButtonBox-->
  <Commands StopOnError="" Lock="">
    <Command Name="" />
    <If>
      <When></When>
      <Then StopOnError="" Lock="">
        <Command Name="" />
      </Then>
      <ElseIf>
        <When></When>
        <Then StopOnError="" Lock="">
          <Command Name="">
            <Input Name="" />
            <Input Name="" />
          </Command>
        </Then>
      </ElseIf>
      <Else StopOnError="" Lock="">
        <Command Name="" />
      </Else>
    </If>
  </Commands>
  <Icon Value="" />
  <Text Value="" />
  <BorderColor Value="" />
  <BorderSize Value="" />
  <BackColor Value="" />
  <MouseOverColor Value="" />
  <MouseDownColor Value="" />
  <IconColor Value="" />
  <Height Value="" />
</Column>
```

{% hint style="info" %}
Тэги, общие для всех типов столбцов описаны в статье [Column](./).
{% endhint %}

## Тэги, специфичные для столбцов типа DatabaseTableColumnButtonBox <a href="#column_numeric_box_tags" id="column_numeric_box_tags"></a>

### Commands

Список команд, которые будут выполнены при нажатии на кнопку.

Необязательный тэг. В качестве значения тэга ожидается список тэгов [`<Command>`](columnbutton.md#teg-less-than-command-greater-than) и/или конструкций [`<If>`](../../../values/if.md).

```xml
<Commands StopOnError="True"  Lock="">
  <Command Name="CommandName1" />
  <If>
    <When></When>
    <Then StopOnError="True" Lock="">
      <Command Name="CommandName2">
        <Input Name="InputName1">input 1</Input>
        <Input Name="InputName2">input 2</Input>
      </Command>
    </Then>
    <ElseIf>
      <When></When>
      <Then StopOnError="True" Lock="">
        <Command Name="CommandName3" />
      </Then>
    </ElseIf>
    <Else StopOnError="True" Lock="">
      <Command Name="CommandName4" />
    </Else>
  </If>
</Commands>
```

#### Атрибуты тэга `<Commands>`

<table data-header-hidden><thead><tr><th width="150" align="center"></th><th width="532.4285714285713"></th></tr></thead><tbody><tr><td align="center">StopOnError</td><td><p>Признак, определяющий, будет ли остановлено выполнение команд, если при выполнении очередной произойдет ошибка.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>По умолчанию используется значение True.</p></td></tr><tr><td align="center">Lock</td><td><p>Признак, определяющий, будет ли блокироваться форма при выполнении команд.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>По умолчанию используется значение False.</p></td></tr></tbody></table>

#### Тэг `<Command>`

Обращение к команде по имени для ее выполнения.

Необязательный тэг. В качестве значения тэга ожидается список тэгов [`<Input>`](../../../values/input.md).

```xml
<!--Вариант 1-->
<Command Name="CommandName1" />

<!--Вариант 2-->
<Command Name="CommandName2">
  <Input Name="InputName1">input 1</Input>
  <Input Name="InputName2">input 2</Input>
</Command>
```

### Height <a href="#column_minimum" id="column_minimum"></a>

Высота кнопки внутри ячейки таблицы.

Необязательный тэг. Значение тэга `<Height>`: не ожидается.

Если тэг `<Height>` отсутствует, то поле для ввода будет растянуто на всю высоту ячейки.

```xml
<Height Value="25" />
```

#### Атрибуты тэга `<Minimum>` <a href="#attributes_tag_column_minimum" id="attributes_tag_column_minimum"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Value</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается числовое значение.</p></td></tr></tbody></table>

### Icon

Иконка, которая будет расположена на кнопке.

Необязательный тэг. Значение тэга `<Icon>`: не ожидается.

Если тэг `<Icon>` отсутствует, то иконка на кнопке будет отсутствовать.

```xml
<Icon Value="remove" />
```

#### Атрибуты тэга `<Icon>` <a href="#attributes_tag_column_minimum" id="attributes_tag_column_minimum"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Value</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается название одного из типов иконок Google. Список иконок доступен по <a href="https://www.w3schools.com/icons/icons_reference.asp">ссылке</a>.</p></td></tr></tbody></table>

### Text

Текст на кнопке.

Необязательный тэг. Значение тэга `<Text>`: не ожидается.

Если тэг `<Text>` отсутствует, то текст на кнопке будет отсутствовать.

```xml
<Text Value="Add to cart" />
```

#### Атрибуты тэга `<Text>` <a href="#attributes_tag_column_minimum" id="attributes_tag_column_minimum"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Value</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается текстовое значение.</p></td></tr></tbody></table>

### BorderColor

Цвет границы кнопки.

Необязательный тэг. Значение тэга `<BorderColor>`: не ожидается.

Если тэг `<BorderColor>` отсутствует, то будет использован светло-серый цвет.

```xml
<BorderColor Value="Red" />
```

#### Атрибуты тэга `<BorderColor>` <a href="#attributes_tag_column_minimum" id="attributes_tag_column_minimum"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Value</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается имя одного из цветов, описанных в форме или описание цвета в формате HTML (#rrggbb).</p></td></tr></tbody></table>

### BorderSize

Толщина границы кнопки (в пикселях).

Необязательный тэг. Значение тэга `<BorderSize>`: не ожидается.

Если тэг `<BorderSize>` отсутствует, то толщина будет установлена в 1 пиксель.

```xml
<BorderSize Value="0" />
```

#### Атрибуты тэга `<BorderSize>` <a href="#attributes_tag_column_minimum" id="attributes_tag_column_minimum"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Value</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается целочисленное значение.</p></td></tr></tbody></table>

### BackColor

Цвет фона кнопки.

Необязательный тэг. Значение тэга `<BorderColor>`: не ожидается.

Если тэг `<BackColor>` отсутствует, то будет использован белый цвет.

```xml
<BackColor Value="Green" />
```

#### Атрибуты тэга `<BackColor>` <a href="#attributes_tag_column_minimum" id="attributes_tag_column_minimum"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Value</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается имя одного из цветов, описанных в форме или описание цвета в формате HTML (#rrggbb).</p></td></tr></tbody></table>

### MouseOverColor

Цвет фона кнопки при наведении мыши.

Необязательный тэг. Значение тэга `<MouseOverColor>`: не ожидается.

Если тэг `<MouseOverColor>` отсутствует, то будет использоваться цвет фона кнопки.

```xml
<MouseOverColor Value="LightGreen" />
```

#### Атрибуты тэга `<MouseOverColor>` <a href="#attributes_tag_column_minimum" id="attributes_tag_column_minimum"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Value</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается имя одного из цветов, описанных в форме или описание цвета в формате HTML (#rrggbb).</p></td></tr></tbody></table>

### MouseDownColor

Цвет нажатой кнопки.

Необязательный тэг. Значение тэга `<MouseDownColor>`: не ожидается.

Если тэг `<MouseDownColor>` отсутствует, то будет использоваться цвет фона кнопки.

```xml
<MouseOverColor Value="Cyan" />
```

#### Атрибуты тэга `<MouseOverColor>` <a href="#attributes_tag_column_minimum" id="attributes_tag_column_minimum"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Value</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается имя одного из цветов, описанных в форме или описание цвета в формате HTML (#rrggbb).</p></td></tr></tbody></table>

### IconColor

Цвет иконки кнопки.

Необязательный тэг. Значение тэга `<IconColor>`: не ожидается.

Если тэг `<IconColor>` отсутствует, то цвет иконки будет установлен автоматически.

```xml
<IconColor Value="Black" />
```

#### Атрибуты тэга `<IconColor>` <a href="#attributes_tag_column_minimum" id="attributes_tag_column_minimum"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Value</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается имя одного из цветов, описанных в форме или описание цвета в формате HTML (#rrggbb).</p></td></tr></tbody></table>
