---
description: Графические настройки отображения формы.
---

# Appearance

## Описание графических настроек отображения формы <a href="#description_appearance" id="description_appearance"></a>

Значение: тэги [`<Colors>`](appearance.md#colors) и [`<FontStyles>`](appearance.md#font_styles).

```xml
<Appearance>
  <Colors>
    <Color Name="" Red="" Green="" Blue="" Alpha="" />
  </Colors>
  <FontStyles>
    <FontStyle Name="" Font="" FromFile="" Size="" Bold="" Italic="" Underline="" Strikeout="" />
  </FontStyles>
</Appearance>
```

## Colors <a href="#colors" id="colors"></a>

Значение тэга `<Colors>`: список тэгов [`<Color>`](appearance.md#colors_color).

### Тэг `<Color>` <a href="#colors_color" id="colors_color"></a>

Цвет.

Необязательный тэг. Значение тэга `<Color>`: не ожидается.

#### Атрибуты тэга`<Color>` <a href="#attributes_tag_colors_color" id="attributes_tag_colors_color"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="464.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Название цвета.</p><p></p><p>Обязательный атрибут. Значение атрибута <code>Name</code>: любое значение.</p></td></tr><tr><td align="center">Red</td><td><p>Красная составляющая цвета.</p><p></p><p>Обязательный атрибут. Ожидается целочисленное значение (от 0 до 255).</p></td></tr><tr><td align="center">Green</td><td><p>Зеленая составляющая цвета.</p><p></p><p>Обязательный атрибут. Ожидается целочисленное значение (от 0 до 255).</p></td></tr><tr><td align="center">Blue</td><td><p>Синяя составляющая цвета.</p><p></p><p>Обязательный атрибут. Ожидается целочисленное значение (от 0 до 255).</p></td></tr><tr><td align="center">Alpha</td><td><p>Составляющая насыщенности цвета.</p><p></p><p>Обязательный атрибут. Ожидается целочисленное значение (от 0 до 255).</p></td></tr></tbody></table>

## FontStyles <a href="#font_styles" id="font_styles"></a>

Значение тэга `<FontStyles>`: список тэгов [`<FontStyle>`](appearance.md#font_styles_font_style).

### Тэг `<FontStyle>` <a href="#font_styles_font_style" id="font_styles_font_style"></a>

Стиль шрифта.

Необязательный тэг. Значение тэга `<FontStyle>`: не ожидается.

#### Атрибуты тэга `<FontStyle>` <a href="#attributes_tag_font_styles_font_style" id="attributes_tag_font_styles_font_style"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="464.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Название стиля шрифта.</p><p></p><p>Обязательный атрибут. Значение атрибута <code>Name</code>: любое значение.</p></td></tr><tr><td align="center">Font</td><td><p>Название системного шрифта.</p><p></p><p>Обязательный атрибут. Значение атрибута <code>Font</code>: название одного из системных шрифтов.</p></td></tr><tr><td align="center">Size</td><td><p>Размер шрифта.</p><p></p><p>Обязательный атрибут. Ожидается целочисленное значение (от 1).</p></td></tr><tr><td align="center">Bold</td><td><p>Признак оформления шрифта жирным.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>Если атрибут <code>Bold</code> отсутствует, то используется значение False.</p></td></tr><tr><td align="center">Italic</td><td><p>Признак оформления шрифта курсивом.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>Если атрибут <code>Italic</code> отсутствует, то используется значение False.</p></td></tr><tr><td align="center">Underline</td><td><p>Признак оформления шрифта подчеркиванием.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>Если атрибут <code>Underline</code> отсутствует, то используется значение False.</p></td></tr><tr><td align="center">Strikeout</td><td><p>Признак оформления шрифта зачеркиванием.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>Если атрибут <code>Strikeout</code> отсутствует, то используется значение False.</p></td></tr></tbody></table>

