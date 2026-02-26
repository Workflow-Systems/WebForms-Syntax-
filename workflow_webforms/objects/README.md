---
description: Любой графический объект.
---

# Objects

## Описание Object <a href="#description_object" id="description_object"></a>

```xml
<MyObject Name="MyObjectName" Type="MyObjectType" Assembly="MyObjectAssembly" ChangeForm="True">
  <!--Тэги, общие для всех графических объектов-->
  <!--Тэги, специфичные для определенного графического объекта (зависит от типа)-->
</MyObject>
```

#### Атрибуты Object <a href="#attributes_object" id="attributes_object"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="428.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Название объекта.</p><p></p><p>Обязательный атрибут.</p></td></tr><tr><td align="center">Type</td><td><p>Название типа объекта в сборке.</p><p></p><p>Обязательный атрибут.</p></td></tr><tr><td align="center">Assembly</td><td><p>Название сборки (библиотека).</p><p></p><p>Обязательный атрибут.</p></td></tr><tr><td align="center">ChangeForm</td><td><p>Признак, определяющий, будет ли проперти <a href="./#get_value_changed"><code>ValueChanged</code></a> данного объекта влиять на проперти <a href="/broken/pages/-MaRrLvqMdBI-ceJPvyX#get_form_changed"><code>FormChanged</code></a> формы и <code>ContainerChanged</code> объектов-контейнеров типа <a href="groupbox.md"><code>GroupBox</code></a> и <a href="panel.md"><code>Panel</code></a>, на которых этот объект расположен.</p><p></p><p>Необязательный атрибут.</p><p></p><p>Если атрибут <code>ChangeForm</code> отсутствует, то используется значение True.</p></td></tr></tbody></table>

### Получение значения Object <a href="#get_value_object" id="get_value_object"></a>

```xml
<Object Name="ObjectName" />
```

Любой графический объект имеет значение, которое, как правило, совпадает по смыслу с одним из его тэгов или проперти.

### Задание значения Object <a href="#set_value_object" id="set_value_object"></a>

Значение объекта: любое значение.

```xml
<Object Name="ObjectName"></Object>
```

## Тэги, общие для всех графических объектов <a href="#common_tags" id="common_tags"></a>

### Top <a href="#top" id="top"></a>

Координата расположения объекта по высоте (сверху вниз).

Необязательный тэг. Ожидается целочисленное значение.

По  умолчанию используется значение 0.

Если тэг `<Top>` присутствует вместе с тэгом [`<Bottom>`](./#bottom), то конфликт разрешается в пользу тэга [`<Bottom>`](./#bottom).

```xml
<Top>0</Top>
```

### Left <a href="#left" id="left"></a>

Координата расположения объекта по ширине (слева направо).

Необязательный тэг. Ожидается целочисленное значение.

По  умолчанию используется значение 0.

Если тэг `<Left>` присутствует вместе с тэгом [`<Right>`](./#right), то конфликт разрешается в пользу тэга [`<Right>`](./#right).

```xml
<Left>0</Left>
```

### Height <a href="#height" id="height"></a>

Высота объекта.

Необязательный тэг. Ожидается целочисленное значение.

Если тэг `<Height>` отсутствует, то используется значение по умолчанию для определенного объекта.

```xml
<Height>200</Height>
```

### Width <a href="#width" id="width"></a>

Ширина объекта.

Необязательный тэг. Ожидается целочисленное значение.

Если тэг `<Width>` отсутствует, то используется значение по умолчанию для определенного объекта.

```xml
<Width>100</Width>
```

### Right <a href="#right" id="right"></a>

Координата правого края объекта.

Необязательный тэг. Ожидается целочисленное значение.

Если тэг `<Right>` присутствует вместе с тэгом [`<Left>`](./#left), то конфликт разрешается в пользу тэга `<Right>`.

```xml
<Right>100</Right>
```

### Bottom <a href="#bottom" id="bottom"></a>

Координата нижнего края объекта.

Необязательный тэг. Ожидается целочисленное значение.

Если тэг `<Bottom>` присутствует вместе с тэгом [`<Top>`](./#top), то конфликт разрешается в пользу тэга `<Bottom>`.

```xml
<Bottom>200</Bottom>
```

### FontStyle <a href="#font_style" id="font_style"></a>

Стиль шрифта объекта.&#x20;

Необязательный тэг. Ожидается имя одного из стилей шрифтов, описанных в форме.&#x20;

Если тэг `<FontStyle>` отсутствует, то используется значение `FontStyle`, которое указано для родительского объекта (если такового нет, то формы).

```xml
<FontStyle>FontStyle</FontStyle>
```

### ForeColor <a href="#fore_color" id="fore_color"></a>

Цвет текста объекта.&#x20;

Необязательный тэг. Ожидается имя одного из цветов, описанных в форме или описание цвета в формате HTML (#rrggbb).&#x20;

Если тэг `<ForeColor>` отсутствует, то используется значение `ForeColor`, которое указано для родительского объекта (если такового нет, то формы).

```xml
<ForeColor>ForeColor</ForeColor>
```

### BackColor <a href="#back_color" id="back_color"></a>

Цвет фона объекта.&#x20;

Необязательный тэг. Ожидается имя одного из цветов, описанных в форме или описание цвета в формате HTML (#rrggbb).&#x20;

Если тэг `<BackColor>` отсутствует, то используется значение `BackColor`, которое указано для родительского объекта (если такового нет, то формы).

```xml
<BackColor>BackColor</BackColor>
```

### TabIndex <a href="#tab_index" id="tab_index"></a>

Индекс очереди при TAB-переходах.&#x20;

Необязательный тэг. Ожидается целочисленное значение.&#x20;

Если тэг `<TabIndex>` отсутствует, то используется значение 0.

```xml
<TabIndex>0</TabIndex>
```

### TabStop <a href="#tab_stop" id="tab_stop"></a>

Признак, определяющий, будет ли объект в очереди при TAB-переходах.&#x20;

Необязательный тэг. Ожидается логическое значение.&#x20;

Если тэг `<TabStop>` отсутствует, то используется значение True.

```xml
<TabStop>True</TabStop>
```

### Enabled <a href="#enabled" id="enabled"></a>

Признак активности объекта.&#x20;

Необязательный тэг. Ожидается логическое значение.&#x20;

Если тэг `<Enabled>` отсутствует, то используется значение True.

```xml
<Enabled>True</Enabled>
```

### Visible <a href="#visible" id="visible"></a>

Признак видимости объекта.&#x20;

Необязательный тэг. Ожидается логическое значение.&#x20;

Если тэг `<Visible>` отсутствует, то используется значение True.

```xml
<Visible>True</Visible>
```

### Hint <a href="#hint" id="hint"></a>

Текст всплывающей подсказки объекта.&#x20;

Необязательный тэг. Любое значение будет переведено в текстовое.

```xml
<Hint>Подсказка</Hint>
```

### Change <a href="#change" id="change"></a>

Настройки изменения проперти [`ValueChanged`](./#get_value_changed) объекта.

Есть 3 способа изменить значение объекта:

1. Изменить значение прямым образом в графическом интерфейсе формы (атрибут `User`).
2.  Указать источник значения - ссылка на любые данные на форме (атрибут `Source`).

    В случае изменения значения в источнике, автоматически изменится значение и самого объекта.
3. Присвоить значение объекту посредством команды [`ValueSetCommand`](../commands/value_set_command.md) (атрибут `ValueSet`).

Необязательный тэг.

Если тэг `<Change>` отсутствует, то для атрибутов `User`, `Source` и `ValueSet` используются значения True, True, и True соответственно.

```xml
<Change User="True" Source="False" ValueSet="True" />
```

#### Атрибуты тэга `<Change>` <a href="#attributes_tag_change" id="attributes_tag_change"></a>

<table data-header-hidden><thead><tr><th width="177.95518753044328" align="center"></th><th width="534.3333333333333"></th></tr></thead><tbody><tr><td align="center">User</td><td><p>Признак, определяющий, будет ли <a href="./#get_value_changed"><code>ValueChanged</code></a> иметь значение True, если пользователь в графическом интерфейсе изменит значение объекта.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p></td></tr><tr><td align="center">Source</td><td><p>Признак, определяющий, будет ли <a href="./#get_value_changed"><code>ValueChanged</code></a> иметь значение True, если значение объекта перезагрузится из источника.</p><p></p><p>Если атрибут <code>Source</code> имеет значение False, и при этом значение из источника перезагрузилось, то <a href="./#get_value_changed"><code>ValueChanged</code></a> будет иметь значение False.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p></td></tr><tr><td align="center">ValueSet</td><td><p>Признак, определяющий, будет ли <a href="./#get_value_changed"><code>ValueChanged</code></a> иметь значение True, если значение объекта будет присвоено из команды <a href="../commands/value_set_command.md"><code>ValueSetCommand</code></a>.</p><p></p><p>Если атрибут <code>ValueSet</code> имеет значение False, и при этом значение было присвоено из команды <a href="../commands/value_set_command.md"><code>ValueSetCommand</code></a>, то <a href="./#get_value_changed"><code>ValueChanged</code></a> будет иметь значение False.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p></td></tr></tbody></table>



### Cursor <a href="#cursor" id="cursor"></a>

Курсор мыши, который появляется при наведении ее на объект.&#x20;

Необязательный тэг. Ожидается название одного из типов курсора мыши:

<table data-header-hidden><thead><tr><th width="250.4241645244216" align="center"></th><th width="415.0037547180997"></th></tr></thead><tbody><tr><td align="center">Default</td><td>Значение по умолчанию (определено настройками операционной системы)</td></tr><tr><td align="center">Arrow</td><td>Обычная стрелка</td></tr><tr><td align="center">Wait</td><td>Индикатор ожидания</td></tr><tr><td align="center">AppStarting</td><td>Изображение стрелки с индикатором ожидания</td></tr><tr><td align="center">Hand</td><td>Изображение в виде руки</td></tr><tr><td align="center">Beam</td><td>Изображение в виде буквы<code>"I"</code></td></tr><tr><td align="center">No</td><td>Изображение в виде перечеркнутого красного круга</td></tr><tr><td align="center">Cross</td><td>Изображение в виде крестика</td></tr><tr><td align="center">Help</td><td>Изображение стрелки и вопросительного знака</td></tr><tr><td align="center">HSplit</td><td>Изображение, которое появляется при наведении указателя мыши на горизонтальный разделитель</td></tr><tr><td align="center">SizeAll</td><td>Четырехконечный курсор для изменения размера, состоящий из четырех соединенных стрелок, указывающих вверх, вниз, налево и направо</td></tr><tr><td align="center">SizeNESW</td><td>Двунаправленный (северо-восток — юго-запад) диагональный курсор для изменения размера</td></tr><tr><td align="center">SizeNS</td><td>Двунаправленный вертикальный курсор для изменения размера</td></tr><tr><td align="center">SizeNWSE</td><td>Двунаправленный (северо-запад — юго-восток) диагональный курсор для изменения размера</td></tr><tr><td align="center">SizeWE</td><td>Двунаправленный горизонтальный курсор для изменения размера</td></tr><tr><td align="center">VSplit</td><td>Курсор, который появляется при наведении указателя мыши на вертикальный разделитель</td></tr><tr><td align="center">ZoomIn</td><td>Изображение в виде увеличительного стекла со знаком "+"</td></tr><tr><td align="center">ZoomOut</td><td>Изображение в виде увеличительного стекла со знаком "-"</td></tr><tr><td align="center">Grab</td><td>Изображение, указывающее на возможность схватить объект</td></tr><tr><td align="center">Grabbing</td><td>Изображение, указывающее на то, что объект был схвачен</td></tr></tbody></table>

```xml
<Cursor>Default</Cursor>
```

### CSS

Содержит фрагмент CSS-кода, описывающий настройки стиля объекта.

Необязательный тэг. Любое значение будет переведено в текстовое.

```xml
<CSS>background: rgba(210, 210, 210, 0.4);
box-shadow: 0px 0px 12px rgba(0, 0, 0, 0.16);</CSS>
```

## Get-проперти для получения свойств <a href="#get_properties" id="get_properties"></a>

Перечисленные ниже get-проперти являются общими для всех графических объектов и предназначены для получения свойств данного объекта.

### Value <a href="#get_value" id="get_value"></a>

Возвращает значение объекта, если его существование подразумевается для объекта определенного типа.

```xml
<Object Name="ObjectName">
  <Property Name="Value" />
</Object>
```

### ValueChanged <a href="#get_value_changed" id="get_value_changed"></a>

Возвращает признак изменения значения объекта, если существование значения подразумевается для объекта определенного типа.

```xml
<Object Name="ObjectName">
  <Property Name="ValueChanged" />
</Object>
```

### Top <a href="#get_top" id="get_top"></a>

Возвращает координату расположения объекта по высоте (сверху вниз).

```xml
<Object Name="ObjectName">
  <Property Name="Top" />
</Object>
```

### Left <a href="#get_left" id="get_left"></a>

Возвращает координату расположения объекта по ширине (слева направо).

```xml
<Object Name="ObjectName">
  <Property Name="Left" />
</Object>
```

### Height <a href="#get_height" id="get_height"></a>

Возвращает высоту объекта.

```xml
<Object Name="ObjectName">
  <Property Name="Height" />
</Object>
```

### Width <a href="#get_width" id="get_width"></a>

Возвращает ширину объекта.

```xml
<Object Name="ObjectName">
  <Property Name="Width" />
</Object>
```

### Right <a href="#get_right" id="get_right"></a>

Возвращает положение правого края объекта.

```xml
<Object Name="ObjectName">
  <Property Name="Right" />
</Object>
```

### Bottom <a href="#get_bottom" id="get_bottom"></a>

Возвращает положение нижнего края объекта.

```xml
<Object Name="ObjectName">
  <Property Name="Bottom" />
</Object>
```

### FontStyle <a href="#get_font_style" id="get_font_style"></a>

Возвращает имя стиля шрифта объекта.

```xml
<Object Name="ObjectName">
  <Property Name="FontStyle" />
</Object>
```

### ForeColor <a href="#get_fore_color" id="get_fore_color"></a>

Возвращает имя цвета текста объекта.

```xml
<Object Name="ObjectName">
  <Property Name="ForeColor" />
</Object>
```

### BackColor <a href="#get_back_color" id="get_back_color"></a>

Возвращает имя цвета фона объекта.

```xml
<Object Name="ObjectName">
  <Property Name="BackColor" />
</Object>
```

### TabIndex <a href="#get_tab_index" id="get_tab_index"></a>

Возвращает индекс очереди при TAB-переходах.

```xml
<Object Name="ObjectName">
  <Property Name="TabIndex" />
</Object>
```

### TabStop <a href="#get_tab_stop" id="get_tab_stop"></a>

Возвращает признак, определяющий, будет ли объект в очереди при TAB-переходах.

```xml
<Object Name="ObjectName">
  <Property Name="TabStop" />
</Object>
```

### Enabled <a href="#get_enabled" id="get_enabled"></a>

Возвращает признак активности объекта.

```xml
<Object Name="ObjectName">
  <Property Name="Enabled" />
</Object>
```

### Visible <a href="#get_visible" id="get_visible"></a>

Возвращает признак видимости объекта.

```xml
<Object Name="ObjectName">
  <Property Name="Visible" />
</Object>
```

### Hint <a href="#get_hint" id="get_hint"></a>

Возвращает текст всплывающей подсказки объекта.

```xml
<Object Name="ObjectName">
  <Property Name="Hint" />
</Object>
```

### Cursor <a href="#get_cursor" id="get_cursor"></a>

Возвращает название типа курсора мыши.

```xml
<Object Name="ObjectName">
  <Property Name="Cursor" />
</Object>
```

### Focused <a href="#get_focused" id="get_focused"></a>

Возвращает признак, определяющий, имеет ли объект фокус.

```xml
<Object Name="ObjectName">
  <Property Name="Focused" />
</Object>
```

### CSS <a href="#get_css" id="get_css"></a>

Возвращает настройки стиля объекта, описываемые фрагментом CSS-кода.

```xml
<Object Name="ObjectName">
  <Property Name="CSS" />
</Object>
```

## Set-проперти для динамического задания свойств <a href="#set_properties" id="set_properties"></a>

Перечисленные ниже set-проперти являются общими для всех графических объектов и предназначены для динамического задания свойств объекта (динамическое - означает, что в процессе работы формы, то есть посредством команды [`ValueSetCommand`](../commands/value_set_command.md)).

### Value <a href="#set_value" id="set_value"></a>

Задает значение объекта.&#x20;

Значение тэга `<Property>`: любое значение.

```xml
<Object Name="ObjectName">
  <Property Name="Value">Value</Property>
</Object>
```

### ValueChanged <a href="#set_value_changed" id="set_value_changed"></a>

Задает признак изменения значения объекта.&#x20;

Ожидается логическое значение.

```xml
<Object Name="ObjectName">
  <Property Name="ValueChanged">False</Property>
</Object>
```

### Top <a href="#set_top" id="set_top"></a>

Задает координату расположения объекта по высоте (сверху вниз).

Ожидается целочисленное значение.

```xml
<Object Name="ObjectName">
  <Property Name="Top">10</Property>
</Object>
```

### Left <a href="#set_left" id="set_left"></a>

Задает координату расположения объекта по ширине (слева направо).

Ожидается целочисленное значение.

```xml
<Object Name="ObjectName">
  <Property Name="Left">20</Property>
</Object>
```

### Height <a href="#set_height" id="set_height"></a>

Задает высоту объекта.&#x20;

Ожидается целочисленное значение.

```xml
<Object Name="ObjectName">
  <Property Name="Height">200</Property>
</Object>
```

### Width <a href="#set_width" id="set_width"></a>

Задает ширину объекта.&#x20;

Ожидается целочисленное значение.

```xml
<Object Name="ObjectName">
  <Property Name="Width">100</Property>
</Object>
```

### Right <a href="#set_right" id="set_right"></a>

Задает положение правого края объекта.

Ожидается целочисленное значение.

```xml
<Object Name="ObjectName">
  <Property Name="Right">100</Property>
</Object>
```

### Bottom <a href="#set_bottom" id="set_bottom"></a>

Задает положение нижнего края объекта.&#x20;

Ожидается целочисленное значение.

```xml
<Object Name="ObjectName">
  <Property Name="Bottom">200</Property>
</Object>
```

### FontStyle <a href="#set_font_style" id="set_font_style"></a>

Задает имя стиля шрифта объекта.&#x20;

Ожидается название одного из стилей шрифтов, описанных в форме.

```xml
<Object Name="ObjectName">
  <Property Name="FontStyle">FontStyle</Property>
</Object>
```

### ForeColor <a href="#set_fore_color" id="set_fore_color"></a>

Задает имя цвета текста объекта.&#x20;

Ожидается название одного из цветов, описанных в форме или описание цвета в формате HTML (#rrggbb).

```xml
<Object Name="ObjectName">
  <Property Name="ForeColor">ForeColor</Property>
</Object>
```

### BackColor <a href="#set_back_color" id="set_back_color"></a>

Задает имя цвета фона объекта.&#x20;

Ожидается название одного из цветов, описанных в форме или описание цвета в формате HTML (#rrggbb).

```xml
<Object Name="ObjectName">
  <Property Name="BackColor">BackColor</Property>
</Object>
```

### TabIndex <a href="#set_tab_index" id="set_tab_index"></a>

Задает индекс очереди при TAB-переходах.&#x20;

Ожидается целочисленное значение.

```xml
<Object Name="ObjectName">
  <Property Name="TabIndex" />
</Object>
```

### TabStop <a href="#set_tab_stop" id="set_tab_stop"></a>

Задает признак, определяющий, будет ли объект в очереди при TAB-переходах.&#x20;

Ожидается логическое значение.

```xml
<Object Name="ObjectName">
  <Property Name="TabStop" />
</Object>
```

### Enabled <a href="#set_enabled" id="set_enabled"></a>

Задает признак активности объекта.&#x20;

Ожидается логическое значение.

```xml
<Object Name="ObjectName">
  <Property Name="Enabled">True</Property>
</Object>
```

### Visible <a href="#set_visible" id="set_visible"></a>

Задает признак видимости объекта.&#x20;

Ожидается логическое значение.

```xml
<Object Name="ObjectName">
  <Property Name="Visible">True</Property>
</Object>
```

### Hint <a href="#set_hint" id="set_hint"></a>

Задает текст всплывающей подсказки объекта.&#x20;

Любое значение будет переведено в текстовое.

```xml
<Object Name="ObjectName">
  <Property Name="Hint">Подсказка</Property>
</Object>
```

### Cursor <a href="#set_cursor" id="set_cursor"></a>

Задает тип курсора мыши.&#x20;

Ожидается название одного из типов курсора мыши.

```xml
<Object Name="ObjectName">
  <Property Name="Cursor">Hand</Property>
</Object>
```

### CSS <a href="#set_css" id="set_css"></a>

Задает настройки стиля объекта, описываемые фрагментом CSS-кода.

Любое значение будет переведено в текстовое.

```xml
<Object Name="ObjectName">
  <Property Name="CSS">background: linear-gradient(to bottom right, rgba(36,81,128,1) 0%, rgba(36,126,111,1) 70%);</Property>
</Object>
```
