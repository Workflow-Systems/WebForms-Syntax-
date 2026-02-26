---
description: Команда; оставляет запись в журнале событий.
---

# LogWriteCommand

## Шаблон LogWriteCommand <a href="#template_log_write_command" id="template_log_write_command"></a>

```xml
<Command Name="" Type="LogWriteCommand" Assembly="Commands">>
  <!--Тэги, общие для всех команд-->
  <Condition Name="" />
  <Lock Value="" />
  <!--Тэги, специфичные для LogWriteCommand-->
  <Severity Type="" />
  <EventId></EventId>
  <Message></Message>
</Command>
```

## Описание LogWriteCommand <a href="#description_log_write_command" id="description_log_write_command"></a>

```xml
<Command Name="LogWriteCommandName" Type="LogWriteCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <!--Тэги, специфичные для LogWriteCommand-->
</Command>
```

### Результат выполнения LogWriteCommand <a href="#result_log_write_command" id="result_log_write_command"></a>

Команда не имеет результата.

## Тэги, специфичные для LogWriteCommand <a href="#tags_log_write_command" id="tags_log_write_command"></a>

### Severity <a href="#severity" id="severity"></a>

Тип добавляемого в журнал события.

Необязательный тэг. Значение тэга `<Severity>`: не ожидается.

Если тэг `<Severity>` отсутствует, то для атрибута `Type` используется значение Information.

```xml
<Severity Type="Information" />
```

#### Атрибуты тэга `<Severity>` <a href="#attributes_tag_severity" id="attributes_tag_severity"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="457.3333333333333"></th></tr></thead><tbody><tr><td align="center">Type</td><td><p>Название типа добавляемого в журнал события.</p><p></p><p>Обязательный атрибут. Ожидается название одного из <a href="logwritecommand.md#log_event_types">типов добавляемого в журнал события</a>.</p></td></tr></tbody></table>

#### Типы добавляемого в журнал события <a href="#log_event_types" id="log_event_types"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="457.3333333333333"></th></tr></thead><tbody><tr><td align="center">Error</td><td>Сообщение об ошибке</td></tr><tr><td align="center">Information</td><td>Информационное событие</td></tr><tr><td align="center">Warning</td><td>Предупреждение</td></tr></tbody></table>

### EventId <a href="#event_id" id="event_id"></a>

Код события, добавляемого в журнал.

Необязательный тэг. Ожидается целочисленное значение.

Если тэг `<EventId>` отсутствует, то используется значение 0.

```xml
<EventId>0</EventId>
```

### Message <a href="#message" id="message"></a>

Текст события, добавляемого в журнал.

Обязательный тэг. Любое значение будет переведено в текстовое.

```xml
<Message>Message</Message>
```
