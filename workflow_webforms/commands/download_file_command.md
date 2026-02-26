---
description: Команда; выполняет загрузку файлов с сервера или из интернета.
---

# DownloadFileCommand

## Шаблон DownloadFileCommand <a href="#template_download_file_command" id="template_download_file_command"></a>

```xml
<Command Name="" Type="DownloadFileCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <Condition Name="" />
  <Lock Value="" />
  <!--Тэги, специфичные для DownloadFileCommand-->
  <FileGuid></FileGuid>
  <FileUrl></FileUrl>
  <ExportFileName Ask=""></ExportFileName>
</Command>
```

## Описание DownloadFileCommand <a href="#description_download_file_command" id="description_download_file_command"></a>

```xml
<Command Name="DownloadFileCommandName" Type="DownloadFileCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <!--Тэги, специфичные для DownloadFileCommand-->
</Command>
```

### Результат выполнения DownloadFileCommand <a href="#result_download_file_command" id="result_download_file_command"></a>

#### Value <a href="#result_value" id="result_value"></a>

Команда не имеет результата.

## Тэги, специфичные для DownloadFileCommand <a href="#tags_download_file_command" id="tags_download_file_command"></a>

### FileGuid <a href="#file_guid" id="file_guid"></a>

Guid'ы файлов на сервере.

Необязательный тэг.  Любое значение будет переведено в массив текстовых значений.

При наличии тэга `<FileGuid>` поле [`<FileUrl>`](download_file_command.md#file_url) игнорируется, однако при его отсутствии тэг [`<FileUrl>`](download_file_command.md#file_url) обязателен.

```xml
<FileGuid>Guid</FileGuid>
```

### FileUrl <a href="#file_url" id="file_url"></a>

URL'ы файлов в интернете.

Необязательный тэг. Любое значение будет переведено в массив текстовых значений.

Игнорируется при наличии тэга [`<FileGuid>`](download_file_command.md#file_guid).

```xml
<FileUrl>Ссылка</FileUrl>
```

### ExportFileName <a href="#export_file_name" id="export_file_name"></a>

Имена файлов, с которыми они будут скачаны у пользователя.

Необязательный тэг. Любое значение будет переведено в текстовое.

Если указан полный путь, то из него будет извлечено имя файла, а остальное проигнорировано.

Если тэг `<ExportFileName>` отсутствует, то имена файлов выбираются в соответствии с источниками файлов.

```xml
<ExportFileName Ask="False">ExportFileName</ExportFileName>
```

#### Атрибуты тэга `<ExportFileName>` <a href="#attributes_tag_export_file_name" id="attributes_tag_export_file_name"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="476.3333333333333"></th></tr></thead><tbody><tr><td align="center">Ask</td><td><p>Признак, определяющий, будет ли задан вопрос о пути сохранения файлов. Диалоговое окно выбора пути показывается только при наличии на странице сертификата и  при наличии разрешения от пользователя на работу с файлами (в браузере). Если диалоговое окно не удалось показать, то загрузка будет выполнена без диалогового окна.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>Если атрибут <code>Ask</code> отсутствует, то используется значение False.</p></td></tr></tbody></table>
