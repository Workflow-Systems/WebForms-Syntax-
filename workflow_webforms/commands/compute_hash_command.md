---
description: >-
  Команда; вычисляет хеш строки с использованием выбранного алгоритма
  хеширования.
---

# ComputeHashCommand

## Шаблон ComputeHashCommand <a href="#template_compute_hash_command" id="template_compute_hash_command"></a>

```xml
<Command Name="" Type="ComputeHashCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <!--Тэги, специфичные для ComputeHashCommand-->
  <Algorithm></Algorithm>
  <Source></Source>
  <FilePath></FilePath>
</Command>
```

## Описание ComputeHashCommand <a href="#description_compute_hash_command" id="description_compute_hash_command"></a>

```xml
<Command Name="ComputeHashCommandName" Type="ComputeHashCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <!--Тэги, специфичные для ComputeHashCommand-->
</Command>
```

### Результат выполнения ComputeHashCommand <a href="#result_compute_hash_command" id="result_compute_hash_command"></a>

#### Value <a href="#result_value" id="result_value"></a>

Вычисленный хеш в виде строки или пустая строка, если хеш не удалось вычислить.

## Тэги, специфичные для ComputeHashCommand <a href="#tags_compute_hash_command" id="tags_compute_hash_command"></a>

### Algorithm <a href="#algorithm" id="algorithm"></a>

Название алгоритма хеширования.

Необязательный тэг. Ожидается название одного из алгоритмов хеширования.

Если тэг `<Algorithm>` отсутствует, то используется значение SHA512.

Полный список всех поддерживаем алгоритмов хеширования можно посмотреть по [ссылке](https://msdn.microsoft.com/ru-ru/library/wet69s13\(v=vs.110\).aspx).

```xml
<Algorithm>SHA512</Algorithm>
```

### Source <a href="#source" id="source"></a>

Строка, для которой будет вычислен хеш.

Необязательный тэг. Любое значение будет переведено в текстовое.

```xml
<Source>1234</Source>
```

### FilePath <a href="#file_path" id="file_path"></a>

Путь до файла, для которого будет вычислен хеш.

Необязательный тэг. Любое значение будет переведено в текстовое.

При наличии тэга [`<Source>`](compute_hash_command.md#source) тэг `<FilePath>` игнорируется, однако при его отсутствии тэг [`<Source>`](compute_hash_command.md#source) обязателен.

```xml
<FilePath>C:\pagefile.sys</FilePath>
```
