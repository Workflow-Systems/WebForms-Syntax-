---
description: >-
  Графический объект; кнопка, по нажатию на которую выполняются определенные
  команды.
---

# Button

## Шаблон Button

Перечень всех возможных тэгов объекта:

```xml
<MyObject Name="" Type="Button" Assembly="BaseControls" ChangeForm="">
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
  <!--Тэги, специфичные для Button-->
  <FlatBorderSize></FlatBorderSize>
  <FlatBorderColor></FlatBorderColor>
  <FlatMouseDownBackColor></FlatMouseDownBackColor>
  <FlatMouseOverBackColor></FlatMouseOverBackColor>
  <Image></Image>
  <ImageAlign></ImageAlign>
  <Icon></Icon>
  <DisabledMode></DisabledMode>
  <DisabledText></DisabledText>
  <TextAlign></TextAlign>
  <Text></Text>
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
</MyObject>
```

## Описание Button

```xml
<MyObject Name="ButtonName" Type="Button" Assembly="BaseControls">
  <!--Тэги, общие для всех графических объектов-->
  <!--Тэги, специфичные для Button-->
</MyObject>
```

Значением Button считается текст, указанный на кнопке.

### Получение значения Button

Для получения указанного на кнопке текста используется get-проперти [Text](button.md#text-1):

```xml
<Object Name="ButtonName">
  <Property Name="Text" />
</Object>
```

Рекомендуется использовать сокращенный вариант записи:

```xml
<Object Name="ButtonName" />
```

### Задание значения Button

Для задания отображаемого на кнопке текста используется set-проперти [Text](button.md#set_text):

```xml
<Object Name="ButtonName">
  <Property Name="Text">Text</Property>
</Object>
```

Рекомендуется использовать сокращенный вариант записи:

```xml
<Object Name="ButtonName">Text</Object>
```

## Тэги, специфичные для Button

### FlatBorderSize <a href="#flat_border_size" id="flat_border_size"></a>

Толщина границы кнопки (в пикселях).

Необязательный тэг. Ожидается целочисленное значение.

По умолчанию используется значение 1.

```xml
<FlatBorderSize>1</FlatBorderSize>
```

### FlatBorderColor <a href="#flat_border_color" id="flat_border_color"></a>

Цвет границы кнопки.

Необязательный тэг. Ожидается имя одного из цветов, описанных в форме или описание цвета в формате HTML (#rrggbb).

По умолчанию используется значение #d3d3d3 (светло-серый).

```xml
<FlatBorderColor>FlatBorderColor</FlatBorderColor>
```

### FlatMouseDownBackColor <a href="#flat_mouse_down_back_color" id="flat_mouse_down_back_color"></a>

Цвет фона нажатой кнопки.

Необязательный тэг. Ожидается имя одного из цветов, описанных в форме или описание цвета в формате HTML (#rrggbb).

Если тэг `<FlatMouseDownBackColor>` отсутствует, то цвет рассчитывается автоматически.

```xml
<FlatMouseDownBackColor>FlatMouseDownBackColor</FlatMouseDownBackColor>
```

### FlatMouseOverBackColor <a href="#flat_mouse_over_back_color" id="flat_mouse_over_back_color"></a>

Цвет фона кнопки при наведении курсора мыши.

Необязательный тэг. Ожидается имя одного из цветов, описанных в форме или описание цвета в формате HTML (#rrggbb).

Если тэг `<FlatMouseOverBackColor>` отсутствует, то цвет рассчитывается автоматически.

```xml
<FlatMouseOverBackColor>FlatMouseOverBackColor</FlatMouseOverBackColor>
```

### Image

Путь до файла с графическим содержанием, которое будет расположено на кнопке.

Необязательный тэг. Любое значение будет переведено в текстовое.

```xml
<Image>Image</Image>
```

### ImageAlign <a href="#image_align" id="image_align"></a>

Тип положения картинки.

Необязательный тэг. Ожидается название одного из типов положения картинки:

<table data-header-hidden><thead><tr><th align="center"></th><th width="464.2197125256674"></th></tr></thead><tbody><tr><td align="center">TopLeft</td><td>Слева сверху</td></tr><tr><td align="center">TopCenter</td><td>По центру сверху</td></tr><tr><td align="center">TopRight</td><td>Справа сверху</td></tr><tr><td align="center">MiddleLeft</td><td>Слева посередине</td></tr><tr><td align="center">MiddleCenter</td><td>По центру посередине</td></tr><tr><td align="center">MiddleRight</td><td>Справа посередине</td></tr><tr><td align="center">BottomLeft</td><td>Слева снизу</td></tr><tr><td align="center">BottomCenter</td><td>По центру снизу</td></tr><tr><td align="center">BottomRight</td><td>Справа снизу</td></tr></tbody></table>

По умолчанию используется значение MiddleCente&#x72;**.**

```xml
<ImageAlign>MiddleCenter</ImageAlign>
```

### Icon

Иконка, которая будет расположена на кнопке.

Необязательный тэг. Любое значение будет переведено в текстовое.

Ожидается название одного из типов иконок Google. Список иконок доступен по [ссылке](https://www.w3schools.com/icons/icons_reference.asp).

```xml
<Icon>keyboard_arrow_down</Icon>
```

### TextAlign <a href="#text_align" id="text_align"></a>

Тип положения текста.

Необязательный тэг. Ожидается название одного из типов положения текста:

<table data-header-hidden><thead><tr><th align="center"></th><th width="438.3333333333333"></th></tr></thead><tbody><tr><td align="center">TopLeft</td><td>Слева сверху</td></tr><tr><td align="center">TopCenter</td><td>По центру сверху</td></tr><tr><td align="center">TopRight</td><td>Справа сверху</td></tr><tr><td align="center">MiddleLeft</td><td>Слева посередине</td></tr><tr><td align="center">MiddleCenter</td><td>По центру посередине</td></tr><tr><td align="center">MiddleRight</td><td>Справа посередине</td></tr><tr><td align="center">BottomLeft</td><td>Слева снизу</td></tr><tr><td align="center">BottomCenter</td><td>По центру снизу</td></tr><tr><td align="center">BottomRight</td><td>Справа снизу</td></tr></tbody></table>

По умолчанию используется значение MiddleLeft.

```xml
<TextAlign>MiddleLeft</TextAlign>
```

### Text

Текст на кнопке.

Необязательный тэг. Любое значение будет переведено в текстовое.

```xml
<Text>Текст</Text>
```

### DisabledMode <a href="#disabled_mode" id="disabled_mode"></a>

Признак, при установке которого при нажатии на неактивную кнопку (Enabled = False) будет показано сообщение с текстом, указанным в тэге [`<DisabledText>`](button.md#disabled_text).

Необязательный тэг. Ожидается логическое значение.

По умолчанию используется значение False.

```xml
<DisabledMode>False</DisabledMode>
```

### DisabledText <a href="#disabled_text" id="disabled_text"></a>

Текст сообщения, которое будет показано по нажатию на неактивную кнопку с установленным признаком [`<DisabledMode>`](button.md#disabledmode).

Необязательный тэг. Любое значение будет переведено в текстовое.

```xml
<DisabledText>Текст сообщения</DisabledText>
```

### Commands

Список команд, которые будут выполнены при нажатии на кнопку.

Необязательный тэг. В качестве значения тэга ожидается список тэгов [`<Command>`](button.md#teg-less-than-command-greater-than) и/или конструкций [`<If>`](../values/if.md).

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

Необязательный тэг. В качестве значения тэга ожидается список тэгов [`<Input>`](../values/input.md).

```xml
<!--Вариант 1-->
<Command Name="CommandName1" />

<!--Вариант 2-->
<Command Name="CommandName2">
  <Input Name="InputName1">input 1</Input>
  <Input Name="InputName2">input 2</Input>
```

## Get-проперти для получения свойств

### FlatBorderSize <a href="#get_flat_border_size" id="get_flat_border_size"></a>

Возвращает ширину границы кнопки.

```xml
<Object Name="ButtonName">
  <Property Name="FlatBorderSize" />
</Object>
```

### FlatBorderColor <a href="#get_flat_border_color" id="get_flat_border_color"></a>

Возвращает имя цвета границы плоской кнопки.

```xml
<Object Name="ButtonName">
  <Property Name="FlatBorderColor" />
</Object>
```

### FlatMouseDownBackColor <a href="#get_flat_mouse_down_back_color" id="get_flat_mouse_down_back_color"></a>

Возвращает имя цвета нажатой кнопки.

```xml
<Object Name="ButtonName">
  <Property Name="FlatMouseDownBackColor" />
</Object>
```

### FlatMouseOverBackColor <a href="#get_flat_mouse_over_back_color" id="get_flat_mouse_over_back_color"></a>

Возвращает имя цвета кнопки при наведении курсора мыши.

```xml
<Object Name="ButtonName">
  <Property Name="FlatMouseOverBackColor" />
</Object>
```

### Image <a href="#get_image" id="get_image"></a>

Возвращает путь до файла с графическим содержанием, которое будет расположено на кнопке.

```xml
<Object Name="ButtonName">
  <Property Name="Image" />
</Object>
```

### ImageAlign <a href="#get_image_align" id="get_image_align"></a>

Возвращает название типа положения картинки.

```xml
<Object Name="ButtonName">
  <Property Name="ImageAlign" />
</Object>
```

### Icon <a href="#get_background_image" id="get_background_image"></a>

Возвращает название иконки, которая расположена на кнопке.

```xml
<Object Name="ButtonName">
  <Property Name="Icon" />
</Object>
```

### TextAlign <a href="#get_text_align" id="get_text_align"></a>

Возвращает название типа положения текста.

```xml
<Object Name="ButtonName">
  <Property Name="TextAlign" />
</Object>
```

### Text

Возвращает текст на кнопке.

```xml
<Object Name="ButtonName">
  <Property Name="Text" />
</Object>
```

### DisabledMode <a href="#get_disabled_mode" id="get_disabled_mode"></a>

Возвращает значение признака [`<DisabledMode>`](button.md#disabled_mode).

```xml
<Object Name="ButtonName">
  <Property Name="DisabledMode" />
</Object>
```

### DisabledText <a href="#get_disabled_text" id="get_disabled_text"></a>

Возвращает текст сообщения, заданное для признака [`<DisabledText>`](button.md#disabled_text).

```xml
<Object Name="ButtonName">
  <Property Name="DisabledText" />
</Object>
```

## Set-проперти для динамического задания свойств

### FlatBorderSize <a href="#set_flat_border_size" id="set_flat_border_size"></a>

Задает ширину границы кнопки.

Ожидается целочисленное значение.

```xml
<Object Name="ButtonName">
  <Property Name="FlatBorderSize">1</Property>
</Object>
```

### FlatBorderColor <a href="#set_flat_border_color" id="set_flat_border_color"></a>

Задает цвет границы кнопки.

Ожидается название одного из цветов, описанных в форме или описание цвета в формате HTML (#rrggbb).

```xml
<Object Name="ButtonName">
  <Property Name="FlatBorderColor">FlatBorderColor</Property>
</Object>
```

### FlatMouseDownBackColor <a href="#set_flat_mouse_down_back_color" id="set_flat_mouse_down_back_color"></a>

Задает цвет нажатой кнопки.

Ожидается название одного из цветов, описанных в форме или описание цвета в формате HTML (#rrggbb).

```xml
<Object Name="ButtonName">
  <Property Name="FlatMouseDownBackColor">FlatMouseDownBackColor</Property>
</Object>
```

### FlatMouseOverBackColor <a href="#set_flat_mouse_over_back_color" id="set_flat_mouse_over_back_color"></a>

Задает цвет кнопки при наведении курсора мыши.

Ожидается название одного из цветов, описанных в форме или описание цвета в формате HTML (#rrggbb).

```xml
<Object Name="ButtonName">
  <Property Name="FlatMouseOverBackColor">FlatMouseOverBackColor</Property>
</Object>
```

### Image <a href="#set_image" id="set_image"></a>

Задает путь до файла с графическим содержанием, которое будет расположено на кнопке.

Любое значение будет переведено в текстовое.

```xml
<Object Name="ButtonName">
  <Property Name="Image" />
</Object>
```

### ImageAlign <a href="#set_image_align" id="set_image_align"></a>

Задает название типа положения картинки.

Ожидается одно из названий типов положения картинки.

```xml
<Object Name="ButtonName">
    <Property Name="ImageAlign">TopLeft</Property>
</Object>
```

### Icon <a href="#set_background_image" id="set_background_image"></a>

Задает иконку, которая будет расположена на кнопке.

Любое значение будет переведено в текстовое.

```xml
<Object Name="ButtonName">
  <Property Name="Icon" />
</Object>
```

### TextAlign <a href="#set_text_align" id="set_text_align"></a>

Задает название типа положения текста.

Ожидается одно из названий типов положения текста.

```xml
<Object Name="ButtonName">
  <Property Name="TextAlign">TopLeft</Property>
</Object>
```

### Text

Задает текст на кнопке.

Любое значение будет переведено в текстовое.

```xml
<Object Name="ButtonName">
  <Property Name="Text">Text</Property>
</Object>
```

### DisabledMode <a href="#get_disabled_mode" id="get_disabled_mode"></a>

Задает значение признака [`<DisabledMode>`](button.md#disabled_mode).

```xml
<Object Name="ButtonName">
  <Property Name="DisabledMode" />
</Object>
```

### DisabledText <a href="#get_disabled_text" id="get_disabled_text"></a>

Задает текст сообщения для признака [`<DisabledText>`](button.md#disabled_text).

```xml
<Object Name="ButtonName">
  <Property Name="DisabledText" />
</Object>
```
