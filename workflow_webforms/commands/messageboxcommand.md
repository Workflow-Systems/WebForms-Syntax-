---
description: Команда; открывает панель с сообщением.
---

# MessageBoxCommand

## Шаблон MessageBoxCommand <a href="#template_message_box_command" id="template_message_box_command"></a>

```xml
<Command Name="" Type="MessageBoxCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <Condition Name="" />
  <Lock Value="" />
  <!--Тэги, специфичные для MessageBoxCommand-->
  <Caption></Caption>
  <Text></Text>
  <Icon Type="" />
  <Buttons Type="" />
</Command>
```

## Описание MessageBoxCommand <a href="#description_message_box_command" id="description_message_box_command"></a>

```xml
<Command Name="MessageBoxCommandName" Type="MessageBoxCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <!--Тэги, специфичные для MessageBoxCommand-->
</Command>
```

### Результат выполнения MessageBoxCommand <a href="#result_message_box_command" id="result_message_box_command"></a>

#### Value <a href="#result_value" id="result_value"></a>

Один из [типов результата работы](messageboxcommand.md#dialog_result_types) диалогового окна.

#### Типы результатов работы диалогового окна <a href="#dialog_result_types" id="dialog_result_types"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="437.3333333333333"></th></tr></thead><tbody><tr><td align="center">OK</td><td>Значение отправляется с кнопкой с надписью "OK"</td></tr><tr><td align="center">Cancel</td><td>Значение отправляется кнопкой с надписью "Отмена" ("Cancel")</td></tr><tr><td align="center">Abort</td><td>Значение отправляется кнопкой с надписью "Прервать" ("Abort")</td></tr><tr><td align="center">Retry</td><td>Значение отправляется кнопкой с надписью "Повторить" ("Retry")</td></tr><tr><td align="center">Ignore</td><td>Значение отправляется кнопкой "Пропустить" ("Ignore")</td></tr><tr><td align="center">Yes</td><td>Значение отправляется с кнопкой с надписью "Да" ("Yes")</td></tr><tr><td align="center">No</td><td>Значение отправляется с кнопкой с надписью "Нет" ("No")</td></tr></tbody></table>

#### OK <a href="#result_ok" id="result_ok"></a>

Признак, определяющий, была ли нажата кнопка "OK" в диалоговом окне.

#### Cancel <a href="#result_cancel" id="result_cancel"></a>

Признак, определяющий, была ли нажата кнопка "Cancel" в диалоговом окне.

#### Abort <a href="#result_abort" id="result_abort"></a>

Признак, определяющий, была ли нажата кнопка "Abort" в диалоговом окне.

#### Retry <a href="#result_retry" id="result_retry"></a>

Признак, определяющий, была ли нажата кнопка "Retry" в диалоговом окне.

#### Ignore <a href="#result_ignore" id="result_ignore"></a>

Признак, определяющий, была ли нажата кнопка "Ignore" в диалоговом окне.

#### Yes <a href="#result_yes" id="result_yes"></a>

Признак, определяющий, была ли нажата кнопка "Yes" в диалоговом окне.

#### No <a href="#result_no" id="result_no"></a>

Признак, определяющий, была ли нажата кнопка "No" в диалоговом окне.

## Тэги, специфичные для MessageBoxCommand <a href="#tags_message_box_command" id="tags_message_box_command"></a>

### Caption <a href="#caption" id="caption"></a>

Заголовок диалогового окна.

Необязательный тэг. Любое значение будет переведено в текстовое.

```xml
<Caption>Caption</Caption>
```

### Text <a href="#text" id="text"></a>

Текст внутри диалогового окна.

Необязательный тэг. Любое значение будет переведено в текстовое.

```xml
<Text>Text</Text>
```

### Icon <a href="#icon" id="icon"></a>

Иконка диалогового окна.

Необязательный тэг. Значение тэга `<Icon>`: не ожидается.

Если тэг `<Icon>` отсутствует, то для атрибута `Type` используется значение Information.

```xml
<Icon Type="None" />
```

#### Атрибуты тэга `<Icon>` <a href="#attributes_tag_icon" id="attributes_tag_icon"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="437.3333333333333"></th></tr></thead><tbody><tr><td align="center">Type</td><td><p>Название типа иконки диалогового окна.</p><p></p><p>Обязательный атрибут. Ожидается название одного из <a href="messageboxcommand.md#dialog_icon_types">типов иконки диалогового окна</a>.</p></td></tr></tbody></table>

#### Типы иконок диалогового окна <a href="#dialog_icon_types" id="dialog_icon_types"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="437.3333333333333"></th></tr></thead><tbody><tr><td align="center">None</td><td>Окно сообщения не содержит иконки</td></tr><tr><td align="center">Question</td><td>Окно сообщения содержит символ, состоящий из вопросительного знака, заключенного в кружок</td></tr><tr><td align="center">Error</td><td>Окно сообщения содержит символ, состоящий из белого значка Х, заключенного в красный кружок</td></tr><tr><td align="center">Warning</td><td>Окно сообщения содержит символ, состоящий из восклицательного знака в желтом треугольнике</td></tr><tr><td align="center">Information</td><td>Окно сообщения содержит символ, состоящий из буквы i в нижнем регистре, помещенной в кружок</td></tr></tbody></table>

### Buttons <a href="#buttons" id="buttons"></a>

Набор кнопок диалогового окна.

Необязательный тэг. Значение тэга `<Buttons>`: не ожидается

Если тэг `<Buttons>` отсутствует, то для атрибута `Type` используется значение OK.

```xml
<Buttons Type="Ok" />
```

#### Атрибуты тэга `<Buttons>` <a href="#attributes_tag_buttons" id="attributes_tag_buttons"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="460.3333333333333"></th></tr></thead><tbody><tr><td align="center">Type</td><td><p>Название набора кнопок диалогового окна.</p><p></p><p>Обязательный атрибут. Ожидается название одного из наборов кнопок диалогового окна.</p></td></tr></tbody></table>

#### Наборы кнопок диалогового окна <a href="#dialog_box_button_sets" id="dialog_box_button_sets"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="460.3333333333333"></th></tr></thead><tbody><tr><td align="center">OK</td><td>Окно сообщения содержит кнопку "ОК"</td></tr><tr><td align="center">OKCancel</td><td>Окно сообщения содержит кнопки "ОК" и "Отмена"</td></tr><tr><td align="center">AbortRetryIgnore</td><td>Окно сообщения содержит кнопки "Прервать", "Повторить" и "Пропустить"</td></tr><tr><td align="center">YesNoCancel</td><td>Окно сообщения содержит кнопки "Да", "Нет" и "Отмена"</td></tr><tr><td align="center">YesNo</td><td>Окно сообщения содержит кнопки "Да" и "Нет"</td></tr><tr><td align="center">RetryCancel</td><td>Окно сообщения содержит кнопки "Повторить" и "Отмена"</td></tr></tbody></table>
