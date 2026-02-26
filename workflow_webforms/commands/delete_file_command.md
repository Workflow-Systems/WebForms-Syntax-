---
description: Команда; удаляет файлы с сервера.
---

# DeleteFileCommand

## Шаблон DeleteFileCommand <a href="#template_delete_file_command" id="template_delete_file_command"></a>

```xml
<Command Name="" Type="DeleteFileCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <Condition Name="" />
  <Lock Value="" />
  <!--Тэги, специфичные для DeleteFileCommand-->
  <FileGuid></FileGuid>
</Command>
```

## Описание DeleteFileCommand <a href="#description_delete_file_command" id="description_delete_file_command"></a>

```xml
<Command Name="DeleteFileCommandName" Type="DeleteFileCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <!--Тэги, специфичные для DeleteFileCommand-->
</Command>
```

### Результат выполнения DeleteFileCommand <a href="#result_delete_file_command" id="result_delete_file_command"></a>

Команда не имеет результата.

## Тэги, специфичные для DeleteFileCommand <a href="#tags_delete_file_command" id="tags_delete_file_command"></a>

### FileGuid <a href="#file_guid" id="file_guid"></a>

Guid'ы файлов на сервере.

Обязательный тэг. Любое значение будет переведено в массив текстовых значений.

```xml
<FileGuid>Guid</FileGuid>
```

### ThrowException <a href="#throw_exception" id="throw_exception"></a>

Признак, определяющий, будут ли проигнорированы все ошибки при выполнении команды.

Необязательный тэг. Ожидается логическое значение.

Если тэг `<ThrowException>` отсутствует, то значение по умолчанию True. Если значение будет False, то ошибки будут проигнорированы.

```xml
<ThrowException></ThrowException>
```
