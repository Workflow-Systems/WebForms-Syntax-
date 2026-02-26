---
description: Меню для навигации внутри веб-приложения.
---

# NavigationMenu

## Шаблон NavigationMenu <a href="#template_label" id="template_label"></a>

Перечень всех возможных тэгов объекта:

```xml
<MyObject Name="" Type="NavigationMenu" Assembly="BaseControls" ChangeForm="">
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
  <!--Тэги, специфичные для NavigationMenu-->
  <ButtonBackColor></ButtonBackColor>
  <ButtonMouseOverColor></ButtonMouseOverColor>
  <ButtonMouseDownColor></ButtonMouseDownColor>
  <ButtonHeight></ButtonHeight>
  <ButtonWidth></ButtonWidth>
  <ButtonTopIncrement></ButtonTopIncrement>
  <TopStart></TopStart>
  <Buttons>
    <Button>
      <Title></Title>
      <Icon></Icon>
      <Href></Href>
    </Button>
  </Buttons>
</MyObject>
```

## Описание NavigationMenu <a href="#description_subscriber" id="description_subscriber"></a>

```xml
<MyObject Name="NavigationMenuName" Type="NavigationMenu" Assembly="BaseControls">
  <!--Тэги, общие для всех графических объектов-->
  <!--Тэги, специфичные для NavigationMenu-->
</MyObject>
```

## Тэги, специфичные для NavigationMenu <a href="#tags_subscriber" id="tags_subscriber"></a>

### ButtonBackColor

Цвет фона кнопок.

Необязательный тэг. Ожидается имя одного из цветов, описанных в форме или описание цвета в формате HTML (#rrggbb).

```xml
<ButtonBackColor>GrayD3</ButtonBackColor>
```

### ButtonMouseOverColor

Цвет фона кнопок при наведении мыши.

Необязательный тэг. Ожидается имя одного из цветов, описанных в форме или описание цвета в формате HTML (#rrggbb).

```xml
<ButtonMouseOverColor>GrayD2</ButtonMouseOverColor>
```

### ButtonMouseDownColor

Цвет фона нажатой кнопки.

Необязательный тэг. Ожидается имя одного из цветов, описанных в форме или описание цвета в формате HTML (#rrggbb).

<pre class="language-xml"><code class="lang-xml"><strong>&#x3C;ButtonMouseDownColor>GrayD1&#x3C;/ButtonMouseDownColor>
</strong></code></pre>

### ButtonHeight

Высота кнопки.

Необязательный тэг. Ожидается целочисленное значение.

По умолчанию используется значение 40.

<pre class="language-xml"><code class="lang-xml"><strong>&#x3C;ButtonHeight>35&#x3C;/ButtonHeight>
</strong></code></pre>

### ButtonWidth

Ширина кнопки.

Необязательный тэг. Ожидается целочисленное значение.

По умолчанию используется значение 200.

<pre class="language-xml"><code class="lang-xml"><strong>&#x3C;ButtonWidth>150&#x3C;/ButtonWidth>
</strong></code></pre>

### ButtonTopIncrement

Сдвиг вниз координаты `Top` кнопки относительно координаты `Top` предыдущей кнопки.

Необязательный тэг. Ожидается целочисленное значение.

По умолчанию используется значение 50.

<pre class="language-xml"><code class="lang-xml"><strong>&#x3C;ButtonTopIncrement>45&#x3C;/ButtonTopIncrement>
</strong></code></pre>

### TopStart

Значение координаты `Top` первой кнопки.

Необязательный тэг. Ожидается целочисленное значение.

По умолчанию используется значение 60.

<pre class="language-xml"><code class="lang-xml"><strong>&#x3C;TopStart>10&#x3C;/TopStart>
</strong></code></pre>

### Buttons <a href="#subscribes" id="subscribes"></a>

Список кнопок в меню.

Необязательный тэг. Ожидается список тэгов [`<Button>`](navigationmenu.md#buttons_button).

```xml
<Buttons>
  <Button>
    <Title>       Список аренд</Title>
    <Icon>view_headline</Icon>
    <Href />
  </Button>
  <Button>
    <Title>       Заявки с сайта</Title>
    <Icon>web</Icon>
    <Href>bids</Href>
  </Button>
</Buttons>
```

#### Тэг `<Button>` <a href="#buttons_button" id="buttons_button"></a>

Кнопка в меню.

Необязательный тэг. Ожидается список тэгов [`<Title>`](navigationmenu.md#buttons_button_title), [`<Icon>`](navigationmenu.md#buttons_button_icon) и [`<Href>`](navigationmenu.md#buttons_button_href).

```xml
<Button>
  <Title>       Заявки с сайта</Title>
  <Icon>web</Icon>
  <Href>bids</Href>
</Button>
```

#### Тэг `<Title>` <a href="#buttons_button_title" id="buttons_button_title"></a>

Текст на кнопке в меню.

Необязательный тэг. Любое значение будет переведено в текстовое.

```xml
<Title>       Заявки с сайта</Title>
```

#### Тэг `<Icon>` <a href="#buttons_button_icon" id="buttons_button_icon"></a>

Иконка, которая будет расположена на кнопке.

Необязательный тэг. Любое значение будет переведено в текстовое.

Ожидается название одного из типов иконок Google. Список иконок доступен по [ссылке](https://www.w3schools.com/icons/icons_reference.asp).

```xml
<Icon>web</Icon>
```

#### Тэг `<Href>` <a href="#buttons_button_href" id="buttons_button_href"></a>

Относительный url-адрес формы, которая будет открыта при нажатии на кнопку.

Необязательный тэг. Любое значение будет переведено в текстовое.

```xml
<Href>bids</Href>
```

## Get-проперти для получения свойств

### ButtonBackColor

Возвращает цвет фона кнопок.

```xml
<Object Name="NavigationMenuName">
  <Property Name="ButtonBackColor" />
</Object>
```

### ButtonMouseOverColor

Возвращает цвет фона кнопок при наведении мыши.

```xml
<Object Name="NavigationMenuName">
  <Property Name="ButtonMouseOverColor" />
</Object>
```

### ButtonMouseDownColor

Возвращает цвет фона нажатой кнопки.

```xml
<Object Name="NavigationMenuName">
  <Property Name="ButtonMouseDownColor" />
</Object>
```

### ButtonHeight

Возвращает высоту кнопки.

```xml
<Object Name="NavigationMenuName">
  <Property Name="ButtonHeight" />
</Object>
```

### ButtonWidth

Возвращает ширину кнопки.

```xml
<Object Name="NavigationMenuName">
  <Property Name="ButtonWidth" />
</Object>
```

### ButtonTopIncrement

Возвращает cдвиг вниз координаты `Top` кнопки относительно координаты `Top` предыдущей кнопки.

```xml
<Object Name="NavigationMenuName">
  <Property Name="ButtonTopIncrement" />
</Object>
```

### TopStart

Возвращает значение координаты `Top` первой кнопки.

```xml
<Object Name="NavigationMenuName">
  <Property Name="TopStart" />
</Object>
```

## Set-проперти для динамического задания свойств <a href="#set_property_panel" id="set_property_panel"></a>

### ButtonBackColor

Задает цвет фона кнопок.

Ожидается имя одного из цветов, описанных в форме или описание цвета в формате HTML (#rrggbb).

```xml
<Object Name="NavigationMenuName">
  <Property Name="ButtonBackColor">Red</Property>
</Object>
```

### ButtonMouseOverColor

Задает цвет фона кнопок при наведении мыши.

Ожидается имя одного из цветов, описанных в форме или описание цвета в формате HTML (#rrggbb).

```xml
<Object Name="NavigationMenuName">
  <Property Name="ButtonMouseOverColor">Green</Property>
</Object>
```

### ButtonMouseDownColor

Задает цвет фона нажатой кнопки.

Ожидается имя одного из цветов, описанных в форме или описание цвета в формате HTML (#rrggbb).

```xml
<Object Name="NavigationMenuName">
  <Property Name="ButtonMouseDownColor">Blue</Property>
</Object>
```

### ButtonHeight

Задает высоту кнопки.

Ожидается целочисленное значение.

```xml
<Object Name="NavigationMenuName">
  <Property Name="ButtonHeight">30</Property>
</Object>
```

### ButtonWidth

Задает ширину кнопки.

Ожидается целочисленное значение.

```xml
<Object Name="NavigationMenuName">
  <Property Name="ButtonWidth">180</Property>
</Object>
```

### ButtonTopIncrement

Задает cдвиг вниз координаты `Top` кнопки относительно координаты `Top` предыдущей кнопки.

Ожидается целочисленное значение.

```xml
<Object Name="NavigationMenuName">
  <Property Name="ButtonTopIncrement">60</Property>
</Object>
```

### TopStart

Задает значение координаты `Top` первой кнопки.

Ожидается целочисленное значение.

```xml
<Object Name="NavigationMenuName">
  <Property Name="TopStart">100</Property>
</Object>
```
