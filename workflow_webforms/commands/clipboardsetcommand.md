---
description: Команда; выполняет запись значения в текстовый буфер обмена Windows.
---

# ClipboardSetCommand

## Шаблон ClipboardSetCommand <a href="#template_clipboard_set_command" id="template_clipboard_set_command"></a>

```xml
<Command Name="" Type="ClipboardSetCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <Condition Name="" />
  <Lock Value="" />
  <!--Тэги, специфичные для ClipboardSetCommand-->
  <ClipboardText></ClipboardText>
</Command>
```

## Описание ClipboardSetCommand <a href="#description_clipboard_set_command" id="description_clipboard_set_command"></a>

Если страница защищена сертификатом, то требуется наличие разрешения пользователя на использование буфера обмена в браузере. В остальных случаях выполнение команды не гарантируется.

```xml
<Command Name="ClipboardSetCommandName" Type="ClipboardSetCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <!--Тэги, специфичные для ClipboardSetCommand-->
</Command>
```

### Результат выполнения ClipboardSetCommand <a href="#result_clipboard_set_command" id="result_clipboard_set_command"></a>

Логическое значение `true` - если команда выполнена успешно, в остальных случаях: `false`.

## Тэги, специфичные для ClipboardSetCommand <a href="#tags_clipboard_set_command" id="tags_clipboard_set_command"></a>

### ClipboardText <a href="#clipboard_text" id="clipboard_text"></a>

Текст для записи в буфер обмена Windows.

Обязательный тэг. Любое значение будет переведено в текстовое.

```xml
<ClipboardText>текст</ClipboardText>
```
