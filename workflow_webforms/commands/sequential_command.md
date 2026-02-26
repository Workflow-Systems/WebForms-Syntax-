---
description: Команда; выполняет несколько команд последовательно.
---

# SequentialCommand

## Шаблон SequentialCommand <a href="#template_sequential_command" id="template_sequential_command"></a>

```xml
<Command Name="" Type="SequentialCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <Condition Name="" />
  <Lock Value="" />
  <!--Тэги, специфичные для SequentialCommand-->
  <Commands StopOnError="" Lock="">
    <Command Name="" />
    <If>
      <When></When>
      <Then StopOnError="">
        <Command Name="" />
      </Then>
      <ElseIf>
        <When></When>
        <Then StopOnError="" Lock="">
          <Command Name="">
            <Input Name="" />
            <Input Name="" />
          </Command>
        </Then>
      </ElseIf>
      <Else StopOnError="" Lock="">
        <Command Name="" />
      </Else>
    </If>
  </Commands>
</Command>
```

## Описание SequentialCommand <a href="#description_sequential_command" id="description_sequential_command"></a>

```xml
<Command Name="SequentialCommandName" Type="SequentialCommand" Assembly="Commands">
  <!--Тэги, общие для всех команд-->
  <!--Тэги, специфичные для SequentialCommand-->
</Command>
```

### Результат выполнения SequentialCommand <a href="#result_sequential_command" id="result_sequential_command"></a>

Команда не имеет результата.

## Тэги, специфичные для SequentialCommand <a href="#tags_sequential_command" id="tags_sequential_command"></a>

### Commands <a href="#commands" id="commands"></a>

Список команд, которые будут выполнены последовательно.

Обязательный тэг. В качестве значения тэга ожидается список тэгов [`<Command>`](sequential_command.md#commands_command) и/или конструкций [`<If>`](../values/if.md#teg-less-than-if-greater-than).

```xml
<Commands StopOnError="True" Lock="">
  <Command Name="CommandName1" />
  <If>
    <When></When>
    <Then StopOnError="True" Lock="">
      <Command Name="CommandName2">
        <Input Name="InputName1">input 1</Input>
        <Input Name="InputName2">input 2</Input>
      </Command>
    </Then>
    <ElseIf>
      <When></When>
      <Then StopOnError="True" Lock="">
        <Command Name="CommandName3" />
      </Then>
    </ElseIf>
    <Else StopOnError="True" Lock="">
      <Command Name="CommandName4" />
    </Else>
  </If>
</Commands>
```

#### Атрибуты тэга `<Commands>` <a href="#attributes_tag_commands" id="attributes_tag_commands"></a>

<table data-header-hidden><thead><tr><th width="150" align="center"></th><th width="532.4285714285713"></th></tr></thead><tbody><tr><td align="center">StopOnError</td><td><p>Признак, определяющий, будет ли остановлено выполнение команд, если при выполнении очередной произойдет ошибка.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>По умолчанию используется значение False.</p></td></tr><tr><td align="center">Lock</td><td><p>Признак, определяющий, будет ли блокироваться форма при выполнении команд.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>По умолчанию используется значение False.</p></td></tr></tbody></table>

#### Тэг `<Command>` <a href="#commands_command" id="commands_command"></a>

Обращение к команде по имени для ее выполнения.

Необязательный тэг. В качестве значения тэга ожидается список тэгов [`<Input>`](../values/input.md).

```xml
<!--Вариант 1-->
<Command Name="CommandName1" />

<!--Вариант 2-->
<Command Name="CommandName2">
  <Input Name="InputName1">input 1</Input>
  <Input Name="InputName2">input 2</Input>
</Command>
```
