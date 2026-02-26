---
description: >-
  Команда; генерирует PDF-файл на основе шаблона формата RTF, DOC или DOCX и
  скачивает этот файл.
---

# ConvertDocumentToPdfCommand

## Шаблон ConvertDocumentToPdfCommand <a href="#template_convert_document_to_pdf_command" id="template_convert_document_to_pdf_command"></a>

```xml
<Command Name="" Type="ConvertDocumentToPdfCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <Condition Name="" />
  <Lock Value="" />
  <!--Тэги, специфичные для ConvertDocumentToPdfCommand-->
  <TemplateFileName></TemplateFileName>
  <ExportFileName Ask=""></ExportFileName>
</Command>
```

## Описание ConvertDocumentToPdfCommand <a href="#description_convert_document_to_pdf_command" id="description_convert_document_to_pdf_command"></a>

```xml
<Command Name="ConvertDocumentToPdfCommandName" Type="ConvertDocumentToPdfCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <!--Тэги, специфичные для ConvertDocumentToPdfCommand-->
</Command>
```

### Результат выполнения ConvertDocumentToPdfCommand <a href="#result_convert_document_to_pdf_command" id="result_convert_document_to_pdf_command"></a>

#### Value <a href="#result_value" id="result_value"></a>

Команда не имеет результата.

## Тэги, специфичные для ConvertDocumentToPdfCommand <a href="#tags_convert_document_to_pdf_command" id="tags_convert_document_to_pdf_command"></a>

### TemplateFileName <a href="#template_file_name" id="template_file_name"></a>

Путь до файла шаблона. Поддерживаются форматы .rtf, .doc и .docx.

Обязательный тэг. Любое значение будет переведено в текстовое.

```xml
<TemplateFileName>TemplateFileName.doc</TemplateFileName>
```

### ExportFileName <a href="#export_file_name" id="export_file_name"></a>

Имя файла, с которым он будет скачан у пользователя.

Необязательный тэг. Любое значение будет переведено в текстовое.

Если указан полный путь, то из него будет извлечено имя файла, а остальное проигнорировано.

Если тэг `<ExportFileName>` отсутствует, то используется автоматически сгенерированное значение, а для атрибута `Ask` используется значение False.

```xml
<ExportFileName Ask="False">ExportFileName</ExportFileName>
```

#### Атрибуты тэга `<ExportFileName>` <a href="#attributes_tag_export_file_name" id="attributes_tag_export_file_name"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="454.3333333333333"></th></tr></thead><tbody><tr><td align="center">Ask</td><td><p>Признак, определяющий, будет ли задан вопрос о пути сохранения файлов. Диалоговое окно выбора пути показывается только при наличии на странице сертификата и  при наличии разрешения от пользователя на работу с файлами (в браузере). Если диалоговое окно не удалось показать, то загрузка будет выполнена без диалогового окна.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>Если атрибут <code>Ask</code> отсутствует, то используется значение False.</p></td></tr></tbody></table>
