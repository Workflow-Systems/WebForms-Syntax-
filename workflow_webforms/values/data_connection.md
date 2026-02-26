---
description: Обращение к соединению с данными для получения.
---

# DataConnection

## Шаблоны DataConnection <a href="#template_data_connection" id="template_data_connection"></a>

```xml
<DataConnection SourceDataConnection="" GetScalar="">
  <Fields>
    <Field Name="" />
  </Fields>
</DataConnection>
```

```xml
<DataConnection SourceDataConnection="" SourceSqlQuery="" GetScalar="">
  <Fields>
    <Field Name="" />
  </Fields>
</DataConnection>
```

```xml
<DataConnection SourceDataConnection="" GetScalar="">
  <SourceQuery Name="">
    <Fields>
      <Field Name="" />
      <Field Name="" />
    </Fields>
  </SourceQuery>
  <SourceQuery Name="">
    <Fields>
      <Field Name="" />
      <Field Name="" />
      <Field Name="" />
    </Fields>
  </SourceQuery>
</DataConnection>
```

#### Атрибуты DataConnection <a href="#attributes_data_connection" id="attributes_data_connection"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="431.3333333333333"></th></tr></thead><tbody><tr><td align="center">GetScalar</td><td><p>Признак, определяющий результат соединения с данными.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>Если атрибут <code>GetScalar</code> отсутствует или значение атрибута False, то значением будет массив строк соединения.</p><p>Если значение - True, то значение - первый элемент первой строки или NULL, если в соединении с данными отсутствуют строки.</p></td></tr></tbody></table>
