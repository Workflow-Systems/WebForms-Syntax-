# ColumnImageBox

## Шаблон DatabaseTableColumnImageBox <a href="#template_databasetable" id="template_databasetable"></a>

Перечень всех возможных тэгов столбца:

```xml
<Column Name="" Type="DatabaseTableColumnImageBox" Assembly="DatabaseTableColumnControls" >
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
  <!--Тэги, специфичные для DatabaseTableColumnImageBox-->
</Column>
```

{% hint style="info" %}
Тэги, общие для всех типов столбцов описаны в статье [Column](./).
{% endhint %}

## Описание ColumnImageBox

В качестве источника изображения в ячейке используется значение ячейки.

Ожидается либо Guid изображения, либо полный путь - в случае, если Engine и Workflow WebForms запущены на одном компьютере и соответствующая настройка указана в конфигурационном файле WebForms.
