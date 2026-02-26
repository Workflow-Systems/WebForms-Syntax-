---
description: Элемент пользовательского интерфейса для ввода и изменения текста.
---

# TextBox

## Шаблон TextBox

Перечень всех возможных тэгов объекта:

```xml
<MyObject Name="" Type="TextBox" Assembly="BaseControls" ChangeForm="">
  <!--Тэги, общие для всех графических объектов-->
  <Top></Top>
  <Bottom></Bottom>
  <Left></Left>
  <Right></Right>
  <Height></Height>
  <Width></Width>
  <FontStyle></FontStyle>
  <ForeColor></ForeColor>
  <BackColor></BackColor>
  <Enabled></Enabled>
  <Visible></Visible>
  <Hint></Hint>
  <Change User="" Source="" ValueSet="" />
  <!--Тэги, специфичные для TextBox-->
  <MaxLength></MaxLength>
  <ReadOnly></ReadOnly>
  <Multiline></Multiline>
  <Password></Password>
  <AllowedSymbols></AllowedSymbols>
  <InputLanguage></InputLanguage>
  <InputCase></InputCase>
  <SelectOnEnter></SelectOnEnter>
  <TipText></TipText>
  <TextAlign></TextAlign>
  <Text></Text>
  <ScrollBars></ScrollBars>  
</MyObject>
```

## Описание TextBox

```xml
<MyObject Name="TextBoxName" Type="TextBox" Assembly="BaseControls">
  <!--Тэги, общие для всех графических объектов-->
  <!--Тэги, специфичные для TextBox-->
</MyObject>
```

Значением `TextBox` считается текст, указанный в поле.

### Получение значения TextBox

Для получения указанного в поле текста используется get-проперти [`Text`](textbox.md#get_text):

```xml
<Object Name="TextBoxName">
  <Property Name="Text" />
</Object>
```

Рекомендуется использовать сокращенный вариант записи:

```xml
<Object Name="TextBoxName" />
```

### Задание значения TextBox

Для задания значения текстовому полю используется set-проперти [`Text`](textbox.md#set_text):

```xml
<Object Name="TextBoxName">
  <Property Name="Text">Текст</Property>
</Object>
```

Рекомендуется использовать сокращенный вариант записи:

```xml
<Object Name="TextBoxName">Текст</Object>
```

## Тэги, специфичные для TextBox

### MaxLength <a href="#max_length" id="max_length"></a>

Задает максимальное число символов, которое разрешается вводить или вставлять в текстовое поле.

Необязательный тэг. Ожидается положительное целочисленное значение.

По умолчанию используется значение 0, показывающее, что ограничения нет.

```xml
<MaxLength>0</MaxLength>
```

### ReadOnly <a href="#read_only" id="read_only"></a>

Указывает, доступно ли текстовое поле только для чтения или для чтения и редактирования.

Необязательный тэг. Ожидается логическое значение.

По умолчанию используется значение False.

```xml
<ReadOnly>False</ReadOnly>
```

### Multiline

Задает значение, показывающее, является ли данный элемент управления многострочным текстовым полем.

Необязательный тэг. Ожидается логическое значение.

По умолчанию используется значение False.

```xml
<Multiline>False</Multiline>
```

### Password

Признак, разрешающий ввод пароля.\
Пользователь увидит только символы звездочек ( \* ). Игнорируется при наличии тэга [`<Multiline>`](textbox.md#multiline).

Необязательный тэг. Ожидается логическое значение.

По умолчанию используется значение False.

```xml
<Password>False</Password>
```

### AllowedSymbols <a href="#allowed_symbols" id="allowed_symbols"></a>

Задает набор символов, которые разрешено вводить в поле.\
Пустая строка соответствует запрету вводить вообще какие-либо символы.

Необязательный тэг. Любое значение будет переведено в текстовое.

Если тэг отсутствует, то можно вводить любые символы.

```xml
<AllowedSymbols>0123456789</AllowedSymbols>
```

### InputLanguage <a href="#input_language" id="input_language"></a>

Задает ограничение на язык вводимых символов.\
Если язык вводимого символа не совпадает с языком, указанным в данном тэге, то этот символ будет трансформирован в символ другого языка, расположенный на этой же клавише клавиатуры.

Необязательный тэг. Ожидается одно из допустимых значений:

<table data-header-hidden><thead><tr><th width="234.41687935952444" align="center"></th><th width="415.40287769784175"></th></tr></thead><tbody><tr><td align="center">Rus</td><td>Русский язык</td></tr><tr><td align="center">Eng</td><td>Английский язык</td></tr><tr><td align="center">None</td><td>Без ограничений по языку</td></tr></tbody></table>

По умолчанию используется значение None.

```xml
<InputLanguage>None</InputLanguage>
```

Например, при значении Rus вводимая последовательность символов "qwerty" будет преобразована в "йцукен".

### InputCase <a href="#input_case" id="input_case"></a>

Задает ограничение на регистр вводимых символов.\
Если регистр вводимого символа не совпадает с регистром, указанном в данном тэге, то этот символ будет трансформирован в указанный регистр.

Необязательный тэг. Ожидается одно из допустимых значений:

<table data-header-hidden><thead><tr><th width="238.67352271687434" align="center"></th><th width="430.0593141797961"></th></tr></thead><tbody><tr><td align="center">Upper</td><td>Верхний регистр</td></tr><tr><td align="center">Lower</td><td>Нижний регистр</td></tr><tr><td align="center">None</td><td>Без ограничений по регистру</td></tr></tbody></table>

По умолчанию используется значение None.

```xml
<InputCase>None</InputCase>
```

### SelectOnEnter <a href="#select_on_enter" id="select_on_enter"></a>

Признак, определяющий, будет ли выделено содержимое поля после получения им фокуса.

Необязательный тэг. Ожидается логическое значение.

По умолчанию используется значение False.

```xml
<SelectOnEnter>False</SelectOnEnter>
```

### TipText <a href="#tip_text" id="tip_text"></a>

Задает текст-заполнитель, который будет отображаться в поле, если оно не имеет фокуса и его значение NULL.

Необязательный тэг. Любое значение будет переведено в текстовое.

```xml
<TipText>Текст подсказки</TipText>
```

### TextAlign <a href="#text_align" id="text_align"></a>

Используется, чтобы указать способ выравнивания текста по горизонтали.

Необязательный тэг.  Ожидается одно из допустимых значений:

<table data-header-hidden><thead><tr><th width="198.926508301592" align="center"></th><th width="355.0302460949434"></th></tr></thead><tbody><tr><td align="center">Left</td><td>Слева</td></tr><tr><td align="center">Center</td><td>По центру</td></tr><tr><td align="center">Right</td><td>Справа</td></tr></tbody></table>

По умолчанию используется значение Left.

```xml
<TextAlign>Left</TextAlign>
```

### Text

Задает значение текстового поля.

Необязательный тэг. Любое значение будет переведено в текстовое.

По умолчанию используется пустая строка.

```xml
<Text>Текст</Text>
```

### ScrollBars <a href="#scroll_bars" id="scroll_bars"></a>

Тип полос прокрутки, показывающий, какие полосы прокрутки должны присутствовать в многострочном поле.\
Используется при установленном тэге [`<Multiline>`](textbox.md#multiline).

Необязательный тэг. Ожидается одно из допустимых значений:

<table data-header-hidden><thead><tr><th width="199.42423557019467" align="center"></th><th width="353.07623138059114"></th></tr></thead><tbody><tr><td align="center">Auto</td><td>Автоматические полосы прокрутки</td></tr><tr><td align="center">Vertical</td><td>Вертикальная полоса прокрутки</td></tr><tr><td align="center">Horizontal</td><td>Горизонтальная полоса прокрутки</td></tr><tr><td align="center">Both</td><td>Вертикальная и горизонтальная полосы прокрутки</td></tr><tr><td align="center">None</td><td>Без полос прокрутки</td></tr></tbody></table>

По умолчанию используется значение Auto.

```xml
<ScrollBars>Vertical</ScrollBars>
```

## Get-проперти для получения свойств

### MaxLength <a href="#get_max_length" id="get_max_length"></a>

Возвращает максимальное число символов, которое разрешается вводить или вставлять в текстовое поле.

```xml
<Object Name="TextBoxName">
  <Property Name="MaxLength" />
</Object>
```

### ReadOnly <a href="#get_read_only" id="get_read_only"></a>

Возвращает значение, определяющее, доступно ли текстовое поле только для чтения или для чтения и редактирования.

```xml
<Object Name="TextBoxName">
  <Property Name="ReadOnly" />
</Object>
```

### Multiline <a href="#get_multiline" id="get_multiline"></a>

Возвращает значение, показывающее, является ли данный элемент управления многострочным текстовым полем.

```xml
<Object Name="TextBoxName">
  <Property Name="Multiline" />
</Object>
```

### Password <a href="#get_password" id="get_password"></a>

Возвращает значение признака ввода пароля в поле.

```xml
<Object Name="TextBoxName">
  <Property Name="Password" />
</Object>
```

### AllowedSymbols <a href="#get_allowed_symbols" id="get_allowed_symbols"></a>

Возвращает набор символов, которые разрешено вводить в поле.

```xml
<Object Name="TextBoxName">
  <Property Name="AllowedSymbols" />
</Object>
```

### InputLanguage <a href="#get_input_language" id="get_input_language"></a>

Возвращает название языка, к которому будут преобразовываться вводимые символы.

```xml
<Object Name="TextBoxName">
  <Property Name="InputLanguage" />
</Object>
```

### InputCase <a href="#get_input_case" id="get_input_case"></a>

Возвращает название регистра, к которому будут преобразовываться вводимые символы.

```xml
<Object Name="TextBoxName">
  <Property Name="InputCase" />
</Object>
```

### SelectOnEnter <a href="#get_select_on_enter" id="get_select_on_enter"></a>

Возвращает значение признака, определяющего, будет ли выделено содержимое поля после получения им фокуса.

```xml
<Object Name="TextBoxName">
  <Property Name="SelectOnEnter" />
</Object>
```

### TipText <a href="#get_tip_text" id="get_tip_text"></a>

Возвращает текст-заполнитель, который будет отображаться в поле, если оно не имеет фокуса и его значение NULL.

```xml
<Object Name="TextBoxName">
  <Property Name="TipText" />
</Object>
```

### TextAlign <a href="#get_text_align" id="get_text_align"></a>

Возвращает способ выравнивания текста по горизонтали.

```xml
<Object Name="TextBoxName">
  <Property Name="TextAlign" />
</Object>
```

### Text <a href="#get_text" id="get_text"></a>

Возвращает значение текстового поля.

```xml
<Object Name="TextBoxName">
  <Property Name="Text" />
</Object>
```

### Length

Возвращает длину текста, введенного в поле.

```xml
<Object Name="TextBoxName">
  <Property Name="Length" />
</Object>
```

### ScrollBars <a href="#get_scroll_bars" id="get_scroll_bars"></a>

Возвращает тип полос прокрутки, показывающий, какие полосы прокрутки должны присутствовать в многострочном поле.

```xml
<Object Name="TextBoxName">
  <Property Name="ScrollBars" />
</Object>
```

## Set-проперти для динамического задания свойств

### MaxLength <a href="#set_max_length" id="set_max_length"></a>

Задает максимальное число символов, которое разрешается вводить или вставлять в текстовое поле.

Ожидается положительное целочисленное значение.

```xml
<Object Name="TextBoxName">
  <Property Name="MaxLength">200</Property>
</Object>
```

### ReadOnly <a href="#set_read_only" id="set_read_only"></a>

Задает значение, определяющее, доступно ли поле только для чтения или для чтения и редактирования.

Ожидается логическое значение.

```xml
<Object Name="TextBoxName">
  <Property Name="ReadOnly">True</Property>
</Object>
```

### Multiline <a href="#set_multiline" id="set_multiline"></a>

Задает значение, показывающее, является ли данный элемент управления многострочным текстовым полем.\
Если тэг [`<Mask>`](textbox.md#mask) присутствует в описании объекта, то любое переданное значение игнорируется.

Ожидается логическое значение.

```xml
<Object Name="TextBoxName">
  <Property Name="Multiline">True</Property>
</Object>
```

### Password <a href="#set_password" id="set_password"></a>

Задает значение признака ввода пароля в поле.\
Если тэг [`<Mask>`](textbox.md#mask) присутствует в описании объекта, то любое переданное значение игнорируется.

Ожидается логическое значение.

```xml
<Object Name="TextBoxName">
  <Property Name="Password">True</Property>
</Object>
```

### AllowedSymbols <a href="#set_allowed_symbols" id="set_allowed_symbols"></a>

Задает набор символов, которые разрешено вводить в поле.

Любое значение будет переведено в текстовое.

```xml
<Object Name="TextBoxName">
  <Property Name="AllowedSymbols">0123,.</Property>
</Object>
```

### InputLanguage <a href="#set_input_language" id="set_input_language"></a>

Задает правила трансформации языка вводимых символов.

Ожидается одно из допустимых значений, указанных в описании тэга [`<InputLanguage>`](textbox.md#input_language).

```xml
<Object Name="TextBoxName">
  <Property Name="InputLanguage">Rus</Property>
</Object>
```

### InputCase <a href="#set_input_case" id="set_input_case"></a>

Задает название языка, к которому будут преобразовываться вводимые символы.

Ожидается одно из допустимых значений, указанных в описании тэга [`<InputCase>`](textbox.md#input_case).

```xml
<Object Name="TextBoxName">
  <Property Name="InputCase">Lower</Property>
</Object>
```

### SelectOnEnter <a href="#set_select_on_enter" id="set_select_on_enter"></a>

Задает значение признака, определяющего, будет ли выделено содержимое поля после получения им фокуса.

Ожидается логическое значение.

```xml
<Object Name="TextBoxName">
  <Property Name="SelectOnEnter">True</Property>
</Object>
```

### TipText <a href="#set_tip_text" id="set_tip_text"></a>

Задает текст-заполнитель, который будет отображаться в поле, если оно не имеет фокуса и его значение NULL.

Любое значение будет переведено в текстовое.

```xml
<Object Name="TextBoxName">
  <Property Name="TipText">Текст</Property>
</Object>
```

### TextAlign <a href="#set_text_align" id="set_text_align"></a>

Задает способ выравнивания текста по горизонтали.\
Если тэг [`<Mask>`](textbox.md#mask) присутствует в описании объекта, то любое переданное значение игнорируется.

Ожидается одно из допустимых значений, указанных в описании тэга [`<TextAlign>`](textbox.md#text_align).

```xml
<Object Name="LabelName">
  <Property Name="TextAlign">Right</Property>
</Object>
```

### Text <a href="#set_text" id="set_text"></a>

Задает значение текстового поля.

Любое значение будет переведено в текстовое.

```xml
<Object Name="TextBoxName">
  <Property Name="Text">Текст</Property>
</Object>
```

### AppendText <a href="#append_text" id="append_text"></a>

Дописывает поле заданным текстом и переводит курсор в конец поля.

Любое значение будет переведено в текстовое.

```xml
<Object Name="TextBoxName">
  <Property Name="AppendText">Текст</Property>
</Object>
```

### ScrollBars <a href="#set_scroll_bars" id="set_scroll_bars"></a>

Задает тип полос прокрутки, показывающий, какие полосы прокрутки должны присутствовать в многострочном поле.\
Используется при установленном тэге [`<Multiline>`](textbox.md#multiline).

Ожидается одно из допустимых значений, указанных в описании тэга [`<ScrollBars>`](textbox.md#scroll_bars).

```xml
<Object Name="TextBoxName">
  <Property Name="ScrollBars">Horizontal</Property>
</Object>
```
