---
description: Структура данных.
---

# Structure

### Шаблон Structure List <a href="#list" id="list"></a>

Массив элементов.

```markup
<Structure Type="List">
  <Item></Item>
  <Item></Item>
  <Item></Item>
</Structure>
```

### Шаблон Structure Table <a href="#table" id="table"></a>

Матрица элементов, выстроенная по принципу таблицы: состоит из строк, которые состоят из определенного количества значений, соответствующих столбцам.

Количество элементов в каждой строке должно быть одинаковым.

```markup
<Structure Type="Table">
  <Row>
    <Item></Item>
    <Item></Item>
  </Row>
  <Row>
    <Item></Item>
    <Item></Item>
  </Row>
</Structure>
```

### Шаблон Structure DataTable <a href="#data_table" id="data_table"></a>

Похожа на Table, только столбцы имеют имена и каждая строка может содержать значений только из определенных столбцов (каких именно - указывается в атрибуте `Name` тэга `<Column>`).

```markup
<Structure Type="DataTable">
  <Row>
    <Column Name=""></Column>
    <Column Name=""></Column>
  </Row>
  <Row>
    <Column Name=""></Column>
    <Column Name=""></Column>
  </Row>
</Structure>
```

### Шаблон Structure Dictionary <a href="#dictionary" id="dictionary"></a>

Словарь соответствий "Ключ" - "Значение".

```markup
<Structure Type="Dictionary">
  <Key Name=""></Key>
  <Key Name=""></Key>
</Structure>
```
