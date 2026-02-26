---
description: >-
  Первично загружающее соединение с данными; получает данные с сервера;
  представляет собой одну или несколько таблиц данных.
---

# PrimaryGetDataConnection



## Шаблон PrimaryGetDataConnection <a href="#template_primary_dc" id="template_primary_dc"></a>

#### Вариант с одним запросом SqlQuery

```xml
<DataConnection Name="" Type="PrimaryGetDataConnection" Assembly="DataConnections">
  <ManualLoad></ManualLoad>
  <DependOn>
    <DataConnection Name="" />
    <DataConnection Name="" />
  </DependOn>
  <UpdateInterval Hours="" Minutes="" Seconds=""></UpdateInterval>
  <SqlQuery Name="" Type="Select">
    <ManualLoad></ManualLoad> 
    <Workflow Name="" />
    <Fields>
      <Field Name="" NativeName="" />
      <Field Name="" Type="FormatField" FormatString="">
        <Field NativeName="" />
        <Field NativeName="" />
      </Field>
    </Fields>
    <Parameters>
      <Parameter NativeName="" RefreshQuery="" SendAsArray="">
        <Value></Value>
        <IfNull></IfNull>
        <IfEmpty></IfEmpty>
      </Parameter>
    </Parameters>
    <Filter>
      <And RefreshFilter="">
        <Or RefreshFilter="">
          <Filter Type="" FilterByNullValue="" RefreshFilter="" Reverse="">
            <Field NativeName="" />
            <Value></Value>
            <DataType Type="" />
            <Enabled></Enabled>
          </Filter>
          <Filter Type="" FilterByNullValue="" RefreshFilter="" Reverse="">
            <Field NativeName="" />
            <Value></Value>
            <DataType Type="" />
            <Enabled></Enabled>
          </Filter>
        </Or>
        <Not RefreshFilter="">
          <Filter Type="" FilterByNullValue="" RefreshFilter="" Reverse="">
            <Field NativeName="" />
            <Value></Value>
            <DataType Type="" />
            <Enabled></Enabled>
          </Filter>
        </Not>
      </And>
    </Filter>
  </SqlQuery>
</DataConnection>
```

#### Вариант с несколькими запросами SqlQuery

Все SqlQuery из DataConnection добавляются в очередь загрузки.

```xml
<DataConnection Name="" Type="PrimaryGetDataConnection" Assembly="DataConnections">
  <ManualLoad></ManualLoad>
  <DependOn>
    <DataConnection Name="" />
    <DataConnection Name="" />
  </DependOn>
  <UpdateInterval Hours="" Minutes="" Seconds=""></UpdateInterval>
  <SqlQueries>
    <SqlQuery Name="" Type="Select">
      <ManualLoad></ManualLoad> 
      <Workflow Name="" />
      <Fields>
        <Field Name="" NativeName="" />
        <Field Name="" Type="FormatField" FormatString="">
          <Field NativeName="" />
          <Field NativeName="" />
        </Field>
      </Fields>
      <Parameters>
        <Parameter NativeName="" RefreshQuery="" SendAsArray="">
          <Value></Value>
          <IfNull></IfNull>
          <IfEmpty></IfEmpty>
        </Parameter>
      </Parameters>
      <Filter>
        <And RefreshFilter="">
          <Or RefreshFilter="">
            <Filter Type="" FilterByNullValue="" RefreshFilter="">
              <Field NativeName="" />
              <Value></Value>
              <DataType Type="" />
              <Enabled></Enabled>
            </Filter>
            <Filter Type="" FilterByNullValue="" RefreshFilter="">
              <Field NativeName="" />
              <Value></Value>
              <DataType Type="" />
              <Enabled></Enabled>
            </Filter>
          </Or>
          <Not RefreshFilter="">
            <Filter Type="" FilterByNullValue="" RefreshFilter="">
              <Field NativeName="" />
              <Value></Value>
              <DataType Type="" />
              <Enabled></Enabled>
            </Filter>
          </Not>
        </And>
      </Filter>
    </SqlQuery>
  </SqlQueries>
</DataConnection>
```

## Описание PrimaryGetDataConnection <a href="#description_primary_dc" id="description_primary_dc"></a>

```xml
<DataConnection Name="PrimaryGetDataConnectionName" Type="PrimaryGetDataConnection" Assembly="DataConnections">
  <!--Тэги, специфичные для PrimaryGetDataConnection-->
</DataConnection>
```

## Тэги, специфичные для PrimaryGetDataConnection <a href="#option_1_tags_primary_dc" id="option_1_tags_primary_dc"></a>

### ManualLoad <a href="#manual_load" id="manual_load"></a>

Признак, определяющий, будет ли загрузка данных происходить только после ручного обновления соединения с данными, а не вместе с загрузкой формы.

Необязательный тэг. Ожидается логическое значение.

По умолчанию используется значение False.

```xml
<ManualLoad>False</ManualLoad>
```

{% hint style="warning" %}
В качестве значения тэга `<ManualLoad>` не стоит ссылаться на другой DataConnection, так как это помешает корректно построить дерево зависимостей - форма не отследит эту зависимость.
{% endhint %}

### DependOn <a href="#depend_on" id="depend_on"></a>

Признак, определяющий зависимость от других соединений с данными. Загрузка данных этого соединения будет осуществлена после загрузки всех указанных соединений.

Необязательный тэг. Ожидается список тэгов `<DataConnection>` с названиями загружающих соединений с данными, описанных на форме.

```xml
<DependOn>
  <DataConnection Name="" />
  <DataConnection Name="" />
</DependOn> 
```

### SqlQuery <a href="#sql_query" id="sql_query"></a>

Запрос для получения данных.

Обязательный тэг. Тэг `<SqlQuery>` не должен находиться одновременно с тэгом [`<SqlQueries>`](./#sql_queries).

```xml
<SqlQuery Name="" Type="Select">
  <Workflow Name="" />
  <ManualLoad></ManualLoad>
  <Fields>
    <Field Name="" />
    <Field Name="" />
    <Field Name="" />
  </Fields>
  <Parameters>
    <Parameter NativeName="">
      <Value></Value>
    </Parameter>
  </Parameters>
  <Filter>
    <And RefreshFilter="">
      <Filter Type="" FilterByNullValue="" RefreshFilter="">
        <Field NativeName="" />
        <Value></Value>
        <DataType Type="" />
        <Enabled></Enabled>
      </Filter>
      <Filter Type="" FilterByNullValue="" RefreshFilter="">
        <Field NativeName="" />
        <Value></Value>
        <DataType Type="" />
        <Enabled></Enabled>
      </Filter>
    </And>
  </Filter>
</SqlQuery>
```

Подробное описание тэга по [ссылке](/broken/pages/vMQQoHIhtBcQbYXgK4rS#sql_query).

### SqlQueries <a href="#sql_queries" id="sql_queries"></a>

Запросы для получения данных.

Обязательный тэг. Тэг `<SqlQueries>` не должен находиться одновременно с тэгом [`<SqlQuery>`](./#sql_query) (на одном уровне).

```xml
<SqlQueries>
  <SqlQuery Name="" Type="Select">
    <Workflow Name="" />
    <ManualLoad></ManualLoad>
    <Fields>
      <Field Name="" />
      <Field Name="" />
      <Field Name="" />
    </Fields>
  </SqlQuery>
  <SqlQuery Name="" Type="Select">
    <Workflow Name="" />
    <ManualLoad></ManualLoad>
    <Fields>
      <Field Name="" />
      <Field Name="" />
      <Field Name="" />
    </Fields>
    <Parameters>
      <Parameter NativeName="">
        <Value></Value>
      </Parameter>
    </Parameters>
  </SqlQuery>
</SqlQueries>
```

### UpdateInterval <a href="#update_interval" id="update_interval"></a>

Интервал автоматического обновления первичного соединения с данными.

Необязательный тэг. Ожидается логическое значение. Если значение тэга не указано, то используется значение True.

```xml
<UpdateInterval Hours="" Minutes="" Seconds="">True</UpdateInterval>
```

Атрибуты тэга `<UpdateInterval>`:

* **Hours** - Интервал в часах.\
  Обязательный атрибут. Ожидается целое положительное число.
* **Minutes** - Интервал в минутах.\
  Необязательный атрибут. Ожидается целое положительное число.
* **Seconds** - Интервал в секундах.\
  Необязательный атрибут. Ожидается целое положительное число.

## Get-проперти для получения свойств <a href="#get_property_primary_dc" id="get_property_primary_dc"></a>

### Count <a href="#get_count" id="get_count"></a>

Возвращает количество строк в указанном запроса загружающего соединения с данными.

Ожидается имя одного из запросов, описанных в загружающем соединении с данными. Если имя запроса не указано, то используется первый запрос (в порядке описания запросов).

```xml
<DataConnection SourceDataConnection="PrimaryGetDataConnectionName">
  <Property Name="Count">SqlQueryName</Property>
</DataConnection>
```

### ValueChanged <a href="#get_value_changed" id="get_value_changed"></a>

Возвращает признак изменения данных DataConnection.

```xml
<DataConnection SourceDataConnection="PrimaryGetDataConnectionName">
  <Property Name="ValueChanged" />
</DataConnection>
```

### RowIndexOf <a href="#get_row_index_of" id="get_row_index_of"></a>

Возвращает индекс строки, удовлетворяющей условиям соответствия названий столбцов и значений в этих столбцах.

```xml
<DataConnection SourceDataConnection="PrimaryGetDataConnectionName">
  <Property Name="RowIndexOf">
    <Parameters>
      <Parameter Name="ColumnNames">
        <Structure Type="List">
          <Item>ColumnName1</Item>
          <Item>ColumnName2</Item>
        </Structure>
      </Parameter>
      <Parameter Name="Values">
        <Structure Type="List">
          <Item>Value1</Item>
          <Item>Value2</Item>
        </Structure>
      </Parameter>
    </Parameters>
  </Property>
</DataConnection>
```

Параметр **ColumnNames** ожидает линейный массив названий полей DataConnection.

Параметр **Values** ожидает линейный массив любых значений, по которым будет произведен поиск в соответствующих полях.

### RowsIndicesOf <a href="#get_rows_indices_of" id="get_rows_indices_of"></a>

Возвращает массив индексов строки, удовлетворяющих условиям соответствия названий столбцов и значений в этих столбцах.

```xml
<DataConnection SourceDataConnection="PrimaryGetDataConnectionName">
  <Property Name="RowsIndicesOf">
    <Parameters>
      <Parameter Name="ColumnNames">
        <Structure Type="List">
          <Item>ColumnName1</Item>
          <Item>ColumnName2</Item>
        </Structure>
      </Parameter>
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
      <Parameter Name="SearchWithArrays">False</Parameter>
    </Parameters>
  </Property>
</DataConnection>
```

Параметр **ColumnNames** ожидает линейный массив названий полей DataConnection.

Параметр **Values** ожидает линейный массив любых значений, по которым будет произведен поиск в соответствующих полях.

Необязательный параметр **SearchWithArrays** разрешает для каждого столбца использовать линейный массив значений, с элементами которого будет сравниваться значения из каждой строки соответствующего столбца. Ожидается логическое значение. По умолчанию используется значение False.

### Column

Возвращает линейный массив значений, содержащихся в определенном столбце таблицы.

```xml
<DataConnection SourceDataConnection="PrimaryGetDataConnectionName">
  <Property Name="Column">
    <Parameters>
      <Parameter Name="ColumnName">ColumnName</Parameter>
    </Parameters>
  </Property>  
</DataConnection>
```

Параметр **ColumnName** ожидает название одного из полей DataConnection.

## Set-проперти для динамического задания свойств

### AddRow <a href="#set_add_row" id="set_add_row"></a>

Добавляет новую строку в таблицу DataConnection.

```xml
<DataConnection Name="PrimaryGetDataConnectionName">
  <Property Name="AddRow">
    <Parameters>
      <Parameter Name="ColumnNames">
        <Structure Type="List">
          <Item>ColumnName1</Item>
          <Item>ColumnName2</Item>
        </Structure>
      </Parameter>
      <Parameter Name="Values">
        <Structure Type="List">
          <Item>Value1</Item>
          <Item>Value2</Item>
        </Structure>
      </Parameter>
      <Parameter Name="Index">0</Parameter>
      <Parameter Name="FireChanged">False</Parameter>
    </Parameters>
  </Property>
</DataConnection>
```

Параметр **ColumnNames** ожидает линейный массив названий полей DataConnection.

Параметр **Values** ожидает линейный массив любых значений, которые будут записаны в соответствующие поля новой строки.

Необязательный параметр **Index** ожидает неотрицательное целочисленное значение, указывающее место вставки новой строки. Если параметр отсутствует, то строка добавляется в конец таблицы DataConnection.

Необязательный параметр **FireChanged** - признак того, что соединение с данными будет рассылать событие об изменении данных при выполнении set-проперти. Ожидается логическое значение. По умолчанию используется значение True.

### AddRows <a href="#set_add_rows" id="set_add_rows"></a>

Добавляет новые строки в таблицу DataConnection.

```xml
<DataConnection Name="PrimaryGetDataConnectionName">
  <Property Name="AddRows">
    <Parameters>
      <Parameter Name="ColumnNames">
        <Structure Type="List">
          <Item>ColumnName1</Item>
          <Item>ColumnName2</Item>
        </Structure>
      </Parameter>
      <Parameter Name="Values">
        <DataConnection SourceDataConnection="SourceDataConnectionName">
          <Fields>
            <Field Name="ColumnName1" />
            <Field Name="ColumnName2" />
          </Fields>
        </DataConnection>
      </Parameter>
      <Parameter Name="Index">0</Parameter>
      <Parameter Name="RawValues">True</Parameter>
      <Parameter Name="FireChanged">False</Parameter>
    </Parameters>
  </Property>
</DataConnection>
```

Параметр **ColumnNames** ожидает линейный массив названий полей DataConnection.

Параметр **Values** ожидает таблицу (например, ссылка на GetDataConnection) с числом столбцов равным числу имен столбцов, указанных в параметре ColumnNames. Допустимо указывать линейный массив, который будет соответствовать одной строке.

Необязательный параметр **Index** ожидает неотрицательное целочисленное значение, указывающее место вставки новой строки. Если параметр отсутствует, то строка добавляется в конец таблицы DataConnection.

Необязательный параметр **RawValues** - признак того, что значения необходимо подставлять "как они есть" - без преобразования в массив скалярных значений. Ожидается логическое значение. По умолчанию используется значение False.

Необязательный параметр **FireChanged** - признак того, что соединение с данными будет рассылать событие об изменении данных при выполнении set-проперти. Ожидается логическое значение. По умолчанию используется значение True.

### UpdateRow <a href="#set_update_row" id="set_update_row"></a>

Изменяет значения полей в строке с указанным индексом.

```xml
<DataConnection Name="PrimaryGetDataConnectionName">
  <Property Name="UpdateRow">
    <Parameters>
      <Parameter Name="RowIndex">0</Parameter>
      <Parameter Name="ColumnNames">
        <Structure Type="List">
          <Item>ColumnName1</Item>
          <Item>ColumnName2</Item>
        </Structure>
      </Parameter>
      <Parameter Name="Values">
        <Structure Type="List">
          <Item>Value1</Item>
          <Item>Value2</Item>
        </Structure>
      </Parameter>
      <Parameter Name="RawValues">True</Parameter>
      <Parameter Name="FireChanged">False</Parameter>
    </Parameters>
  </Property>
</DataConnection>
```

Параметр **ColumnNames** ожидает линейный массив названий полей DataConnection.

Параметр **Values** ожидает линейный массив любых значений.

Параметр **RowIndex** ожидает неотрицательное целочисленное значение, указывающее на индекс строки для изменения.

Необязательный параметр **RawValues** - признак того, что значения необходимо подставлять "как они есть" - без преобразования в массив скалярных значений. Ожидается логическое значение. По умолчанию используется значение False.

Необязательный параметр **FireChanged** - признак того, что соединение с данными будет рассылать событие об изменении данных при выполнении set-проперти. Ожидается логическое значение. По умолчанию используется значение True.

### UpdateRows <a href="#set_update_rows" id="set_update_rows"></a>

Изменяет значения полей в строках с указанными индексами на соответствующее значение из массива.

```xml
<DataConnection Name="PrimaryGetDataConnectionName">
  <Property Name="UpdateRows">
    <Parameters>
      <Parameter Name="RowIndices">
        <Structure Type="List">
          <Item>1</Item>
          <Item>2</Item>
        </Structure>
      </Parameter>
      <Parameter Name="ColumnNames">
        <Structure Type="List">
          <Item>ColumnName1</Item>
          <Item>ColumnName2</Item>
        </Structure>
      </Parameter>
      <Parameter Name="Values">
        <Structure Type="List">
          <Item>Value1</Item>
          <Item>Value2</Item>
        </Structure>
      </Parameter>
      <Parameter Name="ReplicateValues">False</Parameter>
      <Parameter Name="RawValues">True</Parameter>
      <Parameter Name="FireChanged">False</Parameter>
    </Parameters>
  </Property>
</DataConnection>
```

Параметр **ColumnNames** ожидает линейный массив названий полей DataConnection.

Параметр **Values** ожидает линейный массив или матрицу любых значений.

Параметр **RowIndices** ожидает линейный массив неотрицательных целочисленных значений, указывающих на индексы строк для изменения.

Необязательный параметр **ReplicateValues** - признак, определяющий каким образом обрабатывать значение параметра Values. Ожидает логическое значение. По умолчанию используется значение True.

Если значение параметра _False_, то значение параметра Values рассматривается как _матрица значений_, которые будут записаны в строки с индексами, указанными в параметре RowIndices. При этом:

* если количество элементов строки матрицы не совпадает с количеством полей, указанных в параметре ColumnNames, то в соответствующие ячейки ставится значение NULL;&#x20;
* если количество строк матрицы не совпадает с количеством индексов, указанных в параметре RowIndices, то в ячейки строки, у которых отсутствует строка в матрице, ставится значение NULL.

Если значение параметра _True_, то значение параметра Values рассматривается как _линейный массив значений_, который заполняет каждую строку, подставляя элементы в соответствующие колонки.

Необязательный параметр **RawValues** - признак того, что значения необходимо подставлять "как они есть" - без преобразования в массив скалярных значений. Ожидается логическое значение. По умолчанию используется значение False.

Необязательный параметр **FireChanged** - признак того, что соединение с данными будет рассылать событие об изменении данных при выполнении set-проперти. Ожидается логическое значение. По умолчанию используется значение True.

### UpdateColumn <a href="#set_update_column" id="set_update_column"></a>

Построчно изменяет значения строк в заданном поле на соответствующие значения из массива.

```xml
<DataConnection Name="PrimaryGetDataConnectionName">
  <Property Name="UpdateColumn">
    <Parameters>
      <Parameter Name="ColumnName">ColumnName</Parameter>
      <Parameter Name="Values">
        <Structure Type="List">
          <Item>Value1</Item>
          <Item>Value2</Item>
        </Structure>
      </Parameter>
      <Parameter Name="RawValues">True</Parameter>
      <Parameter Name="FireChanged">False</Parameter>
    </Parameters>
  </Property>
</DataConnection>
```

Параметр **ColumnName** ожидает название поля DataConnection.

Параметр **Values** ожидает линейный массив любых значений. Если длина массива меньше количества строк в соединении с данными, то оставшиеся строки не будут изменяться. Если длина массива больше, то оставшиеся значения будут отброшены.

Необязательный параметр **RawValues** - признак того, что значения необходимо подставлять "как они есть" - без преобразования в массив скалярных значений. Ожидается логическое значение. По умолчанию используется значение False.

Необязательный параметр **FireChanged** - признак того, что соединение с данными будет рассылать событие об изменении данных при выполнении set-проперти. Ожидается логическое значение. По умолчанию используется значение True.

### UpdateColumnCellsValues <a href="#set_update_column_cells_values" id="set_update_column_cells_values"></a>

Изменяет значение поля в строках с указанными индексами на заданное значение.

```xml
<DataConnection Name="PrimaryGetDataConnectionName">
  <Property Name="UpdateColumnCellsValues">
    <Parameters>
      <Parameter Name="ColumnName">ColumnName</Parameter>
      <Parameter Name="RowIndices">
        <Structure Type="List">
          <Item>1</Item>
          <Item>2</Item>
        </Structure>
      </Parameter>
      <Parameter Name="Value">Value</Parameter>
      <Parameter Name="RawValues">True</Parameter>
      <Parameter Name="FireChanged">False</Parameter>
    </Parameters>
  </Property>
</DataConnection>
```

Параметр **ColumnName** ожидает название поля DataConnection.

Параметр **Value** ожидает значение, которое будет подставляться в поле.

Необязательный параметр **RowIndices** ожидает линейный массив неотрицательных целочисленных значений, указывающих на индексы строк. Если параметр не указан, то обновятся все строки.

Необязательный параметр **FireChanged** - признак того, что соединение с данными будет рассылать событие об изменении данных при выполнении set-проперти. Ожидается логическое значение. По умолчанию используется значение True.

### DeleteRowsByIndices <a href="#set_delete_rows_by_indices" id="set_delete_rows_by_indices"></a>

Удаляет строки с указанными индексами.

```xml
<DataConnection Name="PrimaryGetDataConnectionName">
  <Property Name="UpdateColumnCellsValues">
    <Parameters>
      <Parameter Name="Value">
        <Structure Type="List">
          <Item>1</Item>
          <Item>2</Item>
        </Structure>
      </Parameter>
      <Parameter Name="FireChanged">False</Parameter>
    </Parameters>
  </Property>
</DataConnection>
```

Необязательный параметр **Value** ожидает линейный массив неотрицательных целочисленных значений. Если параметр отсутствует, то удаляются все строки.

Необязательный параметр **FireChanged** - признак того, что соединение с данными будет рассылать событие об изменении данных при выполнении set-проперти, а так же будет изменяться свойство ValueChanged. Ожидается логическое значение. По умолчанию используется значение True.

### FireChanged <a href="#set_fire_changed" id="set_fire_changed"></a>

Рассылает событие об изменении данных.

Значение не ожидается.

```xml
<DataConnection Name="PrimaryGetDataConnectionName">
  <Property Name="FireChanged" />
</DataConnection>
```

### ValueChanged <a href="#set_value_changed" id="set_value_changed"></a>

Задает признак изменения значения соединения с данными.

Ожидается логическое значение.

```xml
<DataConnection Name="PrimaryGetDataConnectionName">
  <Property Name="ValueChanged">False</Property>
</DataConnection>
```
