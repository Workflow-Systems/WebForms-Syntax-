---
description: Используется для отображения данных в виде текста
---

# ColumnTextBox

## Шаблон DatabaseTableColumnTextBox <a href="#template_databasetable" id="template_databasetable"></a>

Перечень всех возможных тэгов столбца:

```xml
<Column Name="" Type="DatabaseTableColumnTextBox" Assembly="DatabaseTableColumnControls" ><Column Name="" Type="DatabaseTableColumnTextBox" Assembly="DatabaseTableColumnControls" >
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
  <!--Тэги, специфичные для DatabaseTableColumnTextBox-->
  <!--Отсутствуют-->
</Column>
```

{% hint style="info" %}
Тэги, общие для всех типов столбцов описаны в статье [Column](./).
{% endhint %}
