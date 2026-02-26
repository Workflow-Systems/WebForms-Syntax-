---
description: Графический объект; таблица, которая работает с данными базы.
---

# DatabaseTable

## Шаблон DatabaseTable <a href="#template_databasetable" id="template_databasetable"></a>

Перечень всех возможных тэгов объекта:

```xml
<MyObject Name="" Type="DatabaseTable" Assembly="ComplexControls" ChangeForm="">
  <!--Тэги, общие для всех графических объектов-->
  <Top></Top>
  <Left></Left>
  <Height></Height>
  <MaxHeight></MaxHeight>
  <Width></Width>
  <FontStyle></FontStyle>
  <ForeColor></ForeColor>
  <BackColor></BackColor>
  <Enabled></Enabled>
  <Visible></Visible>
  <Hint></Hint>
  <Change User="" Source="" ValueSet="" />
  <!--Тэги, специфичные для DatabaseTable-->
  <RowHeight Value="" />
  <ColumnHeadersHeight Value="" />
  <ColumnHeadersVisible Value="" />
  <BackgroundColor Value="" />
  <CellBorderStyle Value="" />
  <HideSelection Value="" />
  <SelectionColor Name="" FadingRatio="" />
  <MultiSelect Value="" />
  <ScrollBars Value="" />
  <AutoSizeColumnsMode Value="" />
  <ColumnHeadersAlignment Value="" />
  <ShowCellHints Value="" />
  <Formatting>
    <BackColor Name="">
      <Columns>
        <Column Name="" />
        <Column Name="" />
      </Columns>
      <Expression></Expression>
      <Items>
        <Item></Item>
        <Item></Item>
      </Items>
    </BackColor>
    <BackColor>
      <Color></Color>
      <Columns>
        <Column Name="" />
        <Column Name="" />
      </Columns>
      <Expression></Expression>
      <Items>
        <Item></Item>
        <Item></Item>
      </Items>
    </BackColor>
    <BackColor>
      <ColorFromColumnValue></ColorFromColumnValue>
      <Columns>
        <Column Name="" />
        <Column Name="" />
      </Columns>
      <Expression></Expression>
      <Items>
        <Item></Item>
        <Item></Item>
      </Items>
    </BackColor>
    <ForeColor Name="">
      <Columns>
        <Column Name="" />
        <Column Name="" />
      </Columns>
      <Expression></Expression>
      <Items>
        <Item></Item>
        <Item></Item>
      </Items>
    </ForeColor>
    <ForeColor>
      <Color></Color>
      <Columns>
        <Column Name="" />
        <Column Name="" />
      </Columns>
      <Expression></Expression>
      <Items>
        <Item></Item>
        <Item></Item>
      </Items>
    </ForeColor>
    <ForeColor>
      <ColorFromColumnValue></ColorFromColumnValue>
      <Columns>
        <Column Name="" />
        <Column Name="" />
      </Columns>
      <Expression></Expression>
      <Items>
        <Item></Item>
        <Item></Item>
      </Items>
    </ForeColor>
    <FontStyle Name="">
      <Columns>
        <Column Name="" />
        <Column Name="" />
      </Columns>
      <Expression></Expression>
      <Items>
        <Item></Item>
        <Item></Item>
      </Items>
    </FontStyle>
  </Formatting>
  <SourceDataConnection Name="" Query=""/>
  <Columns>
    <Column Name="" Type="DatabaseTableColumnTextBox" Assembly="DatabaseTableColumnControls" >
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
    </Column>
    <Column Name="" Type="DatabaseTableColumnImageBox" Assembly="DatabaseTableColumnControls" >
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
    </Column>
    <Column Name="" Type="DatabaseTableColumnButtonBox" Assembly="DatabaseTableColumnControls" >
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
    <Column Name="" Type="DatabaseTableColumnNumericBox" Assembly="DatabaseTableColumnControls" >
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
      <Height Value="" />
      <Maximum Value="" />
      <Minimum Value="" />
      <DecimalPlaces Value="" />
    </Column>
  </Columns>
</MyObject>
```

## Описание DatabaseTable <a href="#description_databasetable" id="description_databasetable"></a>

```xml
<MyObject Name="DatabaseTableName" Type="DatabaseTable" Assembly="ComplexControls">
  <!--Тэги, общие для всех графических объектов-->
  <!--Тэги, специфичные для DatabaseTable-->
</MyObject>
```

DatabaseTable не имеет значения.

## Тэги, общие для всех графических объектов <a href="#common_tags" id="common_tags"></a>

### Width <a href="#width" id="width"></a>

Ширина таблицы.

Необязательный тэг. Ожидается целочисленное значение.

Если тэг `<Width>` отсутствует, то ширина таблицы определяется шириной всех ее видимых столбцов.

```xml
<Width>300</Width>
```

## Тэги, специфичные для DatabaseTable <a href="#tags_databasetable" id="tags_databasetable"></a>

### MaxHeight <a href="#row_height" id="row_height"></a>

Максимально допустимая высота таблицы.

Если общая высота всех отображаемых строк таблицы будет меньше значения, указанного в `<MaxHeight>`, то реальная высота объекта будет уменьшена, чтобы в точности соответствовать отображаемым строкам. В остальных случаях тэг `<MaxHeight>` работает как тэг `<Height>`.

Необязательный тэг. Ожидается целочисленное значение.

Игнорируется при наличии тэга `<Height>`.

```xml
<MaxHeight>500</MaxHeight>
```

### RowHeight <a href="#row_height" id="row_height"></a>

Высота строк с данными в таблице.

Необязательный тэг. Значение тэга `<RowHeight>`: не ожидается.

Если тэг `<RowHeight>` отсутствует, то высота строк определяется содержимым ячеек.

```xml
<RowHeight Value="22" />
```

#### Атрибуты тэга `<RowHeight>` <a href="#attributes_tag_row_height" id="attributes_tag_row_height"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Value</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается целочисленное значение.</p></td></tr></tbody></table>

### ColumnHeadersHeight <a href="#column_headers_height" id="column_headers_height"></a>

Высота "шапки" таблицы.

Необязательный тэг. Значение тэга `<ColumnHeadersHeight>`: не ожидается.

Если тэг `<ColumnHeadersHeight>` отсутствует, то высота "шапки" определяется содержимым ячеек.

```xml
<ColumnHeadersHeight Value="21" />
```

#### Атрибуты тэга `<ColumnHeadersHeight>` <a href="#attributes_tag_column_headers_height" id="attributes_tag_column_headers_height"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Value</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается целочисленное значение.</p></td></tr></tbody></table>

### ColumnHeadersVisible <a href="#column_headers_visible" id="column_headers_visible"></a>

Признак, определяющий, показывать или нет "шапку" таблицы.

Необязательный тэг. Значение тэга `<ColumnHeadersVisible>`: не ожидается.

Если тэг `<ColumnHeadersVisible>` отсутствует, то для атрибута `Value` используется значение True.

```xml
<ColumnHeadersVisible Value="True" />
```

#### Атрибуты тэга `<ColumnHeadersVisible>` <a href="#attributes_tag_column_headers_visible" id="attributes_tag_column_headers_visible"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Value</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается логическое значение.</p></td></tr></tbody></table>

### BackgroundColor <a href="#background_color" id="background_color"></a>

Цвет фона таблицы.

Необязательный тэг. Значение тэга `<BackgroundColor>`: не ожидается.

Если тэг `<BackgroundColor>` отсутствует, то для атрибута `Value` используется стандартное значение .NET.

```xml
<BackgroundColor Value="BackgroundColor" />
```

#### Атрибуты тэга `<BackgroundColor>` <a href="#attributes_tag_background_color" id="attributes_tag_background_color"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Value</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается имя одного из цветов, описанных на форме или описание цвета в формате HTML (#rrggbb).</p></td></tr></tbody></table>

<table data-header-hidden><thead><tr><th align="center"></th><th width="460.3333333333333"></th></tr></thead><tbody><tr><td align="center">None</td><td>Нет границ</td></tr><tr><td align="center">FixedSingle</td><td>Одиночная плоская</td></tr><tr><td align="center">Fixed3D</td><td>Одиночная объемная</td></tr></tbody></table>

### CellBorderStyle <a href="#cell_border_style" id="cell_border_style"></a>

Название стиля границ ячеек в таблице.

Необязательный тэг. Значение тэга `<CellBorderStyle>`: не ожидается.

Если тэг `<CellBorderStyle>` отсутствует, то для атрибута `Value` используется значение Single.

```xml
<CellBorderStyle Value="Single" />
```

#### Атрибуты тэга `<CellBorderStyle>` <a href="#attributes_tag_cell_border_style" id="attributes_tag_cell_border_style"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Value</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается название одного из <a href="./#cell_border_style_types">стилей границ ячеек</a> в таблице.</p></td></tr></tbody></table>

#### Стили границ ячеек <a href="#cell_border_style_types" id="cell_border_style_types"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="460.3333333333333"></th></tr></thead><tbody><tr><td align="center">Single</td><td>Одинарная граница</td></tr><tr><td align="center">None</td><td>Отсутствие границ</td></tr><tr><td align="center">SingleVertical</td><td>Вертикальная одинарная граница</td></tr><tr><td align="center">SingleHorizontal</td><td>Горизонтальная одинарная граница</td></tr></tbody></table>

### HideSelection <a href="#hide_selection" id="hide_selection"></a>

Признак видимости выделения в таблице.

Необязательный тэг. Значение тэга `<HideSelection>`: не ожидается.

Если тэг `<HideSelection>` отсутствует, то для атрибута `Value` используется значение False.

```xml
<HideSelection Value="False" />
```

#### Атрибуты тэга `<HideSelection>` <a href="#attributes_tag_hide_selection" id="attributes_tag_hide_selection"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Value</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается логическое значение.</p></td></tr></tbody></table>

Замечание. Невидимость выделения задается посредством присвоения внутренним свойствам `<SelectionForeColor>` и `<SelectionBackColor>` значений из свойств `<ForeColor>` и `<BackColor>`, либо при задании значения True для set-проперти HideSelection.

### SelectionColor <a href="#selection_color" id="selection_color"></a>

Настройки цвета выделения в таблице.

Необязательный тэг. Значение тэга `<SelectionColor>`: не ожидается.

Если тэг `<SelectionColor>` отсутствует, то используется системный цвет выделения.

```xml
<SelectionColor Name="LightBlue" FadingRatio="0.55" />
```

#### Атрибуты тэга `<SelectionColor>` <a href="#attributes_tag_selection_color" id="attributes_tag_selection_color"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Имя цвета или описание цвета в формате HTML (#rrggbb).</p><p></p><p>Обязательный атрибут. Ожидается имя одного из цветов, описанных на форме.</p></td></tr><tr><td align="center">FadingRatio</td><td><p>Степень остатка цвета фона при выделении (0 - минимальный остаток, выделенная строка полностью закрашена цветом; 1 - минимальный остаток, выделенная строка не закрашена вовсе).</p><p></p><p>Необязательный атрибут. Ожидается числовое значение от 0 до 1.</p><p></p><p>Если атрибут <code>FadingRatio</code> не задан, то используется значение 0,55.</p></td></tr></tbody></table>

### MultiSelect <a href="#multi_select" id="multi_select"></a>

Признак, определяющий, можно ли выделить в таблице более одной строки одновременно.

Необязательный тэг. Значение тэга `<MultiSelect>`: не ожидается.

Если тэг `<MultiSelect>` отсутствует, то для атрибута `Value` используется значение False.

```xml
<MultiSelect Value="False" />
```

#### Атрибуты тэга `<MultiSelect>` <a href="#attributes_tag_multi_select" id="attributes_tag_multi_select"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Value</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается логическое значение.</p></td></tr></tbody></table>

### ScrollBars <a href="#scroll_bars" id="scroll_bars"></a>

Признак, определяющий, тип полос прокрутки в таблице.

Необязательный тэг. Значение тэга `<ScrollBars>`: не ожидается.

Если тэг `<ScrollBars>` отсутствует, то для атрибута `Value` используется значение Auto.

```xml
<ScrollBars Value="None" />
```

#### Атрибуты тэга `<ScrollBars>` <a href="#attributes_tag_scroll_bars" id="attributes_tag_scroll_bars"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Value</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается название одного из <a href="./#scroll_bars_types">типов полос прокрутки</a> в таблице.</p></td></tr></tbody></table>

#### Типы полос прокрутки <a href="#scroll_bars_types" id="scroll_bars_types"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="460.3333333333333"></th></tr></thead><tbody><tr><td align="center">Auto</td><td>Автоматические полосы прокрутки</td></tr><tr><td align="center">Both</td><td>Разрешены вертикальная и горизонтальная полосы прокрутки</td></tr><tr><td align="center">Vertical</td><td>Только вертикальная полоса прокрутки</td></tr><tr><td align="center">Horizontal</td><td>Только горизонтальная полоса прокрутки</td></tr><tr><td align="center">None</td><td>Нет полос прокрутки</td></tr></tbody></table>

### AutoSizeColumnsMode <a href="#auto_size_columns_mode" id="auto_size_columns_mode"></a>

Название типа автоматического изменения ширины столбцов таблицы.

Необязательный тэг. Значение тэга `<AutoSizeColumnsMode>`: не ожидается.

Если тэг `<AutoSizeColumnsMode>` отсутствует, то для атрибута `Value` используется значение None.

```xml
<AutoSizeColumnsMode Value="None" />
```

#### Атрибуты тэга `<AutoSizeColumnsMode>` <a href="#attributes_tag_auto_size_columns_mode" id="attributes_tag_auto_size_columns_mode"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Value</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается название одного из <a href="./#auto_size_columns_mode_types">типов автоматического изменения ширины столбцов таблицы</a>.</p></td></tr></tbody></table>

#### Типы автоматического изменения ширины столбцов таблицы <a href="#auto_size_columns_mode_types" id="auto_size_columns_mode_types"></a>

<table data-header-hidden><thead><tr><th width="286.33197012750384" align="center"></th><th width="460.3333333333333"></th></tr></thead><tbody><tr><td align="center">None</td><td>Пропорциональное автоматическое изменение ширины столбцов относительно ширины таблицы</td></tr><tr><td align="center">Fill</td><td>Ширина столбцов изменяется так, чтобы точно заполнить ширину всей отображаемой области таблицы, с учетом наличия или отсутствия полосы горизонтальной прокрутки</td></tr></tbody></table>

### ColumnHeadersAlignment <a href="#column_headers_alignment" id="column_headers_alignment"></a>

Название типа положения содержимого заголовка столбца таблицы.

Необязательный тэг. Значение тэга `<ColumnHeadersAlignment>`: не ожидается.

Если тэг `<ColumnHeadersAlignment>` отсутствует, то для атрибута `Value` используется значение NotSet.

```xml
<ColumnHeadersAlignment Value="NotSet" />
```

#### Атрибуты тэга `<ColumnHeadersAlignment>` <a href="#attributes_tag_column_headers_alignment" id="attributes_tag_column_headers_alignment"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Value</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается название одного из <a href="./#column_headers_alignment_types">типов положения содержимого ячейки столбца таблицы</a>.</p></td></tr></tbody></table>

#### Типы положения содержимого ячейки столбца таблицы <a href="#column_headers_alignment_types" id="column_headers_alignment_types"></a>

<table data-header-hidden><thead><tr><th width="286.33197012750384" align="center"></th><th width="460.3333333333333"></th></tr></thead><tbody><tr><td align="center">NotSet</td><td>Не установлено</td></tr><tr><td align="center">TopLeft</td><td>Содержимое выравнивается по верхнему краю в вертикальном направлении и по левому краю ячейки в горизонтальном направлении</td></tr><tr><td align="center">TopCenter</td><td>Содержимое выравнивается по верхнему краю в вертикальном направлении и по центру ячейки</td></tr><tr><td align="center">TopRight</td><td>Содержимое выравнивается по верхнему краю в вертикальном направлении и по правому краю ячейки в горизонтальном направлении</td></tr><tr><td align="center">MiddleLeft</td><td>Содержимое выравнивается вертикально по середине и горизонтально по левому краю ячейки в горизонтальном направлении</td></tr><tr><td align="center">MiddleCenter</td><td>Содержимое выравнивается по вертикальному и горизонтальному центру ячейки</td></tr><tr><td align="center">MiddleRight</td><td>Содержимое выравнивается вертикально по середине и горизонтально по правому краю ячейки в горизонтальном направлении</td></tr><tr><td align="center">BottomLeft</td><td>Содержимое выравнивается по нижнему краю в вертикальном направлении и по левому краю ячейки в горизонтальном направлении</td></tr><tr><td align="center">BottomCenter</td><td>Содержимое выравнивается по нижнему краю в вертикальном направлении и по центру ячейки</td></tr><tr><td align="center">BottomRight</td><td>Содержимое выравнивается по нижнему краю в вертикальном направлении и по правому краю ячейки в горизонтальном направлении</td></tr></tbody></table>

### ShowCellHints <a href="#show_cell_hints" id="show_cell_hints"></a>

Признак, определяющий, будут ли показываться всплывающие подсказки для ячеек таблицы.

Необязательный тэг. Значение тэга `<ShowCellHints>`: не ожидается.

Если тэг `<ShowCellHints>` отсутствует, то для атрибута `Value` используется значение False.

```xml
<ShowCellHints Value="True" />
```

#### Атрибуты тэга `<ShowCellHints>` <a href="#attributes_tag_show_cell_hints" id="attributes_tag_show_cell_hints"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Value</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается логическое значение.</p></td></tr></tbody></table>

### Formatting <a href="#formatting" id="formatting"></a>

Условное форматирование ячеек таблицы на основе значений других ячеек таблицы в этой же строке.

Необязательный тэг. Значение тэга `<Formatting>`: список тэгов [`<BackColor>`](./#formatting_back_color), [`<ForeColor>`](./#formatting_fore_color) и [`<FontStyle>`](./#formatting_font_style).

```xml
<Formatting>
  <BackColor Name="BackColor">
    <Columns>
      <Column Name="ColumnName1" />
      <Column Name="ColumnName2" />
    </Columns>
    <Expression>ColumnName3 > {0} * {1}</Expression>
    <Items>
      <Item>10</Item>
      <Item>20</Item>
    </Items>
  </BackColor>
  <ForeColor Name="ForeColor">
    <Columns>
      <Column Name="ColumnName1" />
      <Column Name="ColumnName2" />
    </Columns>
    <Expression>ColumnName3 > {0} * {1}</Expression>
    <Items>
      <Item>10</Item>
      <Item>20</Item>
    </Items>
  </ForeColor>
  <FontStyle Name="FontStyle">
    <Columns>
      <Column Name="ColumnName1" />
      <Column Name="ColumnName2" />
    </Columns>
    <Expression>ColumnName3 > {0} * {1}</Expression>
    <Items>
      <Item>10</Item>
      <Item>20</Item>
    </Items>
  </FontStyle>
</Formatting>
```

### Тэг `<BackColor>` <a href="#formatting_back_color" id="formatting_back_color"></a>

Условный цвет фона ячейки.

Необязательный тэг. Значение тэга `<BackColor>`: не ожидается.

#### Атрибуты тэга `<BackColor>` <a href="#attributes_tag_formatting_back_color" id="attributes_tag_formatting_back_color"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Значение.</p><p></p><p>Необязательный атрибут. Ожидается имя одного из цветов, описанных на форме или описание цвета в формате HTML (#rrggbb).</p></td></tr></tbody></table>

#### Тэг `<Color>` <a href="#formatting_back_color_color" id="formatting_back_color_color"></a>

Значение.

Необязательный тэг. Ожидается имя одного из цветов, описанных на форме или описание цвета в формате HTML (#rrggbb).

#### Тэг `<ColorFromColumnValue>` <a href="#formatting_back_color_color_from_column_value" id="formatting_back_color_color_from_column_value"></a>

Значение.

Необязательный тэг. Ожидается имя одного из столбцов таблицы, в котором записано название цвета или цвет в формате HTML (#rrggbb).

Значение цвета выбирается в следующем порядке:

1. тэг [`<Color>`](./#formatting_back_color_color);
2. тэг `<ColorFromColumnValue>`;
3. [атрибут](./#attributes_tag_formatting_back_color) `Name`.

#### Тэг `<Columns>` <a href="#formatting_back_color_columns" id="formatting_back_color_columns"></a>

Столбцы таблицы, для которых распространяется условное форматирование ячеек.

Необязательный тэг. Значение тэга `<Columns>`: список тэгов [`<Column>`](./#formatting_back_color_columns_column).

Если тэг `<Columns>` отсутствует, то условное форматирование распространяется на все столбцы таблицы.

#### Тэг `<Column>` <a href="#formatting_back_color_columns_column" id="formatting_back_color_columns_column"></a>

Столбец таблицы, для которого распространяется условное форматирование ячеек.

Необязательный тэг. Значение тэга `<Column>`: не ожидается.

#### Атрибуты тэга `<Column>` <a href="#attributes_tag_formatting_back_color_columns_column" id="attributes_tag_formatting_back_color_columns_column"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается название одного из столбцов таблицы.</p></td></tr></tbody></table>

#### Тэг `<Expression>` <a href="#formatting_back_color_expression" id="formatting_back_color_expression"></a>

Выражение для вычисления, возвращающее логическое значение, на основе которого форматирование будет применено или нет.

Обязательный тэг. Значение тэга `<Expression>`: любое значение.

Выражение для вычисления поддерживает выражения вида "ColumnName", где ColumnName - название одного из столбцов данной таблицы, и выражения вида "{N}" для подстановки значений (N+1)-ого элемента, то есть {0}, {1} и т. д.

Все поддерживаемые в выражении для вычисления конструкции смотрите по ссылке "[http://msdn.microsoft.com/en-us/library/system.data.datacolumn.expression.aspx](http://msdn.microsoft.com/en-us/library/system.data.datacolumn.expression.aspx)".

#### Тэг `<Items>` <a href="#formatting_back_color_items" id="formatting_back_color_items"></a>

Переменные для подстановки в выражение для вычисления.

Необязательный тэг. Значение тэга `<Items>`: список тэгов [`<Item>`](./#formatting_back_color_items_item).

#### Тэг `<Item>` <a href="#formatting_back_color_items_item" id="formatting_back_color_items_item"></a>

Переменная для подстановки в выражение для вычисления.

Необязательный тэг. Значение тэга `<Item>`: любое значение.

### Тэг `<ForeColor>` <a href="#formatting_fore_color" id="formatting_fore_color"></a>

Условный цвет шрифта ячейки.

Необязательный тэг. Значение тэга `<ForeColor>`: не ожидается.

#### Атрибуты тэга `<ForeColor>` <a href="#attributes_tag_formatting_fore_color" id="attributes_tag_formatting_fore_color"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Значение.</p><p></p><p>Необязательный атрибут. Ожидается имя одного из цветов, описанных на форме или описание цвета в формате HTML (#rrggbb).</p></td></tr></tbody></table>

#### Тэг `<Color>` <a href="#formatting_fore_color_color" id="formatting_fore_color_color"></a>

Значение.

Необязательный тэг. Ожидается имя одного из цветов, описанных на форме или описание цвета в формате HTML (#rrggbb).

#### Тэг `<ColorFromColumnValue>` <a href="#formatting_fore_color_color_from_column_value" id="formatting_fore_color_color_from_column_value"></a>

Значение.

Необязательный тэг. Ожидается имя одного из столбцов таблицы, в котором записано название цвета или цвет в формате HTML (#rrggbb).

Значение цвета выбирается в следующем порядке:

1. тэг [`<Color>`](./#formatting_fore_color_color);
2. тэг `<ColorFromColumnValue>`;
3. [атрибут](./#attributes_tag_formatting_fore_color) `Name`.

#### Тэг `<Columns>` <a href="#formatting_fore_color_columns" id="formatting_fore_color_columns"></a>

Столбцы таблицы, для которых распространяется условное форматирование ячеек.

Необязательный тэг. Значение тэга `<Columns>`: список тэгов [`<Column>`](./#formatting_fore_color_columns_column).

Если тэг `<Columns>` отсутствует, то условное форматирование распространяется на все столбцы таблицы.

#### Тэг `<Column>` <a href="#formatting_fore_color_columns_column" id="formatting_fore_color_columns_column"></a>

Столбец таблицы, для которого распространяется условное форматирование ячеек.

Необязательный тэг. Значение тэга `<Column>`: не ожидается.

#### Атрибуты тэга `<Column>` <a href="#attributes_tag_formatting_fore_color_columns_column" id="attributes_tag_formatting_fore_color_columns_column"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается название одного из столбцов таблицы.</p></td></tr></tbody></table>

#### Тэг `<Expression>` <a href="#formatting_fore_color_expression" id="formatting_fore_color_expression"></a>

Выражение для вычисления, возвращающее логическое значение, на основе которого форматирование будет применено или нет.

Обязательный тэг. Значение тэга `<Expression>`: любое значение.

Выражение для вычисления поддерживает выражения вида "ColumnName", где ColumnName - название одного из столбцов данной таблицы, и выражения вида "{N}" для подстановки значений (N+1)-ого элемента, то есть {0}, {1} и т. д.

Все поддерживаемые в выражении для вычисления конструкции смотрите по ссылке "[http://msdn.microsoft.com/en-us/library/system.data.datacolumn.expression.aspx](http://msdn.microsoft.com/en-us/library/system.data.datacolumn.expression.aspx)".

#### Тэг `<Items>` <a href="#formatting_fore_color_items" id="formatting_fore_color_items"></a>

Переменные для подстановки в выражение для вычисления.

Необязательный тэг. Значение тэга `<Items>`: список тэгов [`<Item>`](./#formatting_fore_color_items_item).

#### Тэг `<Item>` <a href="#formatting_fore_color_items_item" id="formatting_fore_color_items_item"></a>

Переменная для подстановки в выражение для вычисления.

Необязательный тэг. Значение тэга `<Item>`: любое значение.

### Тэг `<FontStyle>` <a href="#formatting_font_style" id="formatting_font_style"></a>

Условный стиль шрифта ячейки.

Необязательный тэг. Значение тэга `<FontStyle>`: не ожидается.

#### Атрибуты тэга `<FontStyle>` <a href="#attributes_tag_formatting_font_style" id="attributes_tag_formatting_font_style"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается имя одного из стилей шрифтов, описанных на форме.</p></td></tr></tbody></table>

#### Тэг `<Columns>` <a href="#formatting_font_style_columns" id="formatting_font_style_columns"></a>

Столбцы таблицы, для которых распространяется условное форматирование ячеек.

Необязательный тэг. Значение тэга `<Columns>`: список тэгов [`<Column>`](./#formatting_font_style_columns_column).

Если тэг `<Columns>` отсутствует, то условное форматирование распространяется на все столбцы таблицы.

#### Тэг `<Column>` <a href="#formatting_font_style_columns_column" id="formatting_font_style_columns_column"></a>

Столбец таблицы, для которого распространяется условное форматирование ячеек.

Необязательный тэг. Значение тэга `<Column>`: не ожидается.

#### Атрибуты тэга `<Column>` <a href="#attributes_tag_formatting_font_style_columns_column" id="attributes_tag_formatting_font_style_columns_column"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается название одного из столбцов таблицы.</p></td></tr></tbody></table>

#### Тэг `<Expression>` <a href="#formatting_font_style_expression" id="formatting_font_style_expression"></a>

Выражение для вычисления, возвращающее логическое значение, на основе которого форматирование будет применено или нет.

Обязательный тэг. Значение тэга `<Expression>`: любое значение.

Выражение для вычисления поддерживает выражения вида "ColumnName", где ColumnName - название одного из столбцов данной таблицы, и выражения вида "{N}" для подстановки значений (N+1)-ого элемента, то есть {0}, {1} и т. д.

Все поддерживаемые в выражении для вычисления конструкции смотрите по ссылке "[http://msdn.microsoft.com/en-us/library/system.data.datacolumn.expression.aspx](http://msdn.microsoft.com/en-us/library/system.data.datacolumn.expression.aspx)".

#### Тэг `<Items>` <a href="#formatting_font_style_items" id="formatting_font_style_items"></a>

Переменные для подстановки в выражение для вычисления.

Необязательный тэг. Значение тэга `<Items>`: список тэгов [`<Item>`](./#formatting_font_style_items_item).

#### Тэг `<Item>` <a href="#formatting_font_style_items_item" id="formatting_font_style_items_item"></a>

Переменная для подстановки в выражение для вычисления.

Необязательный тэг. Значение тэга `<Item>`: любое значение.

### SourceDataConnection <a href="#source_data_connection" id="source_data_connection"></a>

Загружающее соединение с данными, данные которого будут размещены в таблице.&#x20;

Необязательный тэг. Значение тэга `<SourceDataConnection>`: не ожидается.

```xml
<SourceDataConnection Name="SourceDataConnection" Query="QueryName"/>
```

#### Атрибуты тэга `<SourceDataConnection>` <a href="#attributes_tag_source_data_connection" id="attributes_tag_source_data_connection"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается имя одного из загружающих соединений с данными, описанных на форме.</p></td></tr><tr><td align="center">Query</td><td><p>Значение.</p><p></p><p>Необязательный атрибут. Ожидается имя одного из запросов загружающего соединения с данными, описанных на форме.</p></td></tr></tbody></table>

### Columns <a href="#columns" id="columns"></a>

Список столбцов таблицы.

Обязательный тэг. Ожидается список тэгов [`<Column>`](/broken/pages/0OeJNldAHKzZM8mcUOgp), содержащих описание столбцов.

```xml
<Columns>
  <Column Name="ColumnName1" Type="DatabaseTableColumnTextBox" Assembly="DatabaseTableColumnControls">
    <!--Тэги, общие для всех столбцов таблицы-->
    <Title></Title>
    <Width></Width>
    <Visible></Visible>
    <MinimumWidth></MinimumWidth>
  </Column>
  <Column Name="ColumnName2" Type="DatabaseTableColumnImageBox" Assembly="DatabaseTableColumnControls">
    <!--Тэги, общие для всех столбцов таблицы-->
    <Title></Title>
    <Width></Width>
    <Visible></Visible>
    <MinimumWidth></MinimumWidth>
  </Column>
  <Column Name="" Type="DatabaseTableColumnButtonBox" Assembly="DatabaseTableColumnControls">
    <!--Тэги, общие для всех столбцов таблицы-->
    <Title></Title>
    <Width></Width>
    <Visible></Visible>
    <MinimumWidth></MinimumWidth>
    <!--Тэги, специфичные для данного типа столбца-->
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
  <Column Name="ColumnName4" Type="DatabaseTableColumnNumericBox" Assembly="DatabaseTableColumnControls">
    <!--Тэги, общие для всех столбцов таблицы-->
    <Title></Title>
    <Width></Width>
    <Visible></Visible>
    <MinimumWidth></MinimumWidth>
    <!--Тэги, специфичные для данного типа столбца-->
    <Height Value="" />
    <Maximum Value="" />
    <Minimum Value="" />
    <DecimalPlaces Value="" />
  </Column>
</Columns>
```

Колонки таблицы могут быть одно из доступных типов:

* [DatabaseTableColumnTextBox](column/columntext.md) - используется для отображения данных в виде текста;
* [DatabaseTableColumnImageBox](column/columnimage.md) - используется для отображения изображений;
* [DatabaseTableColumnButtonBox](column/columnbutton.md) - используется для отображения отображения кнопки, по нажатию на которую происходит выполнение команд;
* [DatabaseTableColumnNumericBox](column/columnnumeric.md) - используется для отображения числовых значений и предоставляет пользователю возможностью задавать значение через NumericBox.

## Get-проперти для получения свойств <a href="#get_property_databasetable" id="get_property_databasetable"></a>

### MaxHeight <a href="#get_row_height" id="get_row_height"></a>

Возвращает максимально допустимую высоту таблицы.

```xml
<Object Name="DatabaseTableName">
  <Property Name="MaxHeight" />
</Object>
```

### RowHeight <a href="#get_row_height" id="get_row_height"></a>

Возвращает высоту строк с данными в таблице.

```xml
<Object Name="DatabaseTableName">
  <Property Name="RowHeight" />
</Object>
```

### ColumnHeadersHeight <a href="#get_column_headers_height" id="get_column_headers_height"></a>

Возвращает высоту "шапки" таблицы.

```xml
<Object Name="DatabaseTableName">
  <Property Name="ColumnHeadersHeight" />
</Object>
```

### ColumnHeadersVisible <a href="#get_column_headers_visible" id="get_column_headers_visible"></a>

Возвращает признак, определяющий, показывать или нет "шапку" таблицы.

```xml
<Object Name="DatabaseTableName">
  <Property Name="ColumnHeadersVisible" />
</Object>
```

### BackgroundColor <a href="#get_background_color" id="get_background_color"></a>

Возвращает имя цвета фона таблицы.

```xml
<Object Name="DatabaseTableName">
  <Property Name="BackgroundColor" />
</Object>
```

### CellBorderStyle <a href="#get_cell_border_style" id="get_cell_border_style"></a>

Возвращает название стиля границ ячеек в таблице.

```xml
<Object Name="DatabaseTableName">
  <Property Name="CellBorderStyle" />
</Object>
```

### HideSelection <a href="#get_hide_selection" id="get_hide_selection"></a>

Возвращает признак видимости выделения в таблице.

```xml
<Object Name="DatabaseTableName">
  <Property Name="HideSelection" />
</Object>
```

### MultiSelect <a href="#get_multi_select" id="get_multi_select"></a>

Возвращает признак, определяющий, можно ли выделить в таблице более одной строки одновременно.

```xml
<Object Name="DatabaseTableName">
  <Property Name="MultiSelect" />
</Object>
```

### Column <a href="#get_column" id="get_column"></a>

Возвращает линейный массив значений, содержащихся в определенном столбце таблицы.

```xml
<Object Name="DatabaseTableName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter-->
  <Property Name="Column">
    <Parameters>
      <!--Значение тэга Parameter с атрибутом Name, равным ColumnName: ожидается название одного из столбцов таблицы-->
      <Parameter Name="ColumnName">ColumnName</Parameter>
    </Parameters>
  </Property>  
</Object>
```

### ColumnUniqueValues <a href="#get_column_unique_values" id="get_column_unique_values"></a>

Возвращает линейный массив уникальных значений, содержащихся в определенном столбце таблицы.

```xml
<Object Name="DatabaseTableName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter-->
  <Property Name="ColumnUniqueValues">
    <Parameters>
      <!--Значение тэга Parameter с атрибутом Name, равным ColumnName: ожидается название одного из столбцов таблицы-->
      <Parameter Name="ColumnName">ColumnName</Parameter>
    </Parameters>
  </Property>
</Object>
```

### ColumnTitle <a href="#get_column_title" id="get_column_title"></a>

Возвращает название столбца таблицы по имени столбца.

```xml
<Object Name="DatabaseTableName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter-->
  <Property Name="ColumnTitle">
    <Parameters>
      <!--Значение тэга Parameter с атрибутом Name, равным ColumnName: ожидается название одного из столбцов таблицы-->
      <Parameter Name="ColumnName">ColumnName</Parameter>
    </Parameters>
  </Property>
</Object>
```

### ColumnHint <a href="#get_column_hint" id="get_column_hint"></a>

Возвращает текст подсказки, всплывающей на заголовке столбца таблицы, по имени столбца.

```xml
<Object Name="DatabaseTableName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter-->
  <Property Name="ColumnHint">
    <Parameters>
      <!--Значение тэга Parameter с атрибутом Name, равным ColumnName: ожидается название одного из столбцов таблицы-->
      <Parameter Name="ColumnName">ColumnName</Parameter>
    </Parameters>
  </Property>
</Object>
```

### ColumnLeft <a href="#get_column_left" id="get_column_left"></a>

Возвращает координату по горизонтали для определенного столбца таблицы, относительно того объекта, где расположена таблица (без учёта полосы горизонтальной прокрутки).

```xml
<Object Name="DatabaseTableName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter-->
  <Property Name="ColumnLeft">
    <Parameters>
      <!--Значение тэга Parameter с атрибутом Name, равным ColumnName: ожидается название одного из столбцов таблицы-->
      <Parameter Name="ColumnName">ColumnName</Parameter>
    </Parameters>
  </Property>
</Object>
```

### ColumnOffset <a href="#get_column_offset" id="get_column_offset"></a>

Возвращает координату по горизонтали для определенного столбца таблицы, относительно того объекта, где расположена таблица (с учётом положения полосы горизонтальной прокрутки).

```xml
<Object Name="DatabaseTableName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter-->
  <Property Name="ColumnOffset">
    <Parameters>
      <!--Значение тэга Parameter с атрибутом Name, равным ColumnName: ожидается название одного из столбцов таблицы-->
      <Parameter Name="ColumnName">ColumnName</Parameter>
    </Parameters>
  </Property>
</Object>
```

### ColumnVisible <a href="#get_column_visible" id="get_column_visible"></a>

Возвращает видимость столбца.

```xml
<Object Name="DatabaseTableName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter-->
  <Property Name="ColumnVisible">
    <Parameters>
      <!--Значение тэга Parameter с атрибутом Name, равным ColumnName: ожидается название одного из столбцов таблицы-->
      <Parameter Name="ColumnName">ColumnName</Parameter>
    </Parameters>
  </Property>
</Object>
```

### ColumnDisplayIndex <a href="#get_column_display_index" id="get_column_display_index"></a>

Возвращает порядок отображения определенного столбца таблицы.

```xml
<Object Name="DatabaseTableName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter-->
  <Property Name="ColumnDisplayIndex">
    <Parameters>
      <!--Значение тэга Parameter с атрибутом Name, равным ColumnName: ожидается название одного из столбцов таблицы-->
      <Parameter Name="ColumnName">ColumnName</Parameter>
    </Parameters>
  </Property>
</Object>
```

### ColumnWidth <a href="#get_column_width" id="get_column_width"></a>

Возвращает ширину определенного столбца таблицы.

```xml
<Object Name="DatabaseTableName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter-->
  <Property Name="ColumnWidth">
    <Parameters>
      <!--Значение тэга Parameter с атрибутом Name, равным ColumnName: ожидается название одного из столбцов таблицы-->
      <Parameter Name="ColumnName">ColumnName</Parameter>
    </Parameters>
  </Property>
</Object>
```

### ColumnSum <a href="#get_column_sum" id="get_column_sum"></a>

Возвращает сумму значений всех ячеек в определенном столбце таблицы.

```xml
<Object Name="DatabaseTableName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter-->
  <Property Name="ColumnSum">
    <Parameters>
      <!--Значение тэга Parameter с атрибутом Name, равным ColumnName: ожидается название одного из столбцов таблицы-->
      <Parameter Name="ColumnName">ColumnName</Parameter>
    </Parameters>
  </Property>
</Object>
```

### CountingSumMultiply <a href="#get_counting_sum_multiply" id="get_counting_sum_multiply"></a>

Возвращает сумму, состоящую из произведений значений ячеек из двух определенных столбцов.

```xml
<Object Name="DatabaseTableName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter-->
  <Property Name="CountingSumMultiply">
    <Parameters>
      <!--Значение тэга Parameter с атрибутом Name, равным ColumnName1: ожидается название одного из столбцов таблицы-->
      <Parameter Name="ColumnName1">ColumnName1</Parameter>
      <!--Значение тэга Parameter с атрибутом Name, равным ColumnName2: ожидается название одного из столбцов таблицы-->
      <Parameter Name="ColumnName2">ColumnName2</Parameter>
    </Parameters>
  </Property>
</Object>
```

### CountingSignSumMultiply <a href="#get_counting_sign_sum_multiply" id="get_counting_sign_sum_multiply"></a>

Возвращает сумму, состоящую из определенных произведений значений ячеек из двух определенных столбцов.

Признаком для включения произведения строки в общую сумму служит значение ячейки третьего столбца.

```xml
<Object Name="DatabaseTableName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter-->
  <Property Name="CountingSignSumMultiply">
    <Parameters>
      <!--Значение тэга Parameter с атрибутом Name, равным ColumnName1: ожидается название одного из столбцов таблицы-->
      <Parameter Name="ColumnName1">ColumnName1</Parameter>
      <!--Значение тэга Parameter с атрибутом Name, равным ColumnName2: ожидается название одного из столбцов таблицы-->
      <Parameter Name="ColumnName2">ColumnName2</Parameter>
      <!--Значение тэга Parameter с атрибутом Name, равным SignColumnName: ожидается название одного из столбцов таблицы-->
      <Parameter Name="SignColumnName">SignColumnName</Parameter>
    </Parameters>
  </Property>
</Object>
```

### SelectedRowIndex <a href="#get_selected_row_index" id="get_selected_row_index"></a>

Возвращает номер первой выделенной строки таблицы.

```markup
<Object Name="DatabaseTableName">
  <Property Name="SelectedRowIndex" />
</Object>
```

### SelectedRowsIndices <a href="#get_selected_rows_indices" id="get_selected_rows_indices"></a>

Возвращает линейный массив индексов выделенных строк таблицы.

```xml
<Object Name="DatabaseTableName">
  <Property Name="SelectedRowsIndices" />
</Object>
```

### SelectedRowsCount <a href="#get_selected_rows_count" id="get_selected_rows_count"></a>

Возвращает количество выделенных строк в таблице.

```markup
<Object Name="DatabaseTableName">
  <Property Name="SelectedRowsCount" />
</Object>
```

### SelectedCellsSumByColumnName <a href="#get_selected_cells_sum_by_column_name" id="get_selected_cells_sum_by_column_name"></a>

Возвращает сумму значений выделенных ячеек в определенном столбце таблицы.

```xml
<Object Name="DatabaseTableName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter-->
  <Property Name="SelectedCellsSumByColumnName">
    <Parameters>
      <!--Значение тэга Parameter с атрибутом Name, равным ColumnName: ожидается название одного из столбцов таблицы-->
      <Parameter Name="ColumnName">ColumnName</Parameter>
    </Parameters>
  </Property>
</Object>
```

### SelectedRowCellValueByColumnName <a href="#get_selected_row_cell_value_by_column_name" id="get_selected_row_cell_value_by_column_name"></a>

Возвращает значение ячейки определенного столбца выделенной строки таблицы.

```xml
<Object Name="DatabaseTableName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter-->
  <Property Name="SelectedRowCellValueByColumnName">
    <Parameters>
      <!--Значение тэга Parameter с атрибутом Name, равным ColumnName: ожидается название одного из столбцов таблицы-->
      <Parameter Name="ColumnName">ColumnName</Parameter>
    </Parameters>
  </Property>
</Object>
```

### SelectedRowsCellValuesByColumnName <a href="#get_selected_rows_cell_values_by_column_name" id="get_selected_rows_cell_values_by_column_name"></a>

Возвращает линейный массив значений ячеек столбца ColumnName выделенных строк таблицы.

```xml
<Object Name="DatabaseTableName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter-->
  <Property Name="SelectedRowsCellValuesByColumnName">
    <Parameters>
      <!--Значение тэга Parameter с атрибутом Name, равным ColumnName: ожидается название одного из столбцов таблицы-->
      <Parameter Name="ColumnName">ColumnName</Parameter>
    </Parameters>
  </Property>
</Object>
```

### RowsCount <a href="#get_rows_count" id="get_rows_count"></a>

Возвращает количество строк в таблице.

```xml
<Object Name="DatabaseTableName">
  <Property Name="RowsCount" />
</Object>
```

### RowIndexOf <a href="#get_row_index_of" id="get_row_index_of"></a>

Возвращает индекс строки, удовлетворяющей условиям соответствия названий столбцов и значений в этих столбцах.

```xml
<Object Name="DatabaseTableName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter-->
  <Property Name="RowIndexOf">
    <Parameters>
      <!--Значение тэга Parameter с атрибутом Name, равным ColumnNames: ожидается линейный массив названий столбцов таблицы-->
      <Parameter Name="ColumnNames">
        <Structure Type="List">
          <Item>ColumnName1</Item>
          <Item>ColumnName2</Item>
        </Structure>
      </Parameter>
      <!--Значение тэга Parameter с атрибутом Name, равным Values: ожидается линейный массив любых значений-->
      <Parameter Name="Values">
        <Structure Type="List">
          <Item>Value1</Item>
          <Item>Value2</Item>
        </Structure>
      </Parameter>
    </Parameters>
  </Property>
</Object>
```

### RowsIndicesOf <a href="#get_rows_indices_of" id="get_rows_indices_of"></a>

Возвращает массив индексов строки, удовлетворяющих условиям соответствия названий столбцов и значений в этих столбцах.

При установке параметра SearchWithArrays поиск для каждого столбца будет вестись по значениям из переданного для него массива по такому принципу, чтобы очередное значение из таблицы совпадало хотя бы с одним значением из этого массива.

```xml
<Object Name="DatabaseTableName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter-->
  <Property Name="RowsIndicesOf">
    <Parameters>
      <!--Значение тэга Parameter с атрибутом Name, равным ColumnNames: ожидается линейный массив названий столбцов таблицы-->
      <Parameter Name="ColumnNames">
        <Structure Type="List">
          <Item>ColumnName1</Item>
          <Item>ColumnName2</Item>
        </Structure>
      </Parameter>
      <!--Значение тэга Parameter с атрибутом Name, равным Values: ожидается линейный массив любых значений-->
      <!--При установленном параметре SearchWithArrays в качестве значения для каждого столбца допустимо передавать линейный массив любых значений, по которым и будет вестись поиск-->
      <Parameter Name="Values">
        <Structure Type="List">
          <Item>Value1</Item>
          <Item>
            <Structure Type="List">
              <Item>Value2</Item>
              <Item>Value3</Item>
            </Structure>
          </Item>
        </Structure>
      </Parameter>
      <!--Необязательный параметр. При отсутствии используется значение False-->
      <!--Значение тэга Parameter с атрибутом Name, равным SearchWithArrays: ожидается логическое значение-->
      <Parameter Name="SearchWithArrays">False</Parameter>
    </Parameters>
  </Property>
</Object>
```

### ValueByAnotherFieldValue <a href="#get_value_by_another_field_value" id="get_value_by_another_field_value"></a>

Возвращает значение ячейки одного столбца в строке, найденной по определенному значению другого столбца.

```xml
<Object Name="DatabaseTableName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter-->
  <Property Name="ValueByAnotherFieldValue">
    <Parameters>
      <!--Значение тэга Parameter с атрибутом Name, равным TargetField: ожидается название одного из столбцов таблицы-->
      <Parameter Name="TargetField">TargetColumnName</Parameter>
      <!--Значение тэга Parameter с атрибутом Name, равным FilterValue: любое значение-->
      <Parameter Name="FilterValue">FilterValue</Parameter>
      <!--Значение тэга Parameter с атрибутом Name, равным FilterField: ожидается название одного из столбцов таблицы-->
      <Parameter Name="FilterField">FilterColumnName</Parameter>
    </Parameters>
  </Property>
</Object>
```

### Data <a href="#get_data" id="get_data"></a>

Возвращает двумерную матрицу элементов с именованными столбцами, содержащую значения всех ячеек таблицы, удовлетворяющую выражению фильтра.

Все поддерживаемые в выражении фильтра конструкции смотрите по [ссылке](http://msdn.microsoft.com/en-us/library/system.data.datacolumn.expression.aspx).

```xml
<Object Name="DatabaseTableName">
  <!--Значение тэга Property: любое значение-->
  <Property Name="Data">FilterField > 0</Property>
</Object>
```

### ArrayData <a href="#get_array_data" id="get_array_data"></a>

Возвращает двумерную матрицу элементов, содержащую значения всех ячеек таблицы.

```xml
<Object Name="DatabaseTableName">
  <!--Значение тэга Property: не ожидается-->
  <Property Name="ArrayData" />
</Object>
```

### DictionaryArrayData <a href="#get_dictionary_array_data" id="get_dictionary_array_data"></a>

Возвращает массив словарей, содержащих значения всех ячеек таблицы.

```xml
<Object Name="DatabaseTableName">
  <!--Значение тэга Property: не ожидается-->
  <Property Name="DictionaryArrayData" />
</Object>
```

### FilteredColumnValues <a href="#get_filtered_column_values" id="get_filtered_column_values"></a>

Возвращает массив элементов определенного столбца ColumnName, выбранных на основе выражения Filter, задающего фильтрацию строк таблицы.

```xml
<Object Name="DatabaseTableName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter-->
  <Property Name="FilteredColumnValues">
    <Parameters>
      <!--Значение тэга Parameter с атрибутом Name, равным ColumnName: ожидается название одного из столбцов таблицы-->
      <Parameter Name="ColumnName">ColumnName</Parameter>
      <!--Значение тэга Parameter с атрибутом Name, равным ColumnName: любое значение-->
      <!--Все поддерживаемые в выражении фильтра конструкции смотрите по ссылке "http://msdn.microsoft.com/en-us/library/system.data.datacolumn.expression.aspx"-->
      <Parameter Name="Filter">ColumnName > 1</Parameter>
    </Parameters>
  </Property>
</Object>
```

### RowAdded <a href="#get_row_added" id="get_row_added"></a>

Возвращает признак, была ли строка с определенным индексом сохранена в базе данных.

```xml
<Object Name="DatabaseTableName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter-->
  <Property Name="RowAdded">
    <Parameters>
      <!--Значение тэга Parameter с атрибутом Name, равным Value: ожидается целочисленное значение-->
      <Parameter Name="Value">1</Parameter>
    </Parameters>
  </Property>
</Object>
```

### VerticalScrollOffset <a href="#get_vertical_scroll_offset" id="get_vertical_scroll_offset"></a>

Возвращает величину смещения полосы вертикальной прокрутки таблицы в пикселях.

```xml
<Object Name="DatabaseTableName">
  <Property Name="VerticalScrollOffset" />
</Object>
```

### HorizontalScrollOffset <a href="#get_horizontal_scroll_offset" id="get_horizontal_scroll_offset"></a>

Возвращает величину смещения полосы горизонтальной прокрутки таблицы в пикселях.

```xml
<Object Name="DatabaseTableName">
  <Property Name="HorizontalScrollOffset" />
</Object>
```

### LastCellClickedRowIndex <a href="#get_last_cell_clicked_row_index" id="get_last_cell_clicked_row_index"></a>

Возвращает индекс строки, по ячейке которой был совершен последний клик (значение обновляется после события Click, но до события CellClick).

```xml
<Object Name="DatabaseTableName">
  <Property Name="LastCellClickedRowIndex" />
</Object>
```

### LastCellClickedColumnName <a href="#get_last_cell_clicked_column_name" id="get_last_cell_clicked_column_name"></a>

Возвращает название столбца, по ячейке которого был совершен последний клик (значение обновляется после события Click, но до события CellClick).

```xml
<Object Name="DatabaseTableName">
  <Property Name="LastCellClickedColumnName" />
</Object>
```

### LastCellDoubleClickedRowIndex <a href="#get_last_cell_double_clicked_row_index" id="get_last_cell_double_clicked_row_index"></a>

Возвращает индекс строки, по ячейке которой был совершен последний двойной клик (значение обновляется после события [DoubleClick](/broken/pages/52ulpzkSf4ww5uSDYcpX), но до события [CellDoubleClick](/broken/pages/-M_yOkwiQuOVd5ZkGd8V)).

```xml
<Object Name="DatabaseTableName">
  <Property Name="LastCellDoubleClickedRowIndex" />
</Object>
```

### LastCellDoubleClickedColumnName <a href="#get_last_cell_double_clicked_column_name" id="get_last_cell_double_clicked_column_name"></a>

Возвращает название столбца, по ячейке которого был совершен последний двойной клик (значение обновляется после события [DoubleClick](/broken/pages/52ulpzkSf4ww5uSDYcpX), но до события [CellDoubleClick](/broken/pages/-M_yOkwiQuOVd5ZkGd8V)).

```xml
<Object Name="DatabaseTableName">
  <Property Name="LastCellDoubleClickedColumnName" />
</Object>
```

### ColumnMinimumWidth <a href="#get_column_minimum_width" id="get_column_minimum_width"></a>

Возвращает минимальную ширину определенного столбца таблицы.

```xml
<Object Name="DatabaseTableName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter-->
  <Property Name="ColumnMinimumWidth">
    <Parameters>
      <!--Значение тэга Parameter с атрибутом Name, равным ColumnName: ожидается название одного из столбцов таблицы-->
      <Parameter Name="ColumnName">ColumnName</Parameter>
    </Parameters>
  </Property>
</Object>
```

## Set-проперти для динамического задания свойств <a href="#set_property_databasetable" id="set_property_databasetable"></a>

### MaxHeight <a href="#set_row_height" id="set_row_height"></a>

Задает максимально допустимую высоту таблицы.

Ожидается целочисленное значение.

```xml
<Object Name="DatabaseTableName">
  <Property Name="MaxHeight">300</Property>
</Object>
```

### RowHeight <a href="#set_row_height" id="set_row_height"></a>

Задает высоту строк с данными в таблице.

Ожидается целочисленное значение.

```xml
<Object Name="DatabaseTableName">
  <Property Name="RowHeight">20</Property>
</Object>
```

### ColumnHeadersHeight <a href="#set_column_headers_height" id="set_column_headers_height"></a>

Задает высоту "шапки" таблицы.

Ожидается целочисленное значение.

```xml
<Object Name="DatabaseTableName">
  <Property Name="ColumnHeadersHeight">20</Property>
</Object>
```

### ColumnHeadersVisible <a href="#set_column_headers_visible" id="set_column_headers_visible"></a>

Задает признак, определяющий, показывать или нет "шапку" таблицы.

Ожидается логическое значение.

```xml
<Object Name="DatabaseTableName">
  <Property Name="ColumnHeadersVisible">True</Property>
</Object>
```

### BackgroundColor <a href="#set_background_color" id="set_background_color"></a>

Задает имя цвета фона таблицы.

Ожидается имя одного из цветов, описанных на форме или описание цвета в формате HTML (#rrggbb).

```xml
<Object Name="DatabaseTableName">
  <Property Name="BackgroundColor">BackgroundColor</Property>
</Object>
```

### MultiSelect <a href="#set_multi_select" id="set_multi_select"></a>

Задает признак, определяющий, можно ли выделить в таблице более одной строки одновременно.

Ожидается логическое значение.

```xml
<Object Name="DatabaseTableName">
  <Property Name="MultiSelect">True</Property>
</Object>
```

### ColumnTitle <a href="#set_column_title" id="set_column_title"></a>

Задает название [`<Title>`](./#column_title) для столбца ColumnName таблицы.

```xml
<Object Name="DatabaseTableName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter-->
  <Property Name="ColumnTitle">
    <Parameters>
      <!--Значение тэга Parameter с атрибутом Name, равным ColumnName: ожидается название одного из столбцов таблицы-->
      <Parameter Name="ColumnName">ColumnName</Parameter>
      <!--Значение тэга Parameter с атрибутом Name, равным Title: ожидается скалярное значение-->
      <Parameter Name="Title">Наименование</Parameter>
    </Parameters>
  </Property>
</Object>
```

### ColumnHint <a href="#set_column_hint" id="set_column_hint"></a>

Задает текст подсказки [`<Hint>`](./#column_hint), всплывающей на заголовке столбца таблицы, для столбца ColumnName таблицы.

```xml
<Object Name="DatabaseTableName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter-->
  <Property Name="ColumnHint">
    <Parameters>
      <!--Значение тэга Parameter с атрибутом Name, равным ColumnName: ожидается название одного из столбцов таблицы-->
      <Parameter Name="ColumnName">ColumnName</Parameter>
      <!--Значение тэга Parameter с атрибутом Name, равным Hint: ожидается скалярное значение-->
      <Parameter Name="Hint">Текст подсказки</Parameter>
    </Parameters>
  </Property>
</Object>
```

### ColumnDisplayIndex <a href="#set_column_display_index" id="set_column_display_index"></a>

Задает порядок отображения [`<DisplayIndex>`](./#column_display_index) для столбца ColumnName таблицы.

```xml
<Object Name="DatabaseTableName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter-->
  <Property Name="ColumnDisplayIndex">
    <Parameters>
      <!--Значение тэга Parameter с атрибутом Name, равным ColumnName: ожидается название одного из столбцов таблицы-->
      <Parameter Name="ColumnName">ColumnName</Parameter>
      <!--Значение тэга Parameter с атрибутом Name, равным DisplayIndex: ожидается неотрицательное целочисленное значение-->
      <Parameter Name="DisplayIndex">3</Parameter>
    </Parameters>
  </Property>
</Object>
```

### ColumnWidth <a href="#set_column_width" id="set_column_width"></a>

Задает ширину [`<Width>`](./#column_width) для столбца ColumnName таблицы.

```xml
<Object Name="DatabaseTableName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter-->
  <Property Name="ColumnWidth">
    <Parameters>
      <!--Значение тэга Parameter с атрибутом Name, равным ColumnName: ожидается название одного из столбцов таблицы-->
      <Parameter Name="ColumnName">ColumnName</Parameter>
      <!--Значение тэга Parameter с атрибутом Name, равным Width: ожидается положительное целочисленное значение-->
      <Parameter Name="Width">100</Parameter>
    </Parameters>
  </Property>
</Object>
```

### SelectedRowIndex <a href="#set_selected_row_index" id="set_selected_row_index"></a>

Задает выделенную строку таблицы по индексу, показывая выделенную строку первой.

Ожидается целочисленное значение.

```xml
<Object Name="DatabaseTableName">
  <Property Name="SelectedRowIndex">1</Property>
</Object>
```

### SelectedRowsIndices <a href="#set_selected_rows_indices" id="set_selected_rows_indices"></a>

Задает выделенные строки таблицы по индексам.

Ожидается линейный массив целочисленных значений.

```xml
<Object Name="DatabaseTableName">
  <Property Name="SelectedRowsIndices">
    <Structure Type="List">
      <Item>1</Item>
      <Item>2</Item>
    </Structure>
  </Property>
</Object>
```

### SelectRowByFieldValue <a href="#set_select_row_by_field_value" id="set_select_row_by_field_value"></a>

Выделяет первую строку таблицы, для которой значение, указанное в столбце ColumnName, совпадает с одним из значений, указанных в параметре Value.

```xml
<Object Name="DatabaseTableName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter-->
  <Property Name="SelectRowByFieldValue">
    <Parameters>
      <!--Значение тэга Parameter с атрибутом Name, равным ColumnName: ожидается название одного из столбцов таблицы-->
      <Parameter Name="ColumnName">ColumnName</Parameter>
      <!--Значение тэга Parameter с атрибутом Name, равным Value: ожидается скалярное значение или линейных массив значений-->
      <Parameter Name="Value">Value</Parameter>
    </Parameters>
  </Property>
</Object>
```

### SelectRowsByFieldValue <a href="#set_select_rows_by_field_value" id="set_select_rows_by_field_value"></a>

Выделяет строки таблицы, для которых значений, указанные в столбце ColumnName, совпадают с одним из значений, указанных в параметре Value.

```xml
<Object Name="DatabaseTableName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter-->
  <Property Name="SelectRowsByFieldValue">
    <Parameters>
      <!--Значение тэга Parameter с атрибутом Name, равным ColumnName: ожидается название одного из столбцов таблицы-->
      <Parameter Name="ColumnName">ColumnName</Parameter>
      <!--Значение тэга Parameter с атрибутом Name, равным Value: ожидается скалярное значение или линейных массив значений-->
      <Parameter Name="Value">Value</Parameter>
    </Parameters>
  </Property>
</Object>
```

### AutoSize <a href="#set_auto_size" id="set_auto_size"></a>

Единоразово устанавливает ширину и высоту таблицы, сворачивая или разворачивая её таким образом, чтобы в зоне видимости оказались все её строки и столбцы без полос прокрутки.

Значение тэга `<Property>`: не ожидается.

```xml
<Object Name="DatabaseTableName">
  <Property Name="AutoSize" />
</Object>
```

### AddRow <a href="#set_add_row" id="set_add_row"></a>

Добавляет новую строку в таблицу со значениями Values, соответствующим столбцам ColumnNames, на место с индексом Index и выделяет ее в соответствии с признаком SelectAfterAdd, при этом снимая выделение с остальных строк в соответствии с признаком ClearOtherSelection.

```xml
<Object Name="DatabaseTableName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter-->
  <Property Name="AddRow">
    <Parameters>
      <!--Необязательный параметр. При отсутствии используется пустой массив-->
      <!--Значение тэга Parameter с атрибутом Name, равным ColumnNames: ожидается линейный массив названий столбцов таблицы-->
      <Parameter Name="ColumnNames">
        <Structure Type="List">
          <Item>ColumnName1</Item>
          <Item>ColumnName2</Item>
        </Structure>
      </Parameter>
      <!--Необязательный параметр. При отсутствии используется пустой массив-->
      <!--Значение тэга Parameter с атрибутом Name, равным Values: ожидается линейный массив любых значений-->
      <Parameter Name="Values">
        <Structure Type="List">
          <Item>Value1</Item>
          <Item>Value2</Item>
        </Structure>
      </Parameter>
      <!--Необязательный параметр. При отсутствии строка будет добавлена в конец таблицы-->
      <!--Значение тэга Parameter с атрибутом Name, равным Index: ожидается целое неотрицательное значение-->
      <Parameter Name="Index">0</Parameter>
      <!--Необязательный параметр. При отсутствии используется значение False-->
      <!--Значение тэга Parameter с атрибутом Name, равным SelectAfterAdd: ожидается логическое значение-->
      <Parameter Name="SelectAfterAdd">False</Parameter>
      <!--Необязательный параметр. При отсутствии используется значение True-->
      <!--Значение тэга Parameter с атрибутом Name, равным ClearOtherSelection: ожидается логическое значение-->
      <Parameter Name="ClearOtherSelection">True</Parameter>
    </Parameters>
  </Property>
</Object>
```

### AddRows <a href="#set_add_rows" id="set_add_rows"></a>

Добавляет новые строки в таблицу со значениями из таблицы Values, столбцы которой соответствуют столбцам ColumnNames, на места начиная с индекса Index и выделяя их (или первую из них - при значении тэга[`<MultiSelect>`](./#multi_select) равного False) в соответствии с признаком SelectAfterAdd, при этом выделение остальных строк снимается в соответствии с признаком ClearOtherSelection.

```xml
<Object Name="DatabaseTableName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter-->
  <Property Name="AddRows">
    <Parameters>
      <!--Необязательный параметр. При отсутствии используется пустой массив-->
      <!--Значение тэга Parameter с атрибутом Name, равным ColumnNames: ожидается линейный массив названий столбцов таблицы-->
      <Parameter Name="ColumnNames">
        <Structure Type="List">
          <Item>ColumnName1</Item>
          <Item>ColumnName2</Item>
        </Structure>
      </Parameter>
      <!--Необязательный параметр. При отсутствии используется пустая таблица-->
      <!--Значение тэга Parameter с атрибутом Name, равным Values: ожидается таблица (например, ссылка на GetDataConnection) с числом столбцов равным аналогичному числу из параметра ColumnNames-->
      <Parameter Name="Values">
        <DataConnection SourceDataConnection="SourceDataConnectionName">
          <Fields>
            <Field Name="ColumnName1" />
            <Field Name="ColumnName2" />
          </Fields>
        </DataConnection>
      </Parameter>
      <!--Необязательный параметр. При отсутствии строки будут добавлены в конец таблицы-->
      <!--Значение тэга Parameter с атрибутом Name, равным Index: ожидается целое неотрицательное значение-->
      <Parameter Name="Index">0</Parameter>
      <!--Необязательный параметр. При отсутствии используется значение False-->
      <!--Значение тэга Parameter с атрибутом Name, равным SelectAfterAdd: ожидается логическое значение-->
      <Parameter Name="SelectAfterAdd">False</Parameter>
      <!--Необязательный параметр. При отсутствии используется значение True-->
      <!--Значение тэга Parameter с атрибутом Name, равным ClearOtherSelection: ожидается логическое значение-->
      <Parameter Name="ClearOtherSelection">True</Parameter>
    </Parameters>
  </Property>
</Object>
```

### UpdateRow <a href="#set_update_row" id="set_update_row"></a>

Изменяет значения столбцов ColumnNames на значения Values, соответствующим столбцам ColumnNames, в строке с индексом RowIndex.

```xml
<Object Name="DatabaseTableName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter-->
  <Property Name="UpdateRow">
    <Parameters>
      <!--Необязательный параметр. При отсутствии обновятся все строки-->
      <!--Значение тэга Parameter с атрибутом Name, равным RowIndex: ожидается целочисленное значение-->
      <Parameter Name="RowIndex">0</Parameter>
      <!--Значение тэга Parameter с атрибутом Name, равным ColumnNames: ожидается линейный массив названий столбцов таблицы-->
      <Parameter Name="ColumnNames">
        <Structure Type="List">
          <Item>ColumnName1</Item>
          <Item>ColumnName2</Item>
        </Structure>
      </Parameter>
      <!--Значение тэга Parameter с атрибутом Name, равным Values: ожидается линейный массив любых значений-->
      <Parameter Name="Values">
        <Structure Type="List">
          <Item>Value1</Item>
          <Item>Value2</Item>
        </Structure>
      </Parameter>
    </Parameters>
  </Property>
</Object>
```

### UpdateRows <a href="#set_update_rows" id="set_update_rows"></a>

Изменяет значения столбцов ColumnNames на значения Values, соответствующим столбцам ColumnNames, в строках с индексами RowIndices.

```xml
<Object Name="DatabaseTableName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter-->
  <Property Name="UpdateRows">
    <Parameters>
      <!--Необязательный параметр. При отсутствии обновятся все строки-->
      <!--Значение тэга Parameter с атрибутом Name, равным RowIndices: ожидается линейный массив целочисленных значений-->
      <Parameter Name="RowIndices">
        <Structure Type="List">
          <Item>1</Item>
          <Item>2</Item>
        </Structure>
      </Parameter>
      <!--Значение тэга Parameter с атрибутом Name, равным ColumnNames: ожидается линейный массив названий столбцов таблицы-->
      <Parameter Name="ColumnNames">
        <Structure Type="List">
          <Item>ColumnName1</Item>
          <Item>ColumnName2</Item>
        </Structure>
      </Parameter>
      <!--Значение тэга Parameter с атрибутом Name, равным Values: ожидается массив любых значений-->
      <Parameter Name="Values">
        <Structure Type="List">
          <Item>Value1</Item>
          <Item>Value2</Item>
        </Structure>
      </Parameter>
      <!--Значение тэга Parameter с атрибутом Name, равным ReplicateValues: ожидается логическое значение-->
      <!--Необязательный параметр. При отсутствии или значении True значение Values рассматривается как линейный массив значений, который изменяет строки с индексами RowIndices-->
      <!--Если параметр равен False, то значение Values рассматривается как матрица значений, которые будут записаны в строки с индексами RowIndices.-->
      <!--При этом:-->
      <!--   1. если количество элементов строки матрицы не совпадает с количеством столбцов ColumnNames, то значения недостающих ячеек изменяются на NULL;-->
      <!--   2. если количество строк матрицы не совпадает с количеством индексов RowIndices, то значения ячеек отсутствующих строк изменятся на NULL.-->
      <Parameter Name="ReplicateValues">False</Parameter>
    </Parameters>
  </Property>
</Object>
```

### UpdateColumn <a href="#set_update_column" id="set_update_column"></a>

Построчно изменяет значения ячеек в столбце ColumnName на соответствующие значения массива Values.

```xml
<!--Индекс обновляемой строки таблицы равен индексу ячейки массива, из которой новое значение будет взято-->
<!--Если длина массива меньше, чем количество строк в таблице, то оставшиеся без обновления строки будут заполнены пустыми значениями. Если длина массива больше, то оставшиеся значения будут проигнорированы-->
<Object Name="DatabaseTableName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter-->
  <Property Name="UpdateColumn">
    <Parameters>
      <!--Значение тэга Parameter с атрибутом Name, равным ColumnName: ожидается название одного из столбцов таблицы-->
      <Parameter Name="ColumnName">ColumnName</Parameter>
      <!--Значение тэга Parameter с атрибутом Name, равным Values: ожидается линейный массив любых значений-->
      <Parameter Name="Values">
        <Structure Type="List">
          <Item>Value1</Item>
          <Item>Value2</Item>
        </Structure>
      </Parameter>
    </Parameters>
  </Property>
</Object>
```

### UpdateColumnCellsValues <a href="#set_update_column_cells_values" id="set_update_column_cells_values"></a>

Изменяет значения ячеек в строках с индексами RowsIndices в столбце ColumnName на значение Value.

```xml
<Object Name="DatabaseTableName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter-->
  <Property Name="UpdateColumnCellsValues">
    <Parameters>
      <!--Значение тэга Parameter с атрибутом Name, равным ColumnName: ожидается название одного из столбцов таблицы-->
      <Parameter Name="ColumnName">ColumnName</Parameter>
      <!--Необязательный параметр. При отсутствии обновятся все строки-->
      <!--Значение тэга Parameter с атрибутом Name, равным RowsIndices: ожидается линейный массив любых значений-->
      <Parameter Name="RowsIndices">
        <Structure Type="List">
          <Item>Value1</Item>
          <Item>Value2</Item>
        </Structure>
      </Parameter>
      <!--Значение тэга Parameter с атрибутом Name, равным Value: ожидается любое значение-->
      <Parameter Name="Value">Value</Parameter>
    </Parameters>
  </Property>
</Object>
```

### DeleteRowsByIndices <a href="#set_delete_rows_by_indices" id="set_delete_rows_by_indices"></a>

Удаляет строки с индексами Value из таблицы.

```xml
<Object Name="DatabaseTableName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter-->
  <Property Name="DeleteRowsByIndices">
    <Parameters>
      <!--Необязательный параметр. При отсутствии удалются все строки-->
      <!--Значение тэга Parameter с атрибутом Name, равным Value: ожидается линейный массив целочисленных значений-->
      <Parameter Name="Value">
        <Structure Type="List">
          <Item>1</Item>
          <Item>2</Item>
        </Structure>
      </Parameter>
    </Parameters>
  </Property>
</Object>
```

### ColumnMinimumWidth <a href="#set_column_minimum_width" id="set_column_minimum_width"></a>

Задает минимальную ширину [`<MinimumWidth>`](./#column_minium_width) для столбца ColumnName таблицы.

```xml
<Object Name="DatabaseTableName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter-->
  <Property Name="ColumnMinimumWidth">
    <Parameters>
      <!--Значение тэга Parameter с атрибутом Name, равным ColumnName: ожидается название одного из столбцов таблицы-->
      <Parameter Name="ColumnName">ColumnName</Parameter>
      <!--Значение тэга Parameter с атрибутом Name, равным Width: ожидается положительное целочисленное значение-->
      <Parameter Name="MinimumWidth">100</Parameter>
    </Parameters>
  </Property>
</Object>
```

### ClearSelection <a href="#set_clear_selection" id="set_clear_selection"></a>

Снимает выделение со всех строк таблицы.

Значение тэга `<Property>`: не ожидается.

```xml
<Object Name="DatabaseTableName">
   <Property Name="ClearSelection" />
</Object>
```
