# Array

## Шаблон Array <a href="#template_input" id="template_input"></a>

Минимальный шаблон

```xml
<Array>
    <!-- Источник массива -->
    <Source></Source>
    <!-- Получение индекса первого элемента. -->
    <Filter>
        <Not>
            <And>
                <Or>
                    <Filter Type="Equal">
                        <!-- или Field (для DC) или Index (для массивов)-->
                        <Field></Field>
                        <Index></Index>
                        <DataType Type=""></DataType>
                        <Value></Value>
                    </Filter>
                </Or>
            </And>
        </Not>
    </Filter>
    <!-- Уникальные элементы в массиве. Если теги On не указаны, используется первый элемент -->
    <Distinct>
      <On Index="" />
    </Distinct>
    <!-- Сортировка. Если теги By не указаны, используется первый элемент и сортируется по возрастанию  -->
    <Order>
      <By Index="" Type="Asc" />
      <By Index="" Type="Desc" />
    </Order>
    <!-- Создать новый массив на основе существующего. Если Items.Count == 1 то возвращает одномерный массив -->
    <Select>
        <Items>
            <!-- Элемент массива -->
            <Item Type="Index"></Item>
            <!-- Выбор из словаря -->
            <Item Type="Field"><!-- название элемента словаря --></Item>
            <!-- Скалярное значение -->
            <Item Type="Value"></Item>
            <!-- Порядковый номер элемента массива -->
            <Item Type="Number" Start="0"></Item>
            <!-- Форматирование значений -->
            <Item Type="Format"></Item>
            <!-- Работа с вложенными массивами -->
            <Item Type="Action">
                <Index><!-- индекс элемента массива --></Index>
                <Actions><!-- цепочка действий. Доступны все действия над массивами--></Actions>
            </Item>
            <!-- Расчет выражения -->
            <Item Type="Expression">
                <!-- В выражении могут использоваться элементы массива ([0]) и дополнительные значения ({0}).-->
                <!-- Дополнительно можно добавить переменную Index -->
                <Expression>{0} > 0</Expression>
                <Items>
                    <!-- Дополнительные значения -->
                    <Item></Item>
                </Items>
            </Item>
            <!-- Подстановка значений -->
            <Item>
                <Index><!-- индекс элемента массива --></Index>
                <Value><!-- таблица значений --></Value>
            </Item>
        </Items>
    </Select>    
</Array>
```

<details>

<summary>Полный шаблон Array</summary>

```xml
<Array>
    <!-- Источник массива -->
    <Source></Source>
    <!-- Добавить в массив значение и вернуть новый массив -->
    <Add></Add>
    <!-- Возвращает элемент массива. Для одномерного массива возвращается скалярное значение. Для многомерного - одномерный массив значений -->
    <ElementAt>
        <Index><!-- value --></Index>
    </ElementAt>
    <!-- Удаление элементов из массива -->
    <Remove>
        <!-- Для удаления одного элемента -->
        <Index></Index>
        <!-- Для удаления нескольких элементов -->
        <Indices>
            <Index></Index>
        </Indices>
        <Structure Type="List">
            <Item></Item>
            <Item></Item>
            <Item></Item>
        </Structure>
    </Remove>
    <!-- Обновить элемент по индексу -->
    <Update>
        <Index></Index>
        <!-- Для одномерного массива -->
        <Value></Value>
        <!-- Для многомерных массивов -->
        <Value>
            <Row>
                <Item></Item>
            </Row>
        </Value>
    </Update>
    <!-- Создать новый массив на основе существующего. Операция Map. Если Items.Count == 1 то возвращает одномерный массив -->
    <Select>
        <Items>
            <Item Type="Expression">
                <!-- В выражении могут использоваться элементы массива ([0]) и дополнительные значения ({0}).-->
                <!-- Дополнительно можно добавить переменную Index -->
                <Expression>{0} > 0</Expression>
                <Items>
                    <Item></Item>
                <Items>
            </Item>
            <!-- Скалярное значение -->
            <Item Type="Value"></Item>
            <!-- Элемент массива -->
            <Item Type="Index"></Item>
            <!-- Порядковый номер элемента массива -->
            <Item Type="Number" Start="0"></Item>
            <!-- Форматирование значений -->
            <Item Type="Format"></Item>
            <!-- Работа с вложенными массивами -->
            <Item Type="Action">
                <Index><!-- индекс элемента массива --></Index>
                <Actions><!-- цепочка действий. Доступны все действия над массивами--></Actions>
            </Item>
            <!-- Подстановка значений -->
            <Item>
                <Index><!-- индекс элемента массива --></Index>
                <Value><!-- таблица значений --></Value>
            </Item>
            <!-- Выбор из словаря -->
            <Item Type="Field"><!-- название элемента словаря --></Item>
        </Items>
    </Select>
    <!-- Агрегация значений. Операция Reduce/Fold. Для одного элемента - скаляр. Для нескольких элементов одномерный массив значений -->
    <Aggregate>
        <Items>
            <Item>
                <!-- Начальное значение -->
                <Result>0</Result>
                <!-- В выражении могут использоваться элементы массива ([0]) и дополнительные значения ({0}).-->
                <!-- Дополнительно можно добавить переменную Index -->
                <!-- Полученный результат сохраняется в Result и вычисляется значение для следующей строки -->
                <!-- Пример расчёта суммы -->
                <Expression>{Result} + {0}</Expression>
                <Items>
                    <Item></Item>
                <Items>
            </Item>
        </Items>
    </Aggregate>
    <!-- Максимальный элемент. Только для одномерных массивов -->
    <Max Type="" />
    <!-- Минимальный элемент. Только для одномерных массивов -->
    <Min Type="" />
    <!-- Получение индекса первого элемента. -->
    <Filter>
        <Not>
            <And>
                <Or>
                    <Filter Type="Equal">
                        <!-- или Field (для DC) или Index (для массивов)-->
                        <Field></Field>
                        <Index></Index>
                        <DataType Type=""></DataType>
                        <Value></Value>
                    </Filter>
                </Or>
            </And>
        </Not>
    </Filter>
    <!-- Первый элемент -->
    <First />
    <!-- Последний элемент -->
    <Last />
    <!-- Форматирует текущий массив в строку -->
    <!-- Если элемент массива Dictionary<string, object>, то доступны поля по {Key}. Для одномерных массивов {0}, {1} -->
    <Format></Format>
    <!-- Объединяет текущий массив в строку с разделителем -->
    <StringJoin Separator="<!-- разделитель элементов -->" LineSeparator="<!-- разделитель строк -->" />
    <!-- Пропустить N строк -->
    <Skip></Skip>
    <!-- Взять из массива N строк -->
    <Take></Take>
    <!-- Количество элементов в массиве -->
    <Count />
    <!-- Уникальные элементы в массиве. Если теги On не указаны, используется первый элемент -->
    <Distinct>
      <On Index="" />
    </Distinct>
    <!-- Индекс элемента (только для одномерных массивов) -->
    <!-- Содержимое тега аналогично тегу Filter -->
    <IndexOf></IndexOf>
    <!-- Преобразовать одномерный массив в многомерный. Для многомерных ничего не делается -->
    <ToTable />
    <!-- Преобразование значение в одномерный массив -->
    <ToArray />
    <!-- Преобразование двухмерного массива в массив словарей -->
    <ToDictionary>
        <!-- Атрибут Name: название элемента словаря -->
        <!-- Атрибут Index: индекс элемента массива, который будет записан в словарь под именем указанным в атрибуте Name -->
        <Key Name="" Index=""/>
    </ToDictionary>
    <!-- Сортировка (только для одномерных массивов) -->
    <Sort />
    <!-- Сортировка. Если теги By не указаны, используется первый элемент и сортируется по возрастанию  -->
    <Order>
      <By Index="" Type="Asc" />
      <By Index="" Type="Desc" />
    </Order>
    <!-- Объединение массивов -->
    <Union><!-- массив --></Union>
    <!-- Для ConvertDC. Для массива Dictionary<string, object> формирует массив из значений словаря по указанному ключу -->
    <Field><!-- field name --></Field>
    <!-- Преобразовать массив массивов ([[1,2,3,...], [4,5,...]]) в одномерный ([1,2,3,...,4,5,...]) -->
    <SelectMany></SelectMany>
    
    <!--Объединения массивов по ключам-->
	<!-- Inner - текущий массив, Outer - массив с которыем будет соединён текущий -->
    <Join>
      <OuterArray><!-- массив с которым будет текущий соединён--></OuterArray>
	  <!--Ключи по которым будуд соединяться массивы-->
      <Keys>
		<!-- Атрибут Index: индекс элемента массива, который будет использоваться в качестве составного ключа -->
		<!-- Количество тегов Inner и Outer должно совпадать -->
        <Inner Index="" />
        <Inner Index="" />
        <Outer Index="" />
        <Outer Index="" />
      </Keys>
	  <!-- Результат объединения -->
      <Result>
	    <!-- Атрибут Index: индекс элемента массива, который будет добавлен в результирующую строку. Если тег Inner, то значение будет выбрано из исходного массива. Если Outer, то из массива из тега OuterArray -->
        <Inner Index="" />
        <Inner Index="" />
        <Outer Index="" />
        <Outer Index="" />
      </Result>
    </Join>
	<!-- Левостороннее соединение -->
    <LeftJoin>
      <OuterArray></OuterArray>
      <Keys>
        <Inner Index="" />
        <Inner Index="" />
        <Outer Index="" />
        <Outer Index="" />
      </Keys>
      <Result>
        <Inner Index="" />
        <Inner Index="" />
        <Outer Index="" />
        <Outer Index="" />
      </Result>
    </LeftJoin>
	<!-- Правостороннее соединение -->
    <RightJoin>
      <OuterArray></OuterArray>
      <Keys>
        <Inner Index="" />
        <Inner Index="" />
        <Outer Index="" />
        <Outer Index="" />
      </Keys>
      <Result>
        <Inner Index="" />
        <Inner Index="" />
        <Outer Index="" />
        <Outer Index="" />
      </Result>
    </RightJoin>
	<!-- Полное соединение -->
    <FullJoin>
      <OuterArray></OuterArray>
      <Keys>
        <Inner Index="" />
        <Inner Index="" />
        <Outer Index="" />
        <Outer Index="" />
      </Keys>
      <Result>
        <Inner Index="" />
        <Inner Index="" />
        <Outer Index="" />
        <Outer Index="" />
      </Result>
    </FullJoin>
    
</Array>
```

</details>

## Описание Array <a href="#description_input" id="description_input"></a>

Значение, которое будет передано в команду при выполнении.

```xml
<Array>
  <Source></Source>
  <Operation1></Operation1>
  <Operation2></Operation2>
</Array>
```

В тэге `<Source>` указывается любое универсальное значение, с которым выполняются операции указанные после тэга `<Source>` _-_ Operation1, Operation2. Операций может быть неограниченное количество. При этом **операции будут выполняться последовательно в порядке объявления**: для первой операции (_Operation1_) используется значение из тэга `<Source>`, для последующих операций - результат предыдущей операции.

Все операции можно разделить на группы:

* Изменение
* Агрегация
* Поиск
* Соединение
* Выборка из массива
* Преобразование
* Сортировка

## Изменение

### Add

Добавляет элемент или элементы в массив.

```xml
<Add><!-- элементы для добавления --></Add>
```

При добавлении элементов используются следующие правила:

* **Матрица добавляется в Матрицу**\
  Строки из матрицы, указанной в тэге `<Value>`, добавляются в конец матрицы из тэга `<Source>`.

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>Text 1</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>Text 2</Item>
      </Row>
    </Structure>
  </Source>
  <Add>
    <Structure Type="Table">
      <Row>
        <Item>3</Item>
        <Item>Text 3</Item>
      </Row>
      <Row>
        <Item>4</Item>
        <Item>Text 4</Item>
      </Row>
    </Structure>
  </Add>
</Array>
```

Результат:

```
+-----+----------+
|  1  |  Text 1  |
|  2  |  Text 2  |
|  3  |  Text 3  |
|  4  |  Text 4  |
+-----+----------+
```

</details>

* **Массив добавляется в Матрицу**\
  В массив из тэга `<Value>` добавляются пустые элементы, чтобы длина массива соответствовала наибольшей длине строки матрицы, указанной в тэге `<Source>`, и полученный массив добавляются в конец матрицы.

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>True</Item>
        <Item>Text 1</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>False</Item>
        <Item>Text 2</Item>
      </Row>
    </Structure>
  </Source>
  <Add>
    <Structure Type="List">
      <Item>3</Item>
      <Item>False</Item>
    </Structure>
  </Add>
</Array>
```

Результат:

```
+-----+---------+----------+
|  1  |  True   |  Text 1  |
|  2  |  False  |  Text 2  |
|  3  |  False  |          |
+-----+---------+----------+
```

</details>

* **Скаляр добавляется в Матрицу**\
  Скаляр из тэга `<Value>` преобразуется в массив с длиной соответствующей наибольшей длине строки матрицы, указанной в тэге `<Source>`_,_ и полученный массив добавляются в конец матрицы.

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>True</Item>
        <Item>Text 1</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>False</Item>
        <Item>Text 2</Item>
      </Row>
    </Structure>
  </Source>
  <Add>3</Add>
</Array>
```

Результат:

```
+-----+---------+----------+
|  1  |  True   |  Text 1  |
|  2  |  False  |  Text 2  |
|  3  |         |          |
+-----+---------+----------+
```

</details>

* **Матрица добавляется в Массив**\
  Первый столбец матрицы, указанной в тэге `<Value>`, преобразуется в массив и добавляется в конец массива из тэга `<Source>`.

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>1</Item>
      <Item>2</Item>
    </Structure>
  </Source>
  <Add>
    <Structure Type="Table">
      <Row>
        <Item>3</Item>
        <Item>Text 3</Item>
      </Row>
      <Row>
        <Item>4</Item>
        <Item>Text 4</Item>
      </Row>
    </Structure>
  </Add>
</Array>
```

Результат:

```
+-----+-----+-----+-----+
|  1  |  2  |  3  |  4  |
+-----+-----+-----+-----+
```

</details>

* **Массив добавляется в Массив**\
  Массив из тэга `<Value>` добавляется в конец массива, указанного в тэге `<Source>`.

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>1</Item>
      <Item>2</Item>
    </Structure>
  </Source>
  <Add>
    <Structure Type="List">
      <Item>3</Item>
      <Item>4</Item>
    </Structure>
  </Add>
</Array>
```

Результат:

```
+-----+-----+-----+-----+
|  1  |  2  |  3  |  4  |
+-----+-----+-----+-----+
```

</details>

* **Скаляр добавляется в Массив**\
  Скаляр из тэга `<Value>` добавляется в конец массива, указанного в тэге `<Source>`.

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>1</Item>
      <Item>2</Item>
    </Structure>
  </Source>
  <Add>3</Add>
</Array>
```

Результат:

```
+-----+-----+-----+
|  1  |  2  |  3  |
+-----+-----+-----+
```

</details>

* Во всех случаях, когда в качестве значения тэга `<Source>` указан **скаляр**, будет генерироваться ошибка **TypeMismatch**.

### InsertAt <a href="#insert_at" id="insert_at"></a>

Добавляет элемент или элементы в массив в указанную позицию.

```xml
<InsertAt>
  <Index><!-- индекс элемента --></Index>
  <Value><!-- элементы для добавления --></Value>
</InsertAt>
```

При добавлении элементов используются следующие правила:

* **Матрица добавляется в Матрицу**\
  Строки из матрицы, указанной в тэге `<Value>`, добавляются в конец матрицы из тэга `<Source>`.

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>Text 1</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>Text 2</Item>
      </Row>
    </Structure>
  </Source>
  <InsertAt>
    <Index>1</Index>
    <Value>
      <Structure Type="Table">
        <Row>
          <Item>3</Item>
          <Item>Text 3</Item>
        </Row>
        <Row>
          <Item>4</Item>
          <Item>Text 4</Item>
        </Row>
      </Structure>
    </Value>
  </InsertAt>
</Array>
```

Результат:

```
+-----+----------+
|  1  |  Text 1  |
|  3  |  Text 3  |
|  4  |  Text 4  |
|  2  |  Text 2  |
+-----+----------+
```

</details>

* **Массив добавляется в Матрицу**\
  В массив из тэга `<Value>` добавляются пустые элементы, чтобы длина массива соответствовала наибольшей длине строки матрицы, указанной в тэге `<Source>`, и полученный массив добавляются в конец матрицы.

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>True</Item>
        <Item>Text 1</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>False</Item>
        <Item>Text 2</Item>
      </Row>
    </Structure>
  </Source>
  <InsertAt>
    <Index>1</Index>
    <Value>
      <Structure Type="List">
        <Item>3</Item>
        <Item>False</Item>
      </Structure>
    </Value>
  </InsertAt>
</Array>
```

Результат:

```
+-----+---------+----------+
|  1  |  True   |  Text 1  |
|  3  |  False  |          |
|  2  |  False  |  Text 2  |
+-----+---------+----------+
```

</details>

* **Скаляр добавляется в Матрицу**\
  Скаляр из тэга `<Value>` преобразуется в массив с длиной соответствующей наибольшей длине строки матрицы, указанной в тэге `<Source>`_,_ и полученный массив добавляются в конец матрицы.

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>True</Item>
        <Item>Text 1</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>False</Item>
        <Item>Text 2</Item>
      </Row>
    </Structure>
  </Source>
  <InsertAt>
    <Index>0</Index>
    <Value>3</Value>
  </InsertAt>
</Array>
```

Результат:

```
+-----+---------+----------+
|  3  |         |          |
|  1  |  True   |  Text 1  |
|  2  |  False  |  Text 2  |
+-----+---------+----------+
```

</details>

* **Матрица добавляется в Массив**\
  Первый столбец матрицы, указанной в тэге `<Value>`, преобразуется в массив и добавляется в конец массива из тэга `<Source>`.

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>1</Item>
      <Item>2</Item>
    </Structure>
  </Source>
  <InsertAt>
    <Index>1</Index>
    <Value>
      <Structure Type="Table">
        <Row>
          <Item>3</Item>
          <Item>Text 3</Item>
        </Row>
        <Row>
          <Item>4</Item>
          <Item>Text 4</Item>
        </Row>
      </Structure>
    </Value>
  </InsertAt>
</Array>
```

Результат:

```
+-----+-----+-----+-----+
|  1  |  3  |  4  |  2  |
+-----+-----+-----+-----+
```

</details>

* **Массив добавляется в Массив**\
  Массив из тэга `<Value>` добавляется в конец массива, указанного в тэге `<Source>`.

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>1</Item>
      <Item>2</Item>
    </Structure>
  </Source>
  <InsertAt>
    <Index>0</Index>
    <Value>
      <Structure Type="List">
        <Item>3</Item>
        <Item>4</Item>
      </Structure>
    </Value>
  </InsertAt>
</Array>
```

Результат:

```
+-----+-----+-----+-----+
|  3  |  4  |  1  |  2  |
+-----+-----+-----+-----+
```

</details>

* **Скаляр добавляется в Массив**\
  Скаляр из тэга `<Value>` добавляется в конец массива, указанного в тэге `<Source>`.

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>1</Item>
      <Item>2</Item>
    </Structure>
  </Source>
  <InsertAt>
    <Index>0</Index>
    <Value>3</Value>
  </InsertAt>
</Array>
```

Результат:

```
+-----+-----+-----+
|  3  |  1  |  2  |
+-----+-----+-----+
```

</details>

* Во всех случаях, когда в качестве значения тэга `<Source>` указан **скаляр**, будет генерироваться ошибка **TypeMismatch**.

### Update

Обновляет элемент в массиве/матрице в указанной позиции.

```xml
<Update>
  <Index><!-- индекс элемента --></Index>
  <Value><!-- элемент для обновления --></Value>
</Update>
```

При обновлении элементов используются следующие правила:

* **Массив добавляется в Матрицу**\
  В массив из тэга `<Value>` добавляются пустые элементы, чтобы длина массива соответствовала наибольшей длине строки матрицы, указанной в тэге `<Source>`, и полученный массив записывается в элемент с индексом `<Index>`.

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>True</Item>
        <Item>Text 1</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>False</Item>
        <Item>Text 2</Item>
      </Row>
    </Structure>
  </Source>
  <Update>
    <Index>0</Index>
    <Value>
      <Structure Type="List">
        <Item>3</Item>
        <Item>False</Item>
      </Structure>
    </Value>
  </Update>
</Array>
```

Результат:

```
+-----+---------+----------+
|  3  |  False  |          |
|  2  |  False  |  Text 2  |
+-----+---------+----------+
```

</details>

* **Скаляр добавляется в Матрицу**\
  Скаляр из тэга `<Value>` преобразуется в массив с длиной соответствующей наибольшей длине строки матрицы, указанной в тэге `<Source>`_,_ и полученный массив записывается в элемент с индексом `<Index>`.

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>True</Item>
        <Item>Text 1</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>False</Item>
        <Item>Text 2</Item>
      </Row>
    </Structure>
  </Source>
  <Update>
    <Index>0</Index>
    <Value>3</Value>
  </Update>
</Array>
```

Результат:

```
+-----+---------+----------+
|  3  |         |          |
|  2  |  False  |  Text 2  |
+-----+---------+----------+
```

</details>

* **Матрица добавляется в Массив**\
  Берет первый элемент первой строки матрицы, указанной в тэге `<Value>`, и записывается в элемент с индексом `<Index>` массива из тэга `<Source>`.

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>1</Item>
      <Item>2</Item>
    </Structure>
  </Source>
  <Update>
    <Index>0</Index>
    <Value>
      <Structure Type="Table">
        <Row>
          <Item>3</Item>
          <Item>Text 3</Item>
        </Row>
        <Row>
          <Item>4</Item>
          <Item>Text 4</Item>
        </Row>
      </Structure>
    </Value>
  </Update>
</Array>
```

Результат:

```
+-----+-----+
|  3  |  2  |
+-----+-----+
```

</details>

* **Массив добавляется в Массив**\
  Берется первый элемент массива из тэга `<Value>` и записывается в элемент с индексом `<Index>` массива, указанном в тэге `<Source>`.

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>1</Item>
      <Item>2</Item>
    </Structure>
  </Source>
  <Update>
    <Index>0</Index>
    <Value>
      <Structure Type="List">
        <Item>3</Item>
        <Item>4</Item>
      </Structure>
    </Value>
  </Update>
</Array>
```

Результат:

```
+-----+-----+
|  3  |  2  |
+-----+-----+
```

</details>

* **Скаляр добавляется в Массив**\
  Скаляр из тэга `<Value>` записывается в элемент с индексом `<Index>` массива, указанного в тэге `<Source>`.

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>1</Item>
      <Item>2</Item>
    </Structure>
  </Source>
  <Update>
    <Index>0</Index>
    <Value>3</Value>
  </Update>
</Array>
```

Результат:

```
+-----+-----+
|  3  |  2  |
+-----+-----+
```

</details>

* Во всех случаях, когда в качестве значения тэга `<Source>` указан **скаляр**, будет генерироваться ошибка **TypeMismatch**.

### Remove

Удаляет элемент(ы) по индексу или индексам.

```xml
<Remove><!-- индекс или массив индексов --></Remove>
```

{% hint style="warning" %}
Если в качестве значения тэга `<Source>` указан **скаляр**, то будет генерироваться ошибка **TypeMismatch**.
{% endhint %}

<details>

<summary>Пример 1. Удаление элемента из матрицы</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>Text 1</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>Text 2</Item>
      </Row>
      <Row>
        <Item>3</Item>
        <Item>Text 3</Item>
      </Row>
    </Structure>
  </Source>
  <Remove>1</Remove>
</Array>
```

Результат:

```
+-----+----------+
|  1  |  Text 1  |
|  3  |  Text 3  |
+-----+----------+
```

</details>

<details>

<summary>Пример 2. Удаление элемента из массива</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>1</Item>
      <Item>2</Item>
      <Item>3</Item>
    </Structure>
  </Source>
  <Remove>1</Remove>
</Array>
```

Результат:

```
+-----+-----+
|  1  |  3  |
+-----+-----+
```

</details>

<details>

<summary>Пример 3. Удаление элементов из матрицы</summary>

```xml
<<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>Text 1</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>Text 2</Item>
      </Row>
      <Row>
        <Item>3</Item>
        <Item>Text 3</Item>
      </Row>
      <Row>
        <Item>4</Item>
        <Item>Text 4</Item>
      </Row>
    </Structure>
  </Source>
  <Remove>
    <Structure Type="List">
      <Item>0</Item>
      <Item>2</Item>
    </Structure>
  </Remove>
</Array>
```

Результат:

```
+-----+----------+
|  2  |  Text 2  |
|  4  |  Text 4  |
+-----+----------+
```

</details>

## Агрегация

### Aggregate

Вычисляет значения по формулам.

```xml
<Aggregate>
  <Items>
    <Item>
      <Result><!-- Начальное значение --></Result>
      <Expression><!-- Выражение для расчёта--></Expression>	
      <Items>
         <!-- Дополнительные значение -->
        <Item></Item>
      <Items>
    </Item>
  </Items>
</Aggregate>
```

В выражении `<Expression>` могут использоваться элементы исходного массива (указываются в квадратных скобках `[]`) или дополнительные значения, перечисленные в тэге `<Items>` (указываются в фигурных скобках `{}`). Также доступна переменная `{Result}`_,_ в которой хранится значение, вычисленное для прошлого элемента.

Если элементов Item в Aggregate/Items несколько, то возвращается массив результатов агрегации. Если один, то скалярное значение.

{% hint style="info" %}
Для вычисления выражений используется **NCalc**.
{% endhint %}

{% hint style="warning" %}
Если в качестве значения тэга `<Source>` указан **скаляр**, то будет генерироваться ошибка **TypeMismatch**.
{% endhint %}

<details>

<summary>Пример 1. Сумма и произведение всех элементов массива</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>1</Item>
      <Item>2</Item>
      <Item>3</Item>
      <Item>4</Item>
    </Structure>
  </Source>
  <Aggregate>
    <Items>
      <Item>
        <Result>0</Result>
        <Expression>{Result} + [0]</Expression>
      </Item>
      <Item>
        <Result>1</Result>
        <Expression>{Result} * [0]</Expression>
      </Item>
    </Items>
  </Aggregate>
</Array>
```

Результат:

```
+------+------+
|  10  |  24  |
+------+------+
```

</details>

<details>

<summary>Пример 2. Сумма произведения элементов матрицы</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>65</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>69</Item>
      </Row>
    </Structure>
  </Source>
  <Aggregate>
    <Items>
      <Item>
        <Result>0</Result>
        <Expression>{Result} + [0] * [1]</Expression>
      </Item>
    </Items>
  </Aggregate>
</Array>
```

Результат:

```
203
```

</details>

### Count

Считает количество элементов в массиве.

```xml
<Count />
```

{% hint style="warning" %}
Если в качестве значения тэга `<Source>` указан **скаляр**, то будет генерироваться ошибка **TypeMismatch**.
{% endhint %}

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>Text 1</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>Text 2</Item>
      </Row>
    </Structure>
  </Source>
  <Count />
</Array>
```

Результат:

```
2
```

</details>

### Max

Находит максимальный элемент в массиве или в столбце матрицы.

```xml
<Max Type="" Index="" />
```

В атрибуте `Type` задаётся один из [типов](../data_types/).

В необязательном атрибуте `Index` для матриц указывается индекс столбца, в котором будет происходить поиск максимального элемента. Если атрибут не указан, то используется значение 0.

{% hint style="warning" %}
Если в качестве значения тэга `<Source>` указан **скаляр**, то будет генерироваться ошибка **TypeMismatch**.
{% endhint %}

<details>

<summary>Пример 1. Максимальный элемент в третьем столбце матрицы</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>Text 1</Item>
        <Item>45</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>Text 2</Item>
        <Item>61</Item>
      </Row>
      <Row>
        <Item>3</Item>
        <Item>Text 3</Item>
        <Item>22</Item>
      </Row>
    </Structure>
  </Source>
  <Max Type="IntegerDataType" Index="2" />
</Array>
```

Результат:

```
61
```

</details>

<details>

<summary>Пример 2. Максимальный элемент массива</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>7</Item>
      <Item>2</Item>
      <Item>10</Item>
      <Item>5</Item>
    </Structure>
  </Source>
  <Max Type="IntegerDataType" />
</Array>
```

Результат:

```
10
```

</details>

### Min

Находит минимальный элемент в массиве или в столбце матрицы.

```xml
<Min Type="" Index="" />
```

В атрибуте `Type` задаётся один из [типов](../data_types/).

В необязательном атрибуте `Index` для матриц указывается индекс столбца, в котором будет происходить поиск минимального элемента. Если атрибут не указан, то используется значение 0.

{% hint style="warning" %}
Если в качестве значения тэга `<Source>` указан **скаляр**, то будет генерироваться ошибка **TypeMismatch**.
{% endhint %}

<details>

<summary>Пример 1. Минимальный элемент в третьем столбце матрицы</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>Text 1</Item>
        <Item>45</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>Text 2</Item>
        <Item>61</Item>
      </Row>
      <Row>
        <Item>3</Item>
        <Item>Text 3</Item>
        <Item>22</Item>
      </Row>
    </Structure>
  </Source>
  <Min Type="IntegerDataType" Index="2" />
</Array>
```

Результат:

```
22
```

</details>

<details>

<summary>Пример 2. Минимальный элемент массива</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>7</Item>
      <Item>2</Item>
      <Item>10</Item>
      <Item>5</Item>
    </Structure>
  </Source>
  <Min Type="IntegerDataType" />
</Array>
```

Результат:

```
2
```

</details>

### Sum

Находит сумму элементов в массиве или в столбце матрицы.

```xml
<Sum Type="" Index="" />
```

В атрибуте `Type` задаётся один из [типов](../data_types/).

В необязательном атрибуте `Index` для матриц указывается индекс столбца, для которого будет вычисляться сумма элементов. Если атрибут не указан, то используется значение 0.

{% hint style="warning" %}
Если в качестве значения тэга `<Source>` указан **скаляр**, то будет генерироваться ошибка **TypeMismatch**.
{% endhint %}

<details>

<summary>Пример 1. Сумма элементов в третьем столбце матрицы</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>Text 1</Item>
        <Item>45</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>Text 2</Item>
        <Item>61</Item>
      </Row>
      <Row>
        <Item>3</Item>
        <Item>Text 3</Item>
        <Item>22</Item>
      </Row>
    </Structure>
  </Source>
  <Sum Type="IntegerDataType" Index="2" />
</Array>
```

Результат:

```
128
```

</details>

<details>

<summary>Пример 2. Сумма элементов массива</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>7</Item>
      <Item>2</Item>
      <Item>10</Item>
      <Item>5</Item>
    </Structure>
  </Source>
  <Sum Type="IntegerDataType" />
</Array>
```

Результат:

```
24
```

</details>

## Поиск

### IndexOf

Возвращает индекс первого элемента массива удовлетворяющего условию.

```xml
<!-- общий синтаксис для поиска -->
<IndexOf Type="">
  <Field Name="" />
  <!-- или -->
  <Index Value="" />
  <Value><!-- значение фильтра --></Value>
  <DataType Type="" />
</IndexOf>
```

В необязательном атрибуте `Type` тэга `<IndexOf>` указывается [тип сравнения значений](array.md#tipy-sravneniya-znachenii). По умолчанию используется фильтр Equal.

Тэг `<Field>` применяется для выборки из массива словарей. В атрибуте `Name` указывается название поля словаря, по которому будет происходить проверка условия.

Тэг `<Index>` применяется для выборки из одномерного массива или матрицы. Для матриц в атрибуте `Value` указывается индекс элемента строки, по которому будет проверка условия.

Тэг [`<DataType>`](../data_types/) задаёт тип элемента. По умолчанию используется тип **StringDataType**.

В зависимости от типа фильтра тэги `<Value>` или `<DataType>` могут отсутствовать. Например, в фильтрах IsNull, IsNotNull.

#### Типы сравнения значений

<table data-header-hidden><thead><tr><th align="center"></th><th width="459.3333333333333"></th></tr></thead><tbody><tr><td align="center">Equal</td><td>Сравнение значений на равенство</td></tr><tr><td align="center">NotEqual</td><td>Сравнение значений на неравенство</td></tr><tr><td align="center">Greater</td><td>Сравнение значений на "больше": элемент массива больше указанного значения</td></tr><tr><td align="center">GreaterOrEqual</td><td>Сравнение значений на "больше или равно": элемент массива больше или равен указанному значению</td></tr><tr><td align="center">Less</td><td>Сравнение значений на "меньше": элемент массива меньше указанного значения</td></tr><tr><td align="center">LessOrEqual</td><td>Сравнение значений на "меньше или равно": элемент массива меньше или равен указанному значению</td></tr><tr><td align="center">Contains</td><td>Сравнение значений на "содержит": элемент массива содержит указанное значение, при этом все значения преобразуется в строку</td></tr><tr><td align="center">NotContains</td><td>Сравнение значений на "не содержит": элемент массива не содержит указанное значение, при этом все значения преобразуется в строку</td></tr><tr><td align="center">In</td><td>Сравнение значений на "входит": элемент массива входит в указанный массив</td></tr><tr><td align="center">NotIn</td><td>Сравнение значений на "не входит": элемент массива не входит в указанный массив</td></tr><tr><td align="center">Overlap</td><td>Сравнение значений на "пересекается": массив из элемента исходного массива имеет общие элементы с указанным массивом</td></tr><tr><td align="center">NotOverlap</td><td>Сравнение значений на "не пересекается": массив из элемента исходного массива не имеет общие элементы с указанным массивом</td></tr><tr><td align="center">MatchSearch</td><td><p>Сравнение значений на "удовлетворяет поисковой строке". Поисковая строка может состоять из слов, разделенных пробелами и символами "+", "*" и "?":</p><ul><li>пробел означает "ИЛИ";</li><li>"+" означает "И";</li><li>"*" означает любое количество любых символов;</li><li>"?" означает ровно один символ.</li></ul></td></tr><tr><td align="center">NotMatchSearch</td><td><p>Сравнение значений на "не удовлетворяет поисковой строке". </p><p>Поисковая строка может состоять из слов, разделенных пробелами и символами "+", "*" и "?":</p><ul><li>пробел означает "ИЛИ";</li><li>"+" означает "И";</li><li>"*" означает любое количество любых символов;</li><li>"?" означает ровно один символ.</li></ul></td></tr><tr><td align="center">ContainedIn</td><td>Сравнение значений на "входит": элемент массива входит в указанное значение, при этом все значения преобразуется в строку</td></tr><tr><td align="center">NotContainedIn</td><td>Сравнение значений на "не входит": элемент массива не входит в указанное значение, при этом все значения преобразуется в строку</td></tr><tr><td align="center">IsNull</td><td>Сравнение на Null</td></tr><tr><td align="center">IsNotNull</td><td>Сравнение на "не Null"</td></tr><tr><td align="center">Nested</td><td>Составной фильтр. Для соединения вложенных фильтров (<a href="array.md#filter"><code>&#x3C;Filter></code></a>) доступны тэги <code>&#x3C;And></code>, <code>&#x3C;Or></code>, <code>&#x3C;Not></code></td></tr></tbody></table>

{% hint style="warning" %}
Если в качестве значения тэга `<Source>` указан **скаляр**, то будет генерироваться ошибка **TypeMismatch**.
{% endhint %}

<details>

<summary>Пример 1. Индекс первого элемента массива, который больше 10</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>-1</Item>
      <Item>1</Item>
      <Item>30</Item>
      <Item>5</Item>
      <Item>15</Item>
    </Structure>
  </Source>
  <IndexOf Type="Greater">
    <Value>10</Value>
    <DataType Type="IntegerDataType" />
  </IndexOf>
</Array>
```

Результат:

```
2
```

</details>

<details>

<summary>Пример 2. Индекс первого элемента массива, который больше 0 и меньше 20</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>-1</Item>
      <Item>1</Item>
      <Item>30</Item>
      <Item>5</Item>
      <Item>15</Item>
    </Structure>
  </Source>
  <IndexOf Type="Nested">
    <And>
      <Filter Type="Greater">
        <Value>0</Value>
        <DataType Type="IntegerDataType" />
      </Filter>
      <Filter Type="Less">
        <Value>20</Value>
        <DataType Type="IntegerDataType" />
      </Filter>
    </And>
  </IndexOf>
</Array>
```

Результат:

```
1
```

</details>

<details>

<summary>Пример 3. Индекс первого элемента матрицы, где второй столбец меньше 0</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>2</Item>
        <Item>2</Item>
      </Row>
      <Row>
        <Item>3</Item>
        <Item>-1</Item>
      </Row>
      <Row>
        <Item>4</Item>
        <Item>15</Item>
      </Row>
      <Row>
        <Item>6</Item>
        <Item>-5</Item>
      </Row>
      <Row>
        <Item>7</Item>
        <Item>5</Item>
      </Row>
    </Structure>
  </Source>
  <IndexOf Type="Less">
    <Index Value="1" />
    <Value>0</Value>
    <DataType Type="IntegerDataType" />
  </IndexOf>
</Array>
```

Результат:

```
1
```

</details>

<details>

<summary>Пример 4. Индекс первого элемента матрицы, где первый столбец больше 4 и второй в диапазоне от -10 до 10</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>2</Item>
        <Item>2</Item>
      </Row>
      <Row>
        <Item>3</Item>
        <Item>-1</Item>
      </Row>
      <Row>
        <Item>4</Item>
        <Item>15</Item>
      </Row>
      <Row>
        <Item>6</Item>
        <Item>-5</Item>
      </Row>
      <Row>
        <Item>7</Item>
        <Item>5</Item>
      </Row>
    </Structure>
  </Source>
  <IndexOf Type="Nested">
    <And>
      <Filter Type="Greater">
        <Value>4</Value>
        <DataType Type="IntegerDataType" />
      </Filter>
      <Filter Type="Greater">
        <Index Value="1" />
        <Value>-10</Value>
        <DataType Type="IntegerDataType" />
      </Filter>
      <Filter Type="Less">
        <Index Value="1" />
        <Value>10</Value>
        <DataType Type="IntegerDataType" />
      </Filter>
    </And>
  </IndexOf>
</Array>
```

Результат:

```
3
```

</details>

### Filter

Возвращает элементы массива, удовлетворяющие условию.

```xml
<!-- общий синтаксис для фильтров -->
<Filter Type="">
  <Field Name="" />
  <!-- или -->
  <Index Value="" />
  <Value><!-- значение фильтра --></Value>
  <DataType Type="" />
</Filter>
```

В необязательном атрибуте `Type` тэга `<Filter>` указывается [тип фильтра](array.md#tipy-sravneniya-znachenii-1). По умолчанию используется фильтр Equal.

Тэг `<Field>` применяется для выборки из массива словарей. В атрибуте `Name` указывается название поля словаря, по которому будет происходить проверка условия.

Тэг `<Index>` применяется для выборки из одномерного массива или матрицы. Для матриц в атрибуте `Value` указывается индекс элемента строки, по которому будет проверка условия.

Тэг [`<DataType>`](../data_types/) задаёт тип элемента. По умолчанию используется тип **StringDataType**.

В зависимости от типа фильтра тэги `<Value>` или `<DataType>` могут отсутствовать. Например, в фильтрах IsNull, IsNotNull.

#### Типы фильтров

<table data-header-hidden><thead><tr><th align="center"></th><th width="459.3333333333333"></th></tr></thead><tbody><tr><td align="center">Equal</td><td>Сравнение значений на равенство</td></tr><tr><td align="center">NotEqual</td><td>Сравнение значений на неравенство</td></tr><tr><td align="center">Greater</td><td>Сравнение значений на "больше": элемент массива больше указанного значения</td></tr><tr><td align="center">GreaterOrEqual</td><td>Сравнение значений на "больше или равно": элемент массива больше или равен указанному значению</td></tr><tr><td align="center">Less</td><td>Сравнение значений на "меньше": элемент массива меньше указанного значения</td></tr><tr><td align="center">LessOrEqual</td><td>Сравнение значений на "меньше или равно": элемент массива меньше или равен указанному значению</td></tr><tr><td align="center">Contains</td><td>Сравнение значений на "содержит": элемент массива содержит указанное значение, при этом все значения преобразуется в строку</td></tr><tr><td align="center">NotContains</td><td>Сравнение значений на "не содержит": элемент массива не содержит указанное значение, при этом все значения преобразуется в строку</td></tr><tr><td align="center">In</td><td>Сравнение значений на "входит": элемент массива входит в указанный массив</td></tr><tr><td align="center">NotIn</td><td>Сравнение значений на "не входит": элемент массива не входит в указанный массив</td></tr><tr><td align="center">Overlap</td><td>Сравнение значений на "пересекается": массив из элемента исходного массива имеет общие элементы с указанным массивом</td></tr><tr><td align="center">NotOverlap</td><td>Сравнение значений на "не пересекается": массив из элемента исходного массива не имеет общие элементы с указанным массивом</td></tr><tr><td align="center">MatchSearch</td><td><p>Сравнение значений на "удовлетворяет поисковой строке". Поисковая строка может состоять из слов, разделенных пробелами и символами "+", "*" и "?":</p><ul><li>пробел означает "ИЛИ";</li><li>"+" означает "И";</li><li>"*" означает любое количество любых символов;</li><li>"?" означает ровно один символ.</li></ul></td></tr><tr><td align="center">NotMatchSearch</td><td><p>Сравнение значений на "не удовлетворяет поисковой строке". </p><p>Поисковая строка может состоять из слов, разделенных пробелами и символами "+", "*" и "?":</p><ul><li>пробел означает "ИЛИ";</li><li>"+" означает "И";</li><li>"*" означает любое количество любых символов;</li><li>"?" означает ровно один символ.</li></ul></td></tr><tr><td align="center">ContainedIn</td><td>Сравнение значений на "входит": элемент массива входит в указанное значение, при этом все значения преобразуется в строку</td></tr><tr><td align="center">NotContainedIn</td><td>Сравнение значений на "не входит": элемент массива не входит в указанное значение, при этом все значения преобразуется в строку</td></tr><tr><td align="center">IsNull</td><td>Сравнение на Null</td></tr><tr><td align="center">IsNotNull</td><td>Сравнение на "не Null"</td></tr><tr><td align="center">Nested</td><td>Составной фильтр. Для соединения вложенных фильтров доступны тэги <code>&#x3C;And></code>, <code>&#x3C;Or></code>, <code>&#x3C;Not></code></td></tr></tbody></table>

{% hint style="warning" %}
Если в качестве значения тэга `<Source>` указан **скаляр**, то будет генерироваться ошибка **TypeMismatch**.
{% endhint %}

<details>

<summary>Пример 1. <strong>Все элементы массива больше 10</strong></summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>-1</Item>
      <Item>1</Item>
      <Item>30</Item>
      <Item>5</Item>
      <Item>15</Item>
    </Structure>
  </Source>
  <Filter Type="Greater">
    <Value>10</Value>
    <DataType Type="IntegerDataType" />
  </Filter>
</Array>
```

Результат:

```
+------+------+
|  30  |  15  |
+------+------+
```

</details>

<details>

<summary>Пример 2. <strong>Все элементы массива больше 0 и меньше 20</strong></summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>-1</Item>
      <Item>1</Item>
      <Item>30</Item>
      <Item>5</Item>
      <Item>15</Item>
    </Structure>
  </Source>
  <Filter Type="Nested">
    <And>
      <Filter Type="Greater">
        <Value>0</Value>
        <DataType Type="IntegerDataType" />
      </Filter>
      <Filter Type="Less">
        <Value>20</Value>
        <DataType Type="IntegerDataType" />
      </Filter>
    </And>
  </Filter>
</Array>
```

Результат:

```
+-----+-----+------+
|  1  |  5  |  15  |
+-----+-----+------+
```

</details>

<details>

<summary>Пример 3. Все элементы матрицы во втором столбце меньше 0</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>2</Item>
        <Item>2</Item>
      </Row>
      <Row>
        <Item>3</Item>
        <Item>-1</Item>
      </Row>
      <Row>
        <Item>4</Item>
        <Item>15</Item>
      </Row>
      <Row>
        <Item>6</Item>
        <Item>-5</Item>
      </Row>
      <Row>
        <Item>7</Item>
        <Item>5</Item>
      </Row>
    </Structure>
  </Source>
  <Filter Type="Less">
    <Index Value="1" />
    <Value>0</Value>
    <DataType Type="IntegerDataType" />
  </Filter>
</Array>
```

Результат:

```
+-----+------+
|  3  |  -1  |
|  6  |  -5  |
+-----+------+
```

</details>

<details>

<summary>Пример 4. Первый столбец матрицы больше 4 и второй в диапазоне от -10 до 10</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>2</Item>
        <Item>2</Item>
      </Row>
      <Row>
        <Item>3</Item>
        <Item>-1</Item>
      </Row>
      <Row>
        <Item>4</Item>
        <Item>15</Item>
      </Row>
      <Row>
        <Item>6</Item>
        <Item>-5</Item>
      </Row>
      <Row>
        <Item>7</Item>
        <Item>5</Item>
      </Row>
    </Structure>
  </Source>
  <Filter Type="Nested">
    <And>
      <Filter Type="Greater">
        <Value>4</Value>
        <DataType Type="IntegerDataType" />
      </Filter>
      <Filter Type="Greater">
        <Index Value="1" />
        <Value>-10</Value>
        <DataType Type="IntegerDataType" />
      </Filter>
      <Filter Type="Less">
        <Index Value="1" />
        <Value>10</Value>
        <DataType Type="IntegerDataType" />
      </Filter>
    </And>
  </Filter>
</Array>
```

Результат:

```
+-----+------+
|  6  |  -5  |
|  7  |   5  |
+-----+------+
```

</details>

## Соединение

### Join

Соединяет исходную матрицу с внешней матрицей по выбранным ключам.\
Аналог `JOIN` из SQL.

```xml
<Join>
  <OuterArray><!-- Внешная матрица --></OuterArray>
  <Keys>
    <!-- Индекс элемента исходной матрицы -->
    <Inner Index="" Type="" />
    <!-- Индекс элемента внешней матрицы -->
    <Outer Index="" Type="" />
  </Keys>
  <!-- Элементы результирующей матрицы -->
  <Result>
    <!-- Элемент исходной матрицы -->
    <Inner Index="" />
    <!-- Элемент внешней матрицы -->
    <Outer Index="" />
  </Result>
</Join>
```

В тэге `<Keys>` указываются индексы элементов, по которым исходная и внешняя матрицы будут соединяться.

В атрибуте `Index` указывается положительное целочисленное значение, а в атрибуте `Type` задаётся один из [типов](../data_types/).

{% hint style="warning" %}
Количество `<Inner>` и `<Outer>` индексов в тэге `<Keys>`должно совпадать.
{% endhint %}

В тэге `<Result>` указываются индексы элементов исходной и/или внешней матрицы, которые будут добавлены в результирующую матрицу.

{% hint style="warning" %}
Если в качестве значения тэга `<Source>` указан **скаляр**, то будет генерироваться ошибка **TypeMismatch**.
{% endhint %}

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>Text 1</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>Text 2</Item>
      </Row>
    </Structure>
  </Source>
  <Join>
    <OuterArray>
      <Structure Type="Table">
        <Row>
          <Item>1</Item>
          <Item>100</Item>
        </Row>
        <Row>
          <Item>3</Item>
          <Item>50</Item>
        </Row>
        <Row>
          <Item>4</Item>
          <Item>95</Item>
        </Row>
      </Structure>
    </OuterArray>
    <Keys>
      <Inner Index="0" Type="IntegerDataType" />
      <Outer Index="0" Type="IntegerDataType" />
    </Keys>
    <Result>
      <Inner Index="0" />
      <Inner Index="1" />
      <Outer Index="1" />
    </Result>
  </Join>
</Array>
```

Результат:

```
+-----+----------+-------+
|  1  |  Text 1  |  100  |
+-----+----------+-------+
```

</details>

### LeftJoin <a href="#left_join" id="left_join"></a>

Соединяет исходную матрицу с внешней матрицей по выбранным ключам, используя все элементы исходной матрицы.\
Аналог `LEFT JOIN` из SQL.

```xml
<LeftJoin>
  <OuterArray><!-- Внешная матрица --></OuterArray>
  <Keys>
    <!-- Индекс элемента исходной матрицы -->
    <Inner Index="" Type="" />
    <!-- Индекс элемента внешней матрицы -->
    <Outer Index="" Type="" />
  </Keys>
  <!-- Элементы результирующей матрицы -->
  <Result>
    <!-- Элемент исходной матрицы -->
    <Inner Index="" />
    <!-- Элемент внешней матрицы -->
    <Outer Index="" />
  </Result>
</LeftJoin>
```

В тэге `<Keys>` указываются индексы элементов, по которым исходная и внешняя матрицы будут соединяться.

В атрибуте `Index` указывается положительное целочисленное значение, а в атрибуте `Type` задаётся один из [типов](../data_types/).

{% hint style="warning" %}
Количество `<Inner>` и `<Outer>` индексов в тэге `<Keys>`должно совпадать.
{% endhint %}

В тэге `<Result>` указываются индексы элементов исходной и/или внешней матрицы, которые будут добавлены в результирующую матрицу.

{% hint style="warning" %}
Если в качестве значения тэга `<Source>` указан **скаляр**, то будет генерироваться ошибка **TypeMismatch**.
{% endhint %}

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>Text 1</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>Text 2</Item>
      </Row>
    </Structure>
  </Source>
  <LeftJoin>
    <OuterArray>
      <Structure Type="Table">
        <Row>
          <Item>1</Item>
          <Item>100</Item>
        </Row>
        <Row>
          <Item>3</Item>
          <Item>50</Item>
        </Row>
        <Row>
          <Item>4</Item>
          <Item>95</Item>
        </Row>
      </Structure>
    </OuterArray>
    <Keys>
      <Inner Index="0" Type="IntegerDataType" />
      <Outer Index="0" Type="IntegerDataType" />
    </Keys>
    <Result>
      <Inner Index="0" />
      <Inner Index="1" />
      <Outer Index="1" />
    </Result>
  </LeftJoin>
</Array>
```

Результат:

```
+-----+----------+-------+
|  1  |  Text 1  |  100  |
|  2  |  Text 2  |       |
+-----+----------+-------+
```

</details>

### RightJoin <a href="#right_join" id="right_join"></a>

Соединяет исходную матрицу с внешней матрицей по выбранным ключам, используя все элементы внешней матрицы.\
Аналог `RIGHT JOIN` из SQL.

```xml
<RightJoin>
  <OuterArray><!-- Внешная матрица --></OuterArray>
  <Keys>
    <!-- Индекс элемента исходной матрицы -->
    <Inner Index="" Type="" />
    <!-- Индекс элемента внешней матрицы -->
    <Outer Index="" Type="" />
  </Keys>
  <!-- Элементы результирующей матрицы -->
  <Result>
    <!-- Элемент исходной матрицы -->
    <Inner Index="" />
    <!-- Элемент внешней матрицы -->
    <Outer Index="" />
  </Result>
</RightJoin>
```

В тэге `<Keys>` указываются индексы элементов, по которым исходная и внешняя матрицы будут соединяться.

В атрибуте `Index` указывается положительное целочисленное значение, а в атрибуте `Type` задаётся один из [типов](../data_types/).

{% hint style="warning" %}
Количество `<Inner>` и `<Outer>` индексов в тэге `<Keys>`должно совпадать.
{% endhint %}

В тэге `<Result>` указываются индексы элементов исходной и/или внешней матрицы, которые будут добавлены в результирующую матрицу.

{% hint style="warning" %}
Если в качестве значения тэга `<Source>` указан **скаляр**, то будет генерироваться ошибка **TypeMismatch**.
{% endhint %}

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>Text 1</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>Text 2</Item>
      </Row>
    </Structure>
  </Source>
  <RightJoin>
    <OuterArray>
      <Structure Type="Table">
        <Row>
          <Item>1</Item>
          <Item>100</Item>
        </Row>
        <Row>
          <Item>3</Item>
          <Item>50</Item>
        </Row>
        <Row>
          <Item>4</Item>
          <Item>95</Item>
        </Row>
      </Structure>
    </OuterArray>
    <Keys>
      <Inner Index="0" Type="IntegerDataType" />
      <Outer Index="0" Type="IntegerDataType" />
    </Keys>
    <Result>
      <Inner Index="0" />
      <Inner Index="1" />
      <Outer Index="1" />
    </Result>
  </RightJoin>
</Array>
```

Результат:

```
+-----+----------+-------+
|  1  |  Text 1  |  100  |
|  3  |          |   50  |
|  4  |          |   95  |
+-----+----------+-------+
```

</details>

### FullJoin <a href="#full_join" id="full_join"></a>

Соединяет исходную матрицу с внешней матрицей по выбранным ключам, используя все элементы исходной и внешней матриц.\
Аналог `FULL JOIN` из SQL.

```xml
<FullJoin>
  <OuterArray><!-- Внешная матрица --></OuterArray>
  <Keys>
    <!-- Индекс элемента исходной матрицы -->
    <Inner Index="" Type="" />
    <!-- Индекс элемента внешней матрицы -->
    <Outer Index="" Type="" />
  </Keys>
  <!-- Элементы результирующей матрицы -->
  <Result>
    <!-- Элемент исходной матрицы -->
    <Inner Index="" />
    <!-- Элемент внешней матрицы -->
    <Outer Index="" />
  </Result>
</FullJoin>
```

В тэге `<Keys>` указываются индексы элементов, по которым исходная и внешняя матрицы будут соединяться.

В атрибуте `Index` указывается положительное целочисленное значение, а в атрибуте `Type` задаётся один из [типов](../data_types/).

{% hint style="warning" %}
Количество `<Inner>` и `<Outer>` индексов в тэге `<Keys>`должно совпадать.
{% endhint %}

В тэге `<Result>` указываются индексы элементов исходной и/или внешней матрицы, которые будут добавлены в результирующую матрицу.

{% hint style="warning" %}
Если в качестве значения тэга `<Source>` указан **скаляр**, то будет генерироваться ошибка **TypeMismatch**.
{% endhint %}

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>Text 1</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>Text 2</Item>
      </Row>
    </Structure>
  </Source>
  <FullJoin>
    <OuterArray>
      <Structure Type="Table">
        <Row>
          <Item>1</Item>
          <Item>100</Item>
        </Row>
        <Row>
          <Item>3</Item>
          <Item>50</Item>
        </Row>
        <Row>
          <Item>4</Item>
          <Item>95</Item>
        </Row>
      </Structure>
    </OuterArray>
    <Keys>
      <Inner Index="0" Type="IntegerDataType" />
      <Outer Index="0" Type="IntegerDataType" />
    </Keys>
    <Result>
      <Inner Index="0" />
      <Inner Index="1" />
      <Outer Index="1" />
    </Result>
  </FullJoin>
</Array>
```

Результат:

```
+-----+----------+-------+
|  1  |  Text 1  |  100  |
|  2  |  Text 2  |       |
|     |          |   50  |
|     |          |   95  |
+-----+----------+-------+
```

</details>

### Concat

Объединяет два массива с сохранением дубликатов.

```xml
<Concat><!-- массив для объединения --></Concat>
```

При объединении элементов используются следующие правила:

* **Матрица объединяется с Матрицей**\
  В каждую строку матрицы из тэга `<Concat>` добавляются пустые элементы, чтобы длина строки соответствовала наибольшей длине строки матрицы, указанной в тэге `<Source>`, и полученная матрица объединяется с матрицей из тэга `<Source>`.

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>Text 1</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>Text 2</Item>
      </Row>
    </Structure>
  </Source>
  <Concat>
    <Structure Type="Table">
      <Row>
        <Item>3</Item>
        <Item>Text 3</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>Text 2</Item>
      </Row>
    </Structure>
  </Concat>
</Array>
```

Результат:

```
+-----+----------+
|  1  |  Text 1  |
|  2  |  Text 2  |
|  3  |  Text 3  |
|  2  |  Text 2  |
+-----+----------+
```

</details>

* **Массив объединяется с Матрицей**\
  Массив из тэга `<Concat>` преобразуется в матрицу. В каждую строку новой матрицы добавляются пустые элементы, чтобы длина строки соответствовала наибольшей длине строки матрицы, указанной в тэге `<Source>`, и полученная матрица объединяется с матрицей из тэга `<Source>`.

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>Text 1</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>Text 2</Item>
      </Row>
    </Structure>
  </Source>
  <Concat>
    <Structure Type="List">
      <Item>3</Item>
      <Item>2</Item>
    </Structure>
  </Concat>
</Array>
```

Результат:

```
+-----+----------+
|  1  |  Text 1  |
|  2  |  Text 2  |
|  3  |          |
|  2  |          |
+-----+----------+
```

</details>

* **Скаляр объединяется с Матрицей**\
  Скаляр из тэга `<Concat>` преобразуется в матрицу. В единственную строку новой матрицы добавляются пустые элементы, чтобы длина строки соответствовала наибольшей длине строки матрицы, указанной в тэге `<Source>`, и полученная матрица объединяется с матрицей из тэга `<Source>`.

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>Text 1</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>Text 2</Item>
      </Row>
    </Structure>
  </Source>
  <Concat>3</Concat>
</Array>
```

Результат:

```
+-----+----------+
|  1  |  Text 1  |
|  2  |  Text 2  |
|  3  |          |
+-----+----------+
```

</details>

* **Матрица объединяется с Массивом**\
  Матрица из тэга `<Concat>` преобразуется в массив, при этом берутся первые элементы каждой строки.  Полученный массив объединяется с массивом из тэга `<Source>`.

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>1</Item>
      <Item>2</Item>
    </Structure>
  </Source>
  <Concat>
    <Structure Type="Table">
      <Row>
        <Item>3</Item>
        <Item>Text 3</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>Text 2</Item>
      </Row>
    </Structure>
  </Concat>
</Array>
```

Результат:

```
+-----+-----+-----+-----+
|  1  |  2  |  3  |  2  |
+-----+-----+-----+-----+
```

</details>

* **Массив объединяется с Массивом**\
  Массив из тэга `<Concat>` объединяется с массивом из тэга `<Source>`.

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>1</Item>
      <Item>2</Item>
    </Structure>
  </Source>
  <Concat>
    <Structure Type="List">
      <Item>3</Item>
      <Item>2</Item>
    </Structure>
  </Concat>
</Array>
```

Результат:

```
+-----+-----+-----+-----+
|  1  |  2  |  3  |  2  |
+-----+-----+-----+-----+
```

</details>

* **Скаляр объединяется с Массивом**\
  Скаляр из тэга `<Concat>` преобразуется в массив и объединяется с массивом из тэга `<Source>`.

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>1</Item>
      <Item>2</Item>
    </Structure>
  </Source>
  <Concat>2</Concat>
</Array>
```

Результат:

```
+-----+-----+-----+
|  1  |  2  |  2  |
+-----+-----+-----+
```

</details>

* Во всех случаях, когда в качестве значения тэга `<Source>` указан **скаляр**, будет генерироваться ошибка **TypeMismatch**.

### Union

Объединяет два массива без сохранения дубликатов.

```xml
<Union><!-- массив для объединения --></Union>
```

При объединении элементов используются следующие правила:

* **Матрица объединяется с Матрицей**\
  В каждую строку матрицы из тэга `<Union>` добавляются пустые элементы, чтобы длина строки соответствовала наибольшей длине строки матрицы, указанной в тэге `<Source>`, и полученная матрица объединяется с матрицей из тэга `<Source>`.

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>Text 1</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>Text 2</Item>
      </Row>
    </Structure>
  </Source>
  <Union>
    <Structure Type="Table">
      <Row>
        <Item>3</Item>
        <Item>Text 3</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>Text 2</Item>
      </Row>
    </Structure>
  </Union>
</Array>
```

Результат:

```
+-----+----------+
|  1  |  Text 1  |
|  2  |  Text 2  |
|  3  |  Text 3  |
+-----+----------+
```

</details>

* **Массив объединяется с Матрицей**\
  Массив из тэга `<Union>` преобразуется в матрицу. В каждую строку новой матрицы добавляются пустые элементы, чтобы длина строки соответствовала наибольшей длине строки матрицы, указанной в тэге `<Source>`, и полученная матрица объединяется с матрицей из тэга `<Source>`.

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>Text 1</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>Text 2</Item>
      </Row>
    </Structure>
  </Source>
  <Union>
    <Structure Type="List">
      <Item>3</Item>
      <Item>2</Item>
    </Structure>
  </Union>
</Array>
```

Результат:

```
+-----+----------+
|  1  |  Text 1  |
|  2  |  Text 2  |
|  3  |          |
|  2  |          |
+-----+----------+
```

</details>

* **Скаляр объединяется с Матрицей**\
  Скаляр из тэга `<Union>` преобразуется в матрицу. В единственную строку новой матрицы добавляются пустые элементы, чтобы длина строки соответствовала наибольшей длине строки матрицы, указанной в тэге `<Source>`, и полученная матрица объединяется с матрицей из тэга `<Source>`.

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>Text 1</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>Text 2</Item>
      </Row>
    </Structure>
  </Source>
  <Union>3</Union>
</Array>
```

Результат:

```
+-----+----------+
|  1  |  Text 1  |
|  2  |  Text 2  |
|  3  |          |
+-----+----------+
```

</details>

* **Матрица объединяется с Массивом**\
  Матрица из тэга `<Union>` преобразуется в массив, при этом берутся первые элементы каждой строки.  Полученный массив объединяется с массивом из тэга `<Source>`.

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>1</Item>
      <Item>2</Item>
    </Structure>
  </Source>
  <Union>
    <Structure Type="Table">
      <Row>
        <Item>3</Item>
        <Item>Text 3</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>Text 2</Item>
      </Row>
    </Structure>
  </Union>
</Array>
```

Результат:

```
+-----+-----+-----+
|  1  |  2  |  3  |
+-----+-----+-----+
```

</details>

* **Массив объединяется с Массивом**\
  Массив из тэга `<Union>` объединяется с массивом из тэга `<Source>`.

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>1</Item>
      <Item>2</Item>
    </Structure>
  </Source>
  <Union>
    <Structure Type="List">
      <Item>3</Item>
      <Item>2</Item>
    </Structure>
  </Union>
</Array>
```

Результат:

```
+-----+-----+-----+
|  1  |  2  |  3  |
+-----+-----+-----+
```

</details>

* **Скаляр объединяется с Массивом**\
  Скаляр из тэга `<Union>` преобразуется в массив и объединяется с массивом из тэга `<Source>`.

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>1</Item>
      <Item>2</Item>
    </Structure>
  </Source>
  <Union>2</Union>
</Array>
```

Результат:

```
+-----+-----+
|  1  |  2  |
+-----+-----+
```

</details>

* Во всех случаях, когда в качестве значения тэга `<Source>` указан **скаляр**, будет генерироваться ошибка **TypeMismatch**.

### Group

Группирует элементы массива по указанным индексам.\
Если в исходном массиве отсутствует элемент с индексом, то вместо него используется значение **Null**.

```xml
<Group> 
  <By Index="" /> 
</Group>
```

Элементов `<By>` может быть неограниченное количество.

{% hint style="warning" %}
Если в качестве значения тэга `<Source>` указан **скаляр**, то будет генерироваться ошибка **TypeMismatch**.
{% endhint %}

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>Text 1</Item>
      </Row>
      <Row>
        <Item>1</Item>
        <Item>Text 2</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>Text 3</Item>
      </Row>
    </Structure>
  </Source>
  <Group>
    <By Index="0" />
  </Group>
</Array>
```

Результат:

```
+-----+------------------+
|  1  |+-----+----------+|
|     ||  1  |  Text 1  ||
|     ||  1  |  Text 2  ||
|     |+-----+----------+|
+-----+-----+------------+
|  2  |+-----+----------+|
|     ||  2  |  Text 3  ||
|     |+-----+----------+|
+-----+------------------+
```

Т.е. будет таблица из двух колонок и двух строк. В первой строке в первой колонке будет скалярный элемент со значением 1, а во второй колонке будет храниться таблица с двумя строками из источника. Во второй строке во второй колонке будет храниться таблица с одной строкой.

</details>

### Zip

Соединяет строки двух массивов таким образом, что первый элемент исходного массива соединяется с первым элементом массива, второй со вторым и т.д.

```xml
<Zip><!-- элементы для соединения --></Zip>
```

{% hint style="info" %}
Длина нового массива соответствует длине наименьшего из массивов.
{% endhint %}

При объединении элементов используются следующие правила:

* **Матрица объединяется с Матрицей**\
  В конец каждой строки исходной матрицы добавляются элементы из соответствующей строки матрицы, указанной в тэге `<Zip>`.

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>Text 1</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>Text 2</Item>
      </Row>
    </Structure>
  </Source>
  <Zip>
    <Structure Type="Table">
      <Row>
        <Item>3</Item>
        <Item>Text 3</Item>
      </Row>
      <Row>
        <Item>4</Item>
        <Item>Text 4</Item>
      </Row>
      <Row>
        <Item>5</Item>
        <Item>Text 5</Item>
      </Row>
    </Structure>
  </Zip>
</Array>
```

Результат:

```
+-----+----------+-----+----------+
|  1  |  Text 1  |  3  |  Text 3  |
|  2  |  Text 2  |  4  |  Text 4  |
+-----+----------+-----+----------+
```

</details>

* **Массив объединяется с Матрицей**\
  В конец каждой строки исходной матрицы добавляется соответствующий элемент массива, указанного в тэге `<Zip>`.

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>Text 1</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>Text 2</Item>
      </Row>
    </Structure>
  </Source>
  <Zip>
    <Structure Type="List">
      <Item>3</Item>
      <Item>4</Item>
      <Item>5</Item>
    </Structure>
  </Zip>
</Array>
```

Результат:

```
+-----+----------+-----+
|  1  |  Text 1  |  3  |
|  2  |  Text 2  |  4  |
+-----+----------+-----+
```

</details>

* **Скаляр объединяется с Матрицей**\
  Скаляр из тэга `<Zip>` добавляется в конец первой строки исходной матрицы, остальные строки матрицы отбрасываются.

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>Text 1</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>Text 2</Item>
      </Row>
    </Structure>
  </Source>
  <Zip>3</Zip>
</Array>
```

Результат:

```
+-----+----------+-----+
|  1  |  Text 1  |  3  |
+-----+----------+-----+
```

</details>

* **Матрица объединяется с Массивом**\
  Матрица из тэга `<Zip>` преобразуется в массив, при этом берутся первые элементы каждой строки.  Полученный массив объединяется с массивом из тэга `<Source>`, при этом элементы массивов образуют строки новой матрицы.

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>1</Item>
      <Item>2</Item>
    </Structure>
  </Source>
  <Zip>
    <Structure Type="Table">
      <Row>
        <Item>3</Item>
        <Item>Text 3</Item>
      </Row>
      <Row>
        <Item>4</Item>
        <Item>Text 4</Item>
      </Row>
      <Row>
        <Item>5</Item>
        <Item>Text 5</Item>
      </Row>
    </Structure>
  </Zip>
</Array>
```

Результат:

```
+-----+-----+
|  1  |  3  |
|  2  |  4  |
+-----+-----+
```

</details>

* **Массив объединяется с Массивом**\
  Элемент массив из тэга `<Zip>` объединяется с соответствующим элементом массива из тэга `<Source>` так, что образуют строку новой матрицы.

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>1</Item>
      <Item>2</Item>
    </Structure>
  </Source>
  <Zip>
    <Structure Type="List">
      <Item>3</Item>
      <Item>4</Item>
      <Item>5</Item>
    </Structure>
  </Zip>
</Array>
```

Результат:

```
+-----+-----+
|  1  |  3  |
|  2  |  4  |
+-----+-----+
```

</details>

* **Скаляр объединяется с Массивом**\
  Скаляр из тэга `<Zip>` преобразуется в массив, и элементы полученного массива соединяются с элементами массива из тэга `<Source>`.

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>1</Item>
      <Item>2</Item>
    </Structure>
  </Source>
  <Zip>3</Zip>
</Array>
```

Результат:

```
+-----+-----+
|  1  |  3  |
+-----+-----+
```

</details>

* Во всех случаях, когда в качестве значения тэга `<Source>` указан **скаляр**, будет генерироваться ошибка **TypeMismatch**.

## Выборка из массива

### ElementAt <a href="#element_at" id="element_at"></a>

Возвращает элемент массива по заданному индексу.\
Если индекс элемента отсутствует в массиве, то операция вернёт **Null**.

```xml
<ElementAt><!-- индекс элемента --></ElementAt>
```

{% hint style="warning" %}
Если в качестве значения тэга `<Source>` указан **скаляр**, то будет генерироваться ошибка **TypeMismatch**.
{% endhint %}

<details>

<summary>Пример 1. Поиск в матрице</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>Text 1</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>Text 2</Item>
      </Row>
      <Row>
        <Item>3</Item>
        <Item>Text 3</Item>
      </Row>
    </Structure>
  </Source>
  <ElementAt>1</ElementAt>
</Array>
```

Результат:

```
+-----+----------+
|  2  |  Text 2  |
+-----+----------+
```

</details>

<details>

<summary>Пример 2. Поиск в массиве</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>1</Item>
      <Item>2</Item>
      <Item>3</Item>
    </Structure>
  </Source>
  <ElementAt>1</ElementAt>
</Array>
```

Результат:

```
2
```

</details>

### Field

Формирует массив из массива словарей.\
Из каждого словаря достает элемент по ключу, имя которого указано в атрибуте `Name` тэга `<Field>`. Если ключ отсутствует в словаре, то возвращается **Null**.

```xml
<Field Name="" />
```

{% hint style="warning" %}
Если в качестве значения тэга `<Source>` указан **не массив словарей**, то выбрасывается исключение **TypeMismatch**.
{% endhint %}

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>
        <Structure Type="Dictionary">
          <Key Name="Key">Val1</Key>
        </Structure>
      </Item>
      <Item>
        <Structure Type="Dictionary">
          <Key Name="Key">Val2</Key>
        </Structure>
      </Item>
      <Item>
        <Structure Type="Dictionary">
          <Key Name="Key2">Val3</Key>
        </Structure>
      </Item>
    </Structure>
  </Source>
  <Field Name="Key" />
</Array>
```

Результат:

```
+--------+--------+--------+
|  Val1  |  Val2  |  NULL  |
+--------+--------+--------+
```

</details>

### First

Возвращает первый элемент массива или матрицы.\
Если массив пустой, то возвращается **Null**.

```xml
<First />
```

{% hint style="warning" %}
Если в качестве значения тэга `<Source>` указан **скаляр**, то будет генерироваться ошибка **TypeMismatch**.
{% endhint %}

<details>

<summary>Пример 1. Первый элемент матрицы</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>Text 1</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>Text 2</Item>
      </Row>
    </Structure>
  </Source>
  <First />
</Array>
```

Результат:

```
+-----+----------+
|  1  |  Text 1  |
+-----+----------+
```

</details>

<details>

<summary>Пример 2. Первый элемент массива</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>1</Item>
      <Item>2</Item>
      <Item>3</Item>
      <Item>4</Item>
    </Structure>
  </Source>
  <First />
</Array>
```

Результат:

```
1
```

</details>

### Last

Возвращает последний элемент массива или матрицы.\
Если массив пустой, то возвращается **Null**.

```xml
<Last />
```

{% hint style="warning" %}
Если в качестве значения тэга `<Source>` указан **скаляр**, то будет генерироваться ошибка **TypeMismatch**.
{% endhint %}

<details>

<summary>Пример 1. Последний элемент матрицы</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>Text 1</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>Text 2</Item>
      </Row>
    </Structure>
  </Source>
  <Last />
</Array>
```

Результат:

```
+-----+----------+
|  2  |  Text 2  |
+-----+----------+
```

</details>

<details>

<summary>Пример 2. Последний элемент массива</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>1</Item>
      <Item>2</Item>
      <Item>3</Item>
      <Item>4</Item>
    </Structure>
  </Source>
  <Last />
</Array>
```

Результат:

```
4
```

</details>

### Skip

Пропускает указанное количество элементов и возвращает оставшиеся элементы.

```xml
<Skip><!-- количество элементов --></Skip>
```

{% hint style="warning" %}
Если в качестве значения тэга `<Source>` указан **скаляр**, то будет генерироваться ошибка **TypeMismatch**.
{% endhint %}

<details>

<summary>Пример 1. Пропуск первых двух элементов в матрице</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>Text 1</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>Text 2</Item>
      </Row>
      <Row>
        <Item>3</Item>
        <Item>Text 3</Item>
      </Row>
      <Row>
        <Item>4</Item>
        <Item>Text 4</Item>
      </Row>
    </Structure>
  </Source>
  <Skip>2</Skip>
</Array>
```

Результат:

```
+-----+----------+
|  3  |  Text 3  |
|  4  |  Text 4  |
+-----+----------+
```

</details>

<details>

<summary>Пример 2. Пропуск первых двух элементов в массиве</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>1</Item>
      <Item>2</Item>
      <Item>3</Item>
      <Item>4</Item>
    </Structure>
  </Source>
  <Skip>2</Skip>
</Array>
```

Результат:

```
+-----+-----+
|  3  |  4  |
+-----+-----+
```

</details>

### Take

Возвращает указанное количество начальных элементов из исходного массива или матрицы.

```xml
<Take><!-- количество элементов --></Take>
```

{% hint style="warning" %}
Если в качестве значения тэга `<Source>` указан **скаляр**, то будет генерироваться ошибка **TypeMismatch**.
{% endhint %}

<details>

<summary>Пример 1. Первые два элемента матрицы</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>Text 1</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>Text 2</Item>
      </Row>
      <Row>
        <Item>3</Item>
        <Item>Text 3</Item>
      </Row>
      <Row>
        <Item>4</Item>
        <Item>Text 4</Item>
      </Row>
    </Structure>
  </Source>
  <Take>2</Take>
</Array>
```

Результат:

```
+-----+----------+
|  1  |  Text 1  |
|  2  |  Text 2  |
+-----+----------+
```

</details>

<details>

<summary>Пример 2. Первые два элемента массива</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>1</Item>
      <Item>2</Item>
      <Item>3</Item>
      <Item>4</Item>
    </Structure>
  </Source>
  <Take>2</Take>
</Array>
```

Результат:

```
+-----+-----+
|  1  |  2  |
+-----+-----+
```

</details>

## Преобразование

### DataTypeFormat <a href="#data_type_format" id="data_type_format"></a>

Преобразует элементы массива в строку с использованием формата указанного [типа](../data_types/).

```xml
<DataTypeFormat Type="" Format="" />
```

Если в тэге `<Source>` указана матрица, то будут браться первые элементы всех строк, а затем преобразовываться в строку заданного формата.

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>1</Item>
      <Item>2</Item>
      <Item>3</Item>
      <Item>4</Item>
    </Structure>
  </Source>
  <DataTypeFormat Type="DoubleDataType" Format="N2" />
</Array>
```

Результат:

```
+--------+--------+--------+--------+
|  1,00  |  2,00  |  3,00  |  4,00  |
+--------+--------+--------+--------+
```

</details>

### DataTypeConvert <a href="#data_type_convert" id="data_type_convert"></a>

Приводит элементы массива к заданному [типу](../data_types/).

```xml
<DataTypeConvert Type="" />
```

Если в тэге `<Source>` указана матрица, то все ее элементы будут приводиться к заданному типу.

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>1.0</Item>
      <Item>2</Item>
      <Item>3.7</Item>
      <Item>4</Item>
    </Structure>
  </Source>
  <DataTypeConvert Type="DoubleDataType" />
</Array>
```

Результат:

```
+-----+-----+-------+-----+
|  1  |  2  |  3,7  |  4  |
+-----+-----+-------+-----+
```

</details>

### Distinct

Возвращает уникальные элементы массива.

```xml
<Distinct />
```

Для выборки строк в матрице можно указать индекс столбца, в котором будет проходить проверка уникальности:

```xml
<Distinct>
  <On Index="" />
</Distinct>
```

Тэгов `<On>` может быть любое количество. Если тэги `<On>` отсутствуют, то выборка строк происходит по первому столбцу.

Если необходимо проверить все столбцы матрицы, то можно использовать необязательный атрибут `AllIndices`:

```xml
<Distinct AllIndices="True"/>
```

Если указаны и атрибут `AllIndices` и тэги  `<On>`, то преимущество отдается атрибуту.

{% hint style="warning" %}
Если в качестве значения тэга `<Source>` указан **скаляр**, то будет генерироваться ошибка **TypeMismatch**.
{% endhint %}

<details>

<summary>Пример 1. Уникальные элементы в массиве</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>1</Item>
      <Item>2</Item>
      <Item>1</Item>
      <Item>4</Item>
    </Structure>
  </Source>
  <Distinct />
</Array>
```

Результат:

```
+-----+-----+-----+
|  1  |  2  |  4  |
+-----+-----+-----+
```

</details>

<details>

<summary>Пример 2. Уникальные элементы в матрице по всем столбцам</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>2</Item>
      </Row>
      <Row>
        <Item>1</Item>
        <Item>1</Item>
      </Row>
      <Row>
        <Item>1</Item>
        <Item>2</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>1</Item>
      </Row>
    </Structure>
  </Source>
  <Distinct>
    <On Index="0" />
    <On Index="1" />
  </Distinct>
</Array>
```

Результат:

```
+-----+-----+
|  1  |  2  |
|  1  |  1  |
|  2  |  1  |
+-----+-----+
```

</details>

<details>

<summary>Пример 3. Уникальные элементы в матрице по одному столбцу</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>2</Item>
      </Row>
      <Row>
        <Item>1</Item>
        <Item>1</Item>
      </Row>
      <Row>
        <Item>1</Item>
        <Item>2</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>1</Item>
      </Row>
    </Structure>
  </Source>
  <Distinct>
    <On Index="1" />
  </Distinct>
</Array>
```

Результат:

```
+-----+-----+
|  1  |  2  |
|  1  |  1  |
+-----+-----+
```

</details>

### Select

Преобразует массив в другой массив с помощью селекторов.

```xml
<Select>
  <Items>
    <Item Type=""></Item>
  </Items>
</Select>
```

В тэге `<Items>` указываются селекторы, которые последовательно применяются к каждому элементу исходного массива (для матриц элементом является строка матрицы). Из значений селекторов формируется новый массив или матрица.

{% hint style="warning" %}
Если в качестве значения тэга `<Source>` указан **скаляр**, то будет генерироваться ошибка **TypeMismatch**.
{% endhint %}

{% hint style="info" %}
Селекторы можно комбинировать друг с другом.
{% endhint %}

Поддерживаются селекторы следующих видов:

* **Index** - Выбирает элемент из исходного массива или матрицы.

```xml
<Item Type="Index"><!-- индекс элемента --></Item>
```

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>Text 1</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>Text 2</Item>
      </Row>
      <Row>
        <Item>3</Item>
        <Item>Text 3</Item>
      </Row>
    </Structure>
  </Source>
  <Select>
    <Items>
      <Item Type="Index">0</Item>
      <Item Type="Index">0</Item>
      <Item Type="Index">1</Item>
    </Items>
  </Select>
</Array>
```

Результат:

```
+-----+-----+----------+
|  1  |  1  |  Text 1  |
|  2  |  2  |  Text 2  |
|  3  |  3  |  Text 3  |
+-----+-----+----------+
```

</details>

* **Field** - Выбор элемент из словаря.

```xml
<Item Type="Field"><!-- название поля словаря--></Item>
```

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="Dictionary">
      <Key Name="Key1">Text 1</Key>
      <Key Name="Key2">Text 2</Key>
      <Key Name="Key3">Text 3</Key>
      <Key Name="Key4">Text 4</Key>
    </Structure>
  </Source>
  <Select>
    <Items>
      <Item Type="Field">Key2</Item>
      <Item Type="Field">Key3</Item>
    </Items>
  </Select>
</Array>
```

Результат:

```
+----------+----------+
|  Text 2  |  Text 3  |
+----------+----------+
```

</details>

* **Value** - Подставляет константное значение.

```xml
<Item Type="Value "><!-- значение--></Item>
```

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>Text 1</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>Text 2</Item>
      </Row>
      <Row>
        <Item>3</Item>
        <Item>Text 3</Item>
      </Row>
    </Structure>
  </Source>
  <Select>
    <Items>
      <Item Type="Index">0</Item>
      <Item Type="Index">1</Item>
      <Item Type="Value">100</Item>
    </Items>
  </Select>
</Array>
```

Результат:

```
+-----+----------+-------+
|  1  |  Text 1  |  100  |
|  2  |  Text 2  |  100  |
|  3  |  Text 3  |  100  |
+-----+----------+-------+
```

</details>

* **Number** - Подставляет порядковый номер элемента.\
  В необязательном атрибуте `Start` можно задать начальное значение последовательности. По умолчанию используется **0**.

```xml
<Item Type="Number" Start="" />
```

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>Text 1</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>Text 2</Item>
      </Row>
      <Row>
        <Item>3</Item>
        <Item>Text 3</Item>
      </Row>
    </Structure>
  </Source>
  <Select>
    <Items>
      <Item Type="Number" Start="5"/>
      <Item Type="Index">0</Item>
      <Item Type="Index">1</Item>
    </Items>
  </Select>
</Array>
```

Результат:

```
+-----+-----+----------+
|  5  |  1  |  Text 1  |
|  6  |  2  |  Text 2  |
|  7  |  3  |  Text 3  |
+-----+-----+----------+
```

</details>

* **Expression** - Вычисляет выражение на основе данных массива и дополнительных переменных.\
  Тэгов `<Item>` может быть любое количество. В выражении `<Expression>` могут использоваться элементы исходного массива (указываются в квадратных скобках `[]`) или дополнительные значения, перечисленные в тэге `<Items>` (указываются в фигурных скобках `{}`).

```xml
<Item Type="Expression">
  <Expression><!-- выражение --></Expression>
  <Items>
   <!-- дополнительные значения -->
   <Item></Item>
  </Items>
</Item>
```

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>Text 1</Item>
        <Item>10</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>Text 2</Item>
        <Item>20</Item>
      </Row>
      <Row>
        <Item>3</Item>
        <Item>Text 3</Item>
        <Item>30</Item>
      </Row>
    </Structure>
  </Source>
  <Select>
    <Items>
      <Item Type="Index">0</Item>
      <Item Type="Index">1</Item>
      <Item Type="Expression">
        <Expression>[2] / {0}</Expression>
        <Items>
          <Item>100</Item>
        </Items>
      </Item>      
    </Items>
  </Select>
</Array>
```

Результат:

```
+-----+----------+-------+
|  1  |  Text 1  |  0,1  |
|  2  |  Text 2  |  0,2  |
|  3  |  Text 3  |  0,3  |
+-----+----------+-------+
```

</details>

* **Format** - Форматирует элементы массива в строку.\
  В строке формата элементы исходного массива доступны по индексу и указываются в фигурных скобках `{}`.

```xml
<Item Type="Format"><!-- строка формата--></Item>
```

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>        
        <Item>1</Item>
        <Item>200</Item>
        <Item>2</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>400</Item>
        <Item>1</Item>
      </Row>
      <Row>
        <Item>3</Item>
        <Item>300</Item>
        <Item>1</Item>
      </Row>
    </Structure>
  </Source>
  <Select>
    <Items>
      <Item Type="Index">0</Item>
      <Item Type="Format">Text {2} ({1})</Item>
    </Items>
  </Select>
</Array>
```

Результат:

```
+-----+----------------+
|  1  |  Text 2 (200)  |
|  2  |  Text 1 (400)  |
|  3  |  Text 1 (300)  |
+-----+----------------+
```

</details>

* **Action** - Элемент на основе вложенного массива.\
  В тэге `<Actions>` указываются операции по работе с массивами аналогично тэгу `<Array>`. Исходным массивом для первой операции будет элемент массива с индексом из тэга `<Index>`.

```xml
<Item Type="Action">
  <Index><!-- индекс элемента исходного массива --></Index>
  <Actions></Actions>
</Item>
```

<details>

<summary>Пример 1. Группировка строк по первому столбцу и расчет суммы вторых столбцов для каждой группы </summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>        
        <Item>1</Item>
        <Item>200</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>400</Item>
      </Row>
      <Row>
        <Item>1</Item>
        <Item>300</Item>
      </Row>
    </Structure>
  </Source>
  <Group>
    <By Index="0" />
  </Group>
  <Select>
    <Items>
      <Item Type="Index">0</Item>
      <Item Type="Action">
        <Index>1</Index>
        <!-- работаем с вложенным массивом -->
        <Actions>
          <Select>
            <Items>
              <!-- второй элемент вложенного массива -->
              <Item Type="Index">1</Item>
            </Items>
          </Select>
          <Sum Type="IntegerDataType" />
        </Actions>
      </Item>
    </Items>
  </Select>
</Array>
```

Результат:

```
+-----+-------+
|  1  |  500  |
|  2  |  400  |
+-----+-------+
```

</details>

<details>

<summary>Пример 2. Расчет суммы элементов для каждого массива в массиве</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>
        <Structure Type="List">
          <Item>1</Item>
          <Item>200</Item>
          <Item>80</Item>
        </Structure>
      </Item>
      <Item>
        <Structure Type="List">
          <Item>2</Item>
          <Item>400</Item>
          <Item>50</Item>
        </Structure>
      </Item>
      <Item>
        <Structure Type="List">
          <Item>1</Item>
          <Item>300</Item>
          <Item>20</Item>
        </Structure>
      </Item>
    </Structure>
  </Source>
  <Select>
    <Items>
      <Item Type="Action">
        <!-- Указывать индекс элемента исходного массива не обязательно -->
        <Index>0</Index>
        <Actions>
          <Sum Type="IntegerDataType" />
        </Actions>
      </Item>
    </Items>
  </Select>
</Array>
```

Результат:

```
+-------+-------+-------+
|  281  |  452  |  321  |
+-------+-------+-------+
```

</details>

* **Substitution** - Выбор значения из таблицы подстановки.\
  В качестве таблицы подстановки должна быть матрица, состоящая из двух столбцов. В первом столбце должен быть ключ, по которому будет идти подстановка, а во втором - значение, которое будет использоваться при подстановке.

```xml
<Item Type="Substitution">
  <Index><!-- индекс элемента исходного массива --></Index>
  <Value><!-- таблица подстановки --></Value>
</Item>
```

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>        
        <Item>1</Item>
        <Item>2</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>1</Item>
      </Row>
      <Row>
        <Item>3</Item>
        <Item>1</Item>
      </Row>
    </Structure>
  </Source>
  <Select>
    <Items>
      <Item Type="Index">0</Item>
      <Item Type="Substitution">
        <Index>1</Index>
        <Value>
          <Structure Type="Table">
            <Row>
              <Item>1</Item>
              <Item>Text 1</Item>
            </Row>
            <Row>
              <Item>2</Item>
              <Item>Text 2</Item>
            </Row>
          </Structure>
        </Value>
      </Item>
    </Items>
  </Select>
</Array>
```

Результат:

```
+-----+----------+
|  1  |  Text 2  |
|  2  |  Text 1  |
|  3  |  Text 1  |
+-----+----------+
```

</details>

### SelectMany <a href="#select_many" id="select_many"></a>

Объединяет строки матрицы в одномерный массив.

```xml
<SelectMany />
```

{% hint style="warning" %}
Если в качестве значения тэга `<Source>` указан **скаляр**, то будет генерироваться ошибка **TypeMismatch**.
{% endhint %}

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>
        <Structure Type="List">
          <Item>1</Item>
          <Item>80</Item>
        </Structure>
      </Item>
      <Item>
        <Structure Type="List">
          <Item>2</Item>
          <Item>50</Item>
        </Structure>
      </Item>
      <Item>
        <Structure Type="List">
          <Item>3</Item>
          <Item>20</Item>
        </Structure>
      </Item>
    </Structure>
  </Source>
  <SelectMany />
</Array>
```

Результат:

```
+-----+------+-----+------+-----+------+
|  1  |  80  |  2  |  50  |  3  |  20  |
+-----+------+-----+------+-----+------+
```

</details>

### StringJoin <a href="#string_join" id="string_join"></a>

Форматирует входящее значение в строку.

```xml
<StringJoin Separator="" LineSeparator="" />
```

Обязательный атрибут `Separator` используется для задания разделителя элементов массива или элементов строки матрицы.

Необязательный атрибут `LineSeparator` используется для задания разделителя строк в матрице. По умолчанию используется значение, указанное в атрибуте `Separator`.

{% hint style="info" %}
Для задания "новой" строки используется сочетание символов: `\r\n`.&#x20;
{% endhint %}

<details>

<summary>Пример 1. Массив массивов</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>
        <Structure Type="List">
          <Item>1</Item>
          <Item>80</Item>
        </Structure>
      </Item>
      <Item>
        <Structure Type="List">
          <Item>2</Item>
          <Item>50</Item>
        </Structure>
      </Item>
    </Structure>
  </Source>
  <StringJoin Separator="; " LineSeparator="\r\n" />
</Array>
```

Результат:

```
1; 80; 2; 50
```

</details>

<details>

<summary>Пример 2. Матрица</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>Text 1</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>Text 2</Item>
      </Row>
      <Row>
        <Item>3</Item>
        <Item>Text 3</Item>
      </Row>
    </Structure>
  </Source>
  <StringJoin Separator="; " LineSeparator="\r\n" />
</Array>
```

Результат:

```
1; Text 1
2; Text 2
3; Text 3
```

</details>

<details>

<summary>Пример 3. Массив</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>Text 1</Item>
      <Item>Text 2</Item>
      <Item>Text 3</Item>
    </Structure>
  </Source>
  <StringJoin Separator="; "  />
</Array>
```

Результат:

```
Text 1; Text 2; Text 3
```

</details>

### StringSplit <a href="#string_split" id="string_split"></a>

Преобразует входное значение в строку, которую затем разделяет по заданному разделителю.

```xml
<StringSplit Separator="" />
```

Обязательный атрибут `Separator` используется для задания разделителя, по которому строка будет разделена.

{% hint style="info" %}
Для разбиения по "новой" строке используется сочетание символов: `\r\n`.&#x20;
{% endhint %}

{% hint style="warning" %}
Так как тэг `<Source>` всегда возвращает массив, то необходимо использовать тэг `<First>` (или любой другой способ), чтобы получить элемент массива, которой будет преобразовываться в строку и разбиваться по заданному разделителю.
{% endhint %}

{% hint style="warning" %}
Если в качестве значения тэга `<Source>` указано **не** **скалярное значение**, то будет генерироваться ошибка **TypeMismatch**.
{% endhint %}

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>1, 2, 3, 4</Source>
  <First />
  <StringSplit Separator=", " />
</Array>
```

Результат:

```
+-----+-----+-----+-----+
|  1  |  2  |  3  |  4  |
+-----+-----+-----+-----+
```

</details>

### ToDictionary <a href="#to_dictionary" id="to_dictionary"></a>

Преобразует массив в массив словарей.

```xml
<ToDictionary>
  <Key Name="" Index="" />
</ToDictionary>
```

Тэгов `<Key>` может быть произвольное количество.

В атрибуте `Name` указывается название ключа словаря.

В атрибуте `Index` указывается индекс элемента массива, который будет записан в словарь по ключу `Name`.

{% hint style="warning" %}
Если в качестве значения тэга `<Source>` указан **скаляр**, то будет генерироваться ошибка **TypeMismatch**.
{% endhint %}

<details>

<summary>Пример 1. Массив преобразуется в словарь</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>1</Item>
      <Item>2</Item>
      <Item>1</Item>
      <Item>4</Item>
    </Structure>
  </Source>
  <ToDictionary>
    <Key Name="Id" Index="0" />
  </ToDictionary>
</Array>
```

Результат:

```
[
   { "Id":"1" },
   { "Id":"2" },
   { "Id":"1" },
   { "Id":"4" }
]
```

</details>

<details>

<summary>Пример 2. Матрица преобразуется в словарь</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>1</Item>
        <Item>100</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>38</Item>
      </Row>
      <Row>
        <Item>3</Item>
        <Item>26</Item>
      </Row>
    </Structure>
  </Source>
  <ToDictionary>
    <Key Name="Id" Index="0" />
    <Key Name="Count"  Index="1" />
  </ToDictionary>
</Array>
```

Результат:

```
[
   {"Id":"1","Count":"100"},
   {"Id":"2","Count":"38"},
   {"Id":"3","Count":"26"}
]
```

</details>

### ToTable <a href="#to_table" id="to_table"></a>

Преобразует массив или скалярное значение в матрицу.

```xml
<ToTable />
```

Преобразование происходит по следующим правилам:

* **Массив преобразуется в матрицу**\
  Создается матрица с количеством строк равным количеству элементов входного массива, и каждый элемент массива пишется в отдельную строку матрицы.

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>1</Item>
      <Item>2</Item>
      <Item>3</Item>
      <Item>4</Item>
    </Structure>
  </Source>
  <ToTable /> 
</Array>
```

Результат:

```
+-----+
|  1  |
|  2  |
|  3  |
|  4  |
+-----+
```

</details>

* **Скаляр преобразуется в матрицу**\
  Создается матрица из одной строки, в которую пишется входное скалярное значение.

<details>

<summary>Пример </summary>

```xml
<Array>
  <Source>2</Source>
  <ToTable />
</Array>
```

Результат:

```
+-----+
|  2  |
+-----+
```

</details>

### ToArray <a href="#to_array" id="to_array"></a>

Преобразует входное значение в массив, если значение скаляр, для массивов возвращает исходное значение.

```xml
<ToArray />
```

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>10</Source>
  <ToArray />
</Array>
```

Результат:

```
+------+
|  10  |
+------+
```

</details>

## Сортировка

### Order

Сортирует элементы массива и матрицы по указанным индексам.

```xml
<Order> 
  <By Index="" Type="" /> 
</Order>
```

Тэгов `<By>` может быть неограниченное количество.

В атрибуте `Index` указывается индекс элемента строки матрицы, по которому будет происходить сортировка. Если в исходном матрице отсутствует элемент с указанным индексом, то такое условие сортировки будет игнорироваться.

В необязательном атрибуте `Type` указывается тип сортировки: **Asc** для сортировки элементов по возрастанию (значение по умолчанию) или **Desc** для сортировки по убыванию.

{% hint style="warning" %}
Если в качестве значения тэга `<Source>` указан **скаляр**, то будет генерироваться ошибка **TypeMismatch**.
{% endhint %}

<details>

<summary>Пример 1. Сортировка матрицы по одному столбцу</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>3</Item>
        <Item>Text 3</Item>
      </Row>
      <Row>
        <Item>1</Item>
        <Item>Text 1</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>Text 2</Item>
      </Row>
      <Row>
        <Item>1</Item>
        <Item>Text 2</Item>
      </Row>
    </Structure>
  </Source>
  <Order>
    <By Index="0" />
  </Order>
</Array>
```

Результат:

```
+-----+----------+
|  1  |  Text 1  |
|  1  |  Text 2  |
|  2  |  Text 2  |
|  3  |  Text 3  |
+-----+----------+
```

</details>

<details>

<summary>Пример 2. Сортировка матрицы по двум столбцам</summary>

```xml
<Array>
  <Source>
    <Structure Type="Table">
      <Row>
        <Item>3</Item>
        <Item>Text 3</Item>
      </Row>
      <Row>
        <Item>1</Item>
        <Item>Text 1</Item>
      </Row>
      <Row>
        <Item>2</Item>
        <Item>Text 2</Item>
      </Row>
      <Row>
        <Item>1</Item>
        <Item>Text 2</Item>
      </Row>
    </Structure>
  </Source>
  <Order>
    <By Index="0" />
    <By Index="1" Type="Desc"/>
  </Order>
</Array>
```

Результат:

```
+-----+----------+
|  1  |  Text 2  |
|  1  |  Text 1  |
|  2  |  Text 2  |
|  3  |  Text 3  |
+-----+----------+
```

</details>

<details>

<summary>Пример 3. Сортировка массива по убыванию</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>3</Item>
      <Item>4</Item>
      <Item>1</Item>
      <Item>2</Item>
    </Structure>
  </Source>
  <Order>
    <By Index="0"  Type="Desc"/>
  </Order>
</Array>
```

Результат:

```
+-----+-----+-----+-----+
|  4  |  3  |  2  |  1  |
+-----+-----+-----+-----+
```

</details>

### Sort

Сортирует элементы одномерного массива.

```xml
<Sort />
```

{% hint style="warning" %}
Если в качестве значения тэга `<Source>` указан **скаляр или матрица**, то будет генерироваться ошибка **TypeMismatch**.
{% endhint %}

<details>

<summary>Пример</summary>

```xml
<Array>
  <Source>
    <Structure Type="List">
      <Item>3</Item>
      <Item>4</Item>
      <Item>1</Item>
      <Item>2</Item>
    </Structure>
  </Source>
  <Sort />
</Array>
```

Результат:

```
+-----+-----+-----+-----+
|  1  |  2  |  3  |  4  |
+-----+-----+-----+-----+
```

</details>
