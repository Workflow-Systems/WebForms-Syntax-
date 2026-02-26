---
description: Контейнер для вставки HTML-разметки
---

# MarkupContainer

## Шаблон MarkupContainer <a href="#template" id="template"></a>

Перечень всех возможных тэгов объекта:

```xml
<MyObject Name="" Type="MarkupContainer" Assembly="BaseControls">
  <!--Тэги, общие для всех графических объектов-->
  <Top></Top>
  <Left></Left>
  <Height></Height>
  <Width></Width>
  <FontStyle></FontStyle>
  <ForeColor></ForeColor>
  <Visible></Visible>
  <CSS></CSS>
  <!--Тэги, специфичные для MarkupContainer-->
  <Markup></Markup>
  <Page404Component></Page404Component>
  <TextAlign></TextAlign>
</MyObject>
```

## Описание MarkupContainer <a href="#description" id="description"></a>

```xml
<MyObject Name="" Type="MarkupContainer" Assembly="BaseControls">
  <!--Тэги, общие для всех графических объектов-->
  <!--Тэги, специфичные для MarkupContainer-->
</MyObject>
```

MarkupContainer не имеет значения.

## Тэги, специфичные для MarkupContainer <a href="#specific-tags" id="specific-tags"></a>

### Markup <a href="#markup" id="markup"></a>

Описывает HTML-код, который будет встраиваться на форму при просмотре страницы.

Необязательный тэг. Ожидается любое значение.

```xml
<Markup>
  <![CDATA[
    <div class="loader" TestElement>Loading<span class="loader__dot">.</span><span class="loader__dot">.</span><span class="loader__dot">.</span></div>
    <style TestElement>
      @keyframes blink {50% { color: transparent }}
      .loader__dot { animation: 1s blink infinite }
      .loader__dot:nth-child(2) { animation-delay: 250ms }
      .loader__dot:nth-child(3) { animation-delay: 500ms }
    </style>
  ]]>
</Markup>
```

{% hint style="warning" %}
Обратите внимание, что HTML-код необходимо экранировать, используя символы

`<![CDATA[`_`HTML-код`_`]]>`
{% endhint %}

### Page404Component <a href="#page_404_component" id="page_404_component"></a>

Признак, переключающий контейнер разметки в режим отображения сообщения об ошибке 404.

Необязательный тэг. Ожидается логическое значение.

По умолчанию используется значение False.

```xml
<Page404Component>True</Page404Component>
```

### TextAlign <a href="#text_align" id="text_align"></a>

Название типа положения текста надписи.

Необязательный тэг. Ожидается название одного из типов положения текста:

<table data-header-hidden><thead><tr><th width="214" align="center"></th><th width="437.3333333333333"></th></tr></thead><tbody><tr><td align="center">TopLeft</td><td>Слева сверху</td></tr><tr><td align="center">TopCenter</td><td>По центру сверху</td></tr><tr><td align="center">TopRight</td><td>Справа сверху</td></tr><tr><td align="center">MiddleLeft</td><td>Слева посередине</td></tr><tr><td align="center">MiddleCenter</td><td>По центру посередине</td></tr><tr><td align="center">MiddleRight</td><td>Справа посередине</td></tr><tr><td align="center">BottomLeft</td><td>Слева снизу</td></tr><tr><td align="center">BottomCenter</td><td>По центру снизу</td></tr><tr><td align="center">BottomRight</td><td>Справа снизу</td></tr></tbody></table>

По умолчанию используется значение MiddleLeft.

```xml
<TextAlign>MiddleCenter</TextAlign>
```

## Get-проперти для получения свойств <a href="#get-properties" id="get-properties"></a>

### Markup <a href="#get_markup" id="get_markup"></a>

Возвращает HTML-код, который встраивается на форму при просмотре страницы.

```xml
<Object Name="MarkupContainerName">
  <Property Name="Markup" />
</Object>
```

### Page404Component <a href="#get_page_404_component" id="get_page_404_component"></a>

Возвращает значение признака, переключающего контейнер разметки в режим отображения сообщения об ошибке 404.

```xml
<Object Name="MarkupContainerName">
  <Property Name="Page404Component" />
</Object>
```

### TextAlign <a href="#get_text_align" id="get_text_align"></a>

Возвращает название типа положения текста.

```xml
<Object Name="MarkupContainerName">
  <Property Name="TextAlign" />
</Object>
```

## Set-проперти для динамического задания свойств <a href="#set-properties" id="set-properties"></a>

### Markup <a href="#set_markup" id="set_markup"></a>

Задает HTML-код, который будет встраиваться на форму при просмотре страницы.

```xml
<Object Name="MarkupContainerName">
  <Property Name="Markup"></Property>
</Object>
```

### Page404Component <a href="#set_page_404_component" id="set_page_404_component"></a>

Задает значение признаку, переключающему контейнер разметки в режим отображения сообщения об ошибке 404.

Ожидается логическое значение.

```xml
<Object Name="MarkupContainerName">
  <Property Name="Page404Component">True</Property>
</Object>
```

### TextAlign <a href="#set_text_align" id="set_text_align"></a>

Задает название типа положения текста.

Ожидается одно из названий типов положения текста.

```xml
<Object Name="MarkupContainerName">
  <Property Name="TextAlign">TopLeft</Property>
</Object>
```
