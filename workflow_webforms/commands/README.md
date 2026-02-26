---
description: Команда, выполняемая на клиентском приложении.
---

# Commands

## Описание Command <a href="#description_command" id="description_command"></a>

```xml
<Command Name="CommandName" Type="CommandType" Assembly="CommandAssembly">
  <!--Тэги, общие для всех команд-->
  <!--Тэги, специфичные для определенной команды (зависит от типа)-->
</Command>
```

Команда может иметь результат, которой может состоять из нескольких значений.

#### Атрибуты Command <a href="#attributes_command" id="attributes_command"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="446.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Название команды.</p><p></p><p>Обязательный атрибут.</p></td></tr><tr><td align="center">Type</td><td><p>Название типа команды в сборке.</p><p></p><p>Обязательный атрибут.</p></td></tr><tr><td align="center">Assembly</td><td><p>Название сборки (библиотека).</p><p></p><p>Обязательный атрибут.</p></td></tr></tbody></table>

## Тэги, общие для всех команд <a href="#common_tags" id="common_tags"></a>

### Condition <a href="#condition" id="condition"></a>

Дополнительное условие проверки при запуске команды: если значение условия True, то команда выполняется, в противном случае - нет.

Необязательный тэг. Значение тэга `<Condition>`: не ожидается.

```xml
<Condition Name="ConditionName" />
```

#### Атрибуты тэга `<Condition>` <a href="#attributes_tag_condition" id="attributes_tag_condition"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="446.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Имя условия.</p><p></p><p>Обязательный атрибут. Ожидается одно из имен условий, описанных на форме в разделе условий.</p></td></tr></tbody></table>

### Lock <a href="#lock" id="lock"></a>

Признак, определяющий, пределяющий, будет ли выполнение команды вызывать блокировку формы.

Необязательный тэг. Значение тэга `<Lock>`: не ожидается.

Если тэг `<Lock>` отсутствует, то для атрибута `Value` используется значение False.

```xml
<Lock Value="True" />
```

#### Атрибуты тэга `<Lock>` <a href="#attributes_tag_lock" id="attributes_tag_lock"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="446.3333333333333"></th></tr></thead><tbody><tr><td align="center">Value</td><td><p>Значение.</p><p></p><p>Обязательный атрибут. Ожидается логическое значение.</p></td></tr></tbody></table>
