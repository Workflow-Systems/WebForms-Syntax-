# Executions



## Описание Execution <a href="#description_execution" id="description_execution"></a>

Значение: тэги [`<ConditionExpression>`](executions.md#condition_expression) и [`<Commands>`](executions.md#commands).

```xml
<Execution>
  <ConditionExpression>
    <Or>
      <Not>
        <And>
          <Condition Name="" />
          <Condition Name="" />
          <Condition Name="" />
        </And>
      </Not>
      <And>
        <Condition Name="" />
        <Condition Name="" />
      </And>
    </Or>
  </ConditionExpression>
  <Commands StopOnError="" Lock="">
    <Command Name="" />
    <If>
      <When></When>
      <Then StopOnError="" Lock="">
        <Command Name="">
          <Input Name="" />
          <Input Name="" />
        </Command>
      </Then>
      <ElseIf>
        <When></When>
        <Then StopOnError="" Lock="">
          <Command Name="" />
        </Then>
      </ElseIf>
      <Else StopOnError="" Lock="">
        <Command Name="" />
      </Else>
    </If>
  </Commands>
</Execution>
```

### ConditionExpression <a href="#condition_expression" id="condition_expression"></a>

Логическое выражение из значений условий.

Обязательный тэг. Ожидается логическое выражение с использованием тэгов `<And>`, `<Or>`, `<Not>` в качестве операций и тэгов [`<Condition>`](conditions/) в качестве операндов.

### Commands <a href="#commands" id="commands"></a>

Список команд, которые будут выполнены при наступлении условий.

Обязательный тэг. Значение тэга `<Commands>`: список тэгов [`<Command>`](executions.md#commands_command) и [`<If>`](values/if.md).

#### Атрибуты тэга `<Commands>` <a href="#attributes_tag_commands" id="attributes_tag_commands"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="475.3333333333333"></th></tr></thead><tbody><tr><td align="center">StopOnError</td><td><p>Признак, определяющий, будет ли остановлено выполнение команд, если при выполнении очередной произойдет ошибка.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>Если атрибут <code>StopOnError</code> отсутствует, то используется значение False.</p></td></tr><tr><td align="center">Lock</td><td><p>Признак, определяющий, будет ли блокироваться форма при выполнении команд.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>Если атрибут <code>Lock</code> отсутствует, то используется значение False.</p></td></tr></tbody></table>

#### Тэг `<Command>` <a href="#commands_command" id="commands_command"></a>

Обращение к команде по имени для ее выполнения.

Необязательный тэг. В качестве значения тэга ожидается список тэгов [`<Input>`](values/input.md).

```xml
<!--Вариант 1-->
<Command Name="CommandName1" />

<!--Вариант 2-->
<Command Name="CommandName2">
  <Input Name="InputName1">input 1</Input>
  <Input Name="InputName2">input 2</Input>
</Command>
```
