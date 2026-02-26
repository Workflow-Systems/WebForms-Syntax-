---
description: Команда; сохраняет изображение из буфера обмена на Engine.
---

# SaveClipboardImageCommand

## Шаблон SaveClipboardImageCommand <a href="#template_save_clipboard_image_command" id="template_save_clipboard_image_command"></a>

```xml
<Command Name="" Type="SaveClipboardImageCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <Condition Name="" />
  <Lock Value="" />
  <!--Тэги, специфичные для SaveClipboardImageCommand-->
  <ImageFormat></ImageFormat>
  <Storage></Storage>
</Command>
```

## Описание SaveClipboardImageCommand <a href="#description_save_clipboard_image_command" id="description_save_clipboard_image_command"></a>

Чтение буфера обмена возможно только на страницах с сертификатом и при наличии разрешения пользователя на чтение буфера обмена в браузере.

```xml
<Command Name="SaveClipboardImageCommandName" Type="SaveClipboardImageCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <!--Тэги, специфичные для SaveClipboardImageCommand-->
</Command>
```

### Результат выполнения SaveClipboardImageCommand <a href="#result_save_clipboard_image_command" id="result_save_clipboard_image_command"></a>

#### Value <a href="#result_value" id="result_value"></a>

Если в буфере обмена нашлось изображение и его удалось сохранить: Guid файла, загруженного на Engine. Во всех остальных случаях возвращается `null`.&#x20;

## Тэги, специфичные для SaveClipboardImageCommand <a href="#tags_save_clipboard_image_command" id="tags_save_clipboard_image_command"></a>

### ImageFormat <a href="#image_format" id="image_format"></a>

Название [формата изображения](saveclipboardimagecommand.md#image_formats) для сохранения.

Необязательный тэг. Ожидается название одного из форматов изображений.

Если тэг `<ImageFormat>` отсутствует, то используется значение Png.

#### Форматы изображений <a href="#image_formats" id="image_formats"></a>

1. Bmp
2. Gif
3. Jpg
4. Png
5. Tiff

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
