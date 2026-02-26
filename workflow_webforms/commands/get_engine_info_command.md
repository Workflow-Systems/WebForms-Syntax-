---
description: >-
  Команда; запрашивает информацию из среды серверной части (например, версию и
  дату сборки веб-сервиса).
---

# GetEngineInfoCommand

## Шаблон GetEngineInfoCommand <a href="#template_get_engine_info_command" id="template_get_engine_info_command"></a>

```xml
<Command Name="" Type="GetEngineInfoCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <Condition Name="" />
  <Lock Value="" />
  <!--Тэги, специфичные для GetEngineInfoCommand-->
  <Info Type="" />
</Command>
```

## Описание GetEngineInfoCommand <a href="#description_get_engine_info_command" id="description_get_engine_info_command"></a>

```xml
<Command Name="GetEngineInfoCommandName" Type="GetEngineInfoCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <!--Тэги, специфичные для GetEngineInfoCommand-->
</Command>
```

### Результат выполнения GetEngineInfoCommand <a href="#result_get_engine_info_command" id="result_get_engine_info_command"></a>

#### Value <a href="#result_value" id="result_value"></a>

Запрашиваемый с сервера результат.

## Тэги, специфичные для GetEngineInfoCommand <a href="#tags_get_engine_info_command" id="tags_get_engine_info_command"></a>

### Info <a href="#info" id="info"></a>

Тип получаемой с сервера информации.

Обязательный тэг. Значение тэга `<Info>`: не ожидается.

```xml
<Info Type="EngineAssemblyVersion" />
```

#### Атрибуты тэга `<Info>` <a href="#attributes_tag_info" id="attributes_tag_info"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Type</td><td><p>Название типа запроса информации, поддерживаемого сервером.</p><p></p><p>Обязательный атрибут. Ожидается название одного из <a href="get_engine_info_command.md#request_types">типов запросов информации, поддерживаемых сервером</a>.</p></td></tr></tbody></table>

#### Типы запросов информации, поддерживаемые сервером <a href="#request_types" id="request_types"></a>

<table data-header-hidden><thead><tr><th width="278.6296484971982" align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">EngineAssemblyVersion</td><td>Версия сборки веб-сервиса, указанной в формате "Major.Minor"</td></tr><tr><td align="center">EngineAssemblyVersionLong</td><td>Версия сборки веб-сервиса, указанной в формате "Major.Minor.Build.Revision"</td></tr><tr><td align="center">EngineAssemblyDateTime</td><td>Дата и время сборки веб-сервиса</td></tr></tbody></table>
