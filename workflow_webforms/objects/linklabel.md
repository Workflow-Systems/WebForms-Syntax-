---
description: Графический объект; надпись-ссылка.
---

# LinkLabel

## Шаблон LinkLabel <a href="#template_linklabel" id="template_linklabel"></a>

Перечень всех возможных тэгов объекта:

```xml
<MyObject Name="" Type="LinkLabel" Assembly="BaseControls" ChangeForm="">
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
  <!--Тэги, специфичные для LinkLabel-->
  <Link></Link>
  <TextAlign></TextAlign>
  <Text></Text>
  <FileGuid></FileGuid>
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
          <Command Name="" />
        </Then>
      </ElseIf>
      <Else StopOnError="" Lock="">
        <Command Name="" />
      </Else>
    </If>
  </Commands>
</MyObject>
```

## Описание LinkLabel <a href="#description_linklabel" id="description_linklabel"></a>

```xml
<MyObject Name="LinkLabelName" Type="LinkLabel" Assembly="BaseControls">
  <!--Тэги, общие для всех графических объектов-->
  <!--Тэги, специфичные для LinkLabel-->
</MyObject>
```

### Получение значения LinkLabel <a href="#get_value_linklabel" id="get_value_linklabel"></a>

Значением LinkLabel считается текст ссылки.

```xml
<Object Name="LinkLabelName" />
```

### Задание значения LinkLabel <a href="#set_value_linklabel" id="set_value_linklabel"></a>

Любое значение будет переведено в текстовое.

```xml
<Object Name="LinkLabelName"></Object>
```

## Тэги, специфичные для LinkLabel <a href="#tags_linklabel" id="tags_linklabel"></a>

### Link <a href="#link" id="link"></a>

Текст ссылки (открывается, только если поле [`<FileGuid>`](linklabel.md#file_guid) не задано).

Необязательный тэг. Любое значение будет переведено в текстовое.

Можно указать относительный путь внутри приложения WebForms, например "/account", где "account" - URL-адрес одной из форм.

```xml
<Link>Ссылка</Link>
```

### TextAlign <a href="#text_align" id="text_align"></a>

Название типа положения текста надписи.

Необязательный тэг. Ожидается название одного из типов положения текста:

<table data-header-hidden><thead><tr><th width="214" align="center"></th><th width="437.3333333333333"></th></tr></thead><tbody><tr><td align="center">TopLeft</td><td>Слева сверху</td></tr><tr><td align="center">TopCenter</td><td>По центру сверху</td></tr><tr><td align="center">TopRight</td><td>Справа сверху</td></tr><tr><td align="center">MiddleLeft</td><td>Слева посередине</td></tr><tr><td align="center">MiddleCenter</td><td>По центру посередине</td></tr><tr><td align="center">MiddleRight</td><td>Справа посередине</td></tr><tr><td align="center">BottomLeft</td><td>Слева снизу</td></tr><tr><td align="center">BottomCenter</td><td>По центру снизу</td></tr><tr><td align="center">BottomRight</td><td>Справа снизу</td></tr></tbody></table>

По умолчанию используется значение MiddleLeft.

```xml
<TextAlign>MiddleLeft</TextAlign>
```

### Text <a href="#text" id="text"></a>

Текст надписи.

Необязательный тэг. Любое значение будет переведено в текстовое.

```xml
<Text>Текст</Text>
```

### FileGuid <a href="#file_guid" id="file_guid"></a>

Guid файла, который будет загружаться с сервера при открытии ссылки (открывается несмотря на наличие ссылки в поле [`<Link>`](linklabel.md#link)).

Необязательный тэг. Любое значение будет переведено в текстовое.

```xml
<FileGuid>Guid</FileGuid>
```

### Commands <a href="#commands" id="commands"></a>

Список команд, которые будут выполнены при клике мышкой (команды выполняются только если поля [`<Link>`](linklabel.md#link) и [`<FileGuid>`](linklabel.md#file_guid) пустые).

Необязательный тэг. В качестве значения тэга ожидается список тэгов [`<Command>`](linklabel.md#commands_command) и/или конструкций [`<If>`](../values/if.md).

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

#### Атрибуты тэга `<Commands>` <a href="#attributes_tag_commands" id="attributes_tag_commands"></a>

<table data-header-hidden><thead><tr><th width="150" align="center"></th><th width="532.4285714285713"></th></tr></thead><tbody><tr><td align="center">StopOnError</td><td><p>Признак, определяющий, будет ли остановлено выполнение команд, если при выполнении очередной произойдет ошибка.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>По умолчанию используется значение True.</p></td></tr><tr><td align="center">Lock</td><td><p>Признак, определяющий, будет ли блокироваться форма при выполнении команд.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>По умолчанию используется значение False.</p></td></tr></tbody></table>

#### Тэг `<Command>` <a href="#commands_command" id="commands_command"></a>

Обращение к команде по имени для ее выполнения.

Необязательный тэг. В качестве значения тэга ожидается список тэгов [`<Input>`](../values/input.md).

```xml
<!--Вариант 1-->
<Command Name="CommandName1" />

<!--Вариант 2-->
<Command Name="CommandName2">
  <Input Name="InputName1">input 1</Input>
  <Input Name="InputName2">input 2</Input>
</Command>
```

## Get-проперти для получения свойств <a href="#get_property_linklabel" id="get_property_linklabel"></a>

### Link <a href="#get_link" id="get_link"></a>

Возвращает текст ссылки.

```xml
<Object Name="LinkLabelName">
  <Property Name="Link" />
</Object>
```

### Text <a href="#get_text" id="get_text"></a>

Возвращает текст надписи.

```xml
<Object Name="LinkLabelName">
  <Property Name="Text" />
</Object>
```

### TextAlign <a href="#get_text_align" id="get_text_align"></a>

Возвращает название типа положения текста.

```xml
<Object Name="LinkLabelName">
  <Property Name="TextAlign" />
</Object>
```

### FileGuid <a href="#get_file_guid" id="get_file_guid"></a>

Возвращает Guid файла, который будет загружаться с сервера при открытии ссылки.

```xml
<Object Name="LinkLabelName">
  <Property Name="FileGuid" />
</Object>
```

## Set-проперти для динамического задания свойств <a href="#set_property_linklabel" id="set_property_linklabel"></a>

### Link <a href="#set_link" id="set_link"></a>

Задает текст ссылки.

Любое значение будет переведено в текстовое.

```xml
<Object Name="LinkLabelName">
  <Property Name="Link">Ссылка</Property>
</Object>
```

### Text <a href="#set_text" id="set_text"></a>

Задает текст надписи.

Любое значение будет переведено в текстовое.

```xml
<Object Name="LinkLabelName">
  <Property Name="Text">Text</Property>
</Object>
```

### TextAlign <a href="#set_text_align" id="set_text_align"></a>

Задает название типа положения текста.

Ожидается одно из названий типов положения текста.

```xml
<Object Name="LinkLabelName">
  <Property Name="TextAlign">TopLeft</Property>
</Object>
```

### FileGuid <a href="#set_file_guid" id="set_file_guid"></a>

Задает Guid файла, который будет загружаться с сервера при открытии ссылки.

Любое значение будет переведено в текстовое.

```xml
<Object Name="LinkLabelName">
  <Property Name="FileGuid">Guid</Property>
</Object>
```
