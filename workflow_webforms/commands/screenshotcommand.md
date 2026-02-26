---
description: Команда; получает скриншот страницы браузера и сохраняет его на Engine.
---

# ScreenshotCommand

## Шаблон ScreenshotCommand <a href="#template_screenshot_command" id="template_screenshot_command"></a>

```xml
<Command Name="" Type="ScreenshotCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <Condition Name="" />
  <Lock Value="" />
  <!--Тэги, специфичные для ScreenshotCommand-->
  <Top></Top>
  <Left></Left>
  <Bottom></Bottom>
  <Right></Right>
  <Height></Height>
  <Width></Width>
  <ImageFormat></ImageFormat>
  <ExportFileName Ask=""></ExportFileName>
</Command>
```

## Описание ScreenshotCommand <a href="#description_screenshot_command" id="description_screenshot_command"></a>

```xml
<Command Name="ScreenshotCommandName" Type="ScreenshotCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <!--Тэги, специфичные для ScreenshotCommand-->
</Command>
```

### Результаты выполнения ScreenshotCommand <a href="#result_screenshot_command" id="result_screenshot_command"></a>

#### Value <a href="#result_value" id="result_value"></a>

Guid файла, загруженного на Engine.

## Тэги, специфичные для ScreenshotCommand <a href="#tags_screenshot_command" id="tags_screenshot_command"></a>

### Top <a href="#top" id="top"></a>

Координата верхнего края скриншота.

Необязательный тэг. Ожидается неотрицательное целочисленное значение.

По умолчанию используется значение 0.

```xml
<Top>0</Top>
```

Если тэг `<Top>` присутствует вместе с тэгом [`<Bottom>`](screenshotcommand.md#bottom), то конфликт разрешается в пользу тэга `<Top>`.

### Left <a href="#left" id="left"></a>

Координата левого края скриншота.

Необязательный тэг. Ожидается неотрицательное целочисленное значение.

По умолчанию используется значение 0.

```xml
<Left>0</Left>
```

Если тэг `<Left>` присутствует вместе с тэгом [`<Right>`](screenshotcommand.md#right), то конфликт разрешается в пользу тэга `<Left>`.

### Bottom <a href="#bottom" id="bottom"></a>

Координата нижнего края скриншота.

Необязательный тэг. Ожидается неотрицательное целочисленное значение.

```xml
<Bottom>200</Bottom>
```

Если тэг `<Bottom>` присутствует вместе с тэгом [`<Top>`](screenshotcommand.md#top), то конфликт разрешается в пользу тэга `<Top>`.

Если тэги `<Top>` и `<Bottom>` будут отсутствовать, то для тэга `<Top>` будет использоваться значение по умолчанию - 0.

### Right <a href="#right" id="right"></a>

Координата правого края скриншота.

Необязательный тэг. Ожидается неотрицательное целочисленное значение.

```xml
<Right>100</Right>
```

Если тэг `<Right>` присутствует вместе с тэгом [`<Left>`](screenshotcommand.md#left), то конфликт разрешается в пользу тэга `<Left>`.

Если тэги `<Left>` и `<Right>` будут отсутствовать, то для тэга `<Left>` будет использоваться значение по умолчанию - 0.

### Height <a href="#height" id="height"></a>

Высота скриншота.

Необязательный тэг. Ожидается неотрицательное целочисленное значение.

По умолчанию используется значение высоты экрана.

```xml
<Height>200</Height>
```

### Width <a href="#width" id="width"></a>

Ширина объекта.

Необязательный тэг. Ожидается неотрицательное целочисленное значение.

По умолчанию используется значение ширины экрана.

```xml
<Width>100</Width>
```

### ImageFormat <a href="#image_format" id="image_format"></a>

Название формата изображения для сохранения.

Необязательный тэг. Ожидается название одного из форматов изображений: Bmp, Gif, Jpg, Png, Tiff.

По умолчанию используется значение Png.

```xml
<ImageFormat>Png</ImageFormat>
```

### ExportFileName <a href="#export_file_name" id="export_file_name"></a>

Имя файла, который будет загружен на Engine.

Необязательный тэг. Любое значение будет переведено в текстовое.

Если указан полный путь, то из него будет извлечено имя файла, а остальное проигнорировано.

Если тэг `<ExportFileName>` отсутствует, то имя файла выбирается произвольно.

```xml
<ExportFileName>ExportFileName</ExportFileName>
```
