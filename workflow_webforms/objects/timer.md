---
description: >-
  Таймер, выполняющий определенные команды в указанное время некоторое
  количество раз; не имеет графического отображения.
---

# Timer

## Шаблон Timer <a href="#template_timer" id="template_timer"></a>

Перечень всех возможных тэгов объекта:

```xml
<MyObject Name="" Type="Timer" Assembly="SimpleControls" ChangeForm="">
  <ManualStart></ManualStart>
  <StartTime></StartTime>
  <Interval></Interval>
  <StopCount></StopCount>
  <StopTime></StopTime>
  <StopCondition></StopCondition>
  <Commands StopOnError="" Lock="">
    <Command Name="" />
    <If>
      <When></When>
      <Then StopOnError="" Lock="">
        <Command Name="" />
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
</MyObject>
```

## Описание Timer <a href="#description_timer" id="description_timer"></a>

```xml
<MyObject Name="" Type="Timer" Assembly="SimpleControls" ChangeForm="True">
  <!--Тэги, специфичные для Timer-->
</MyObject>
```

#### Атрибуты Timer <a href="#attributes_timer" id="attributes_timer"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="457.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Название объекта.</p><p>Обязательный атрибут.</p></td></tr><tr><td align="center">Type</td><td><p>Название типа объекта в сборке.</p><p>Обязательный атрибут.</p></td></tr><tr><td align="center">Assembly</td><td><p>Название сборки (библиотека).</p><p>Обязательный атрибут.</p></td></tr></tbody></table>

### Получение значения Timer <a href="#get_value_timer" id="get_value_timer"></a>

Значением Timer считается значение, равное количеству совершенных запусков таймера.

```xml
<Object Name="TimerName" />
```

### Задание значения Timer <a href="#set_value_timer" id="set_value_timer"></a>

Значение объекта: любое значение.

```xml
<Object Name="TimerName"></Object>
```

## Тэги, специфичные для Timer <a href="#tags_timer" id="tags_timer"></a>

### Change <a href="#change" id="change"></a>

Настройки изменения проперти [`ValueChanged`](timer.md#get_value_changed) объекта.

Необязательный тэг.

Если тэг `<Change>` отсутствует, то для атрибутов `User`, `Source` и `ValueSet` используются значения True, True, и True соответственно.

```xml
<Change User="True" Source="False" ValueSet="True" />
```

#### Атрибуты тэга \<Change> <a href="#attributes_tag_change" id="attributes_tag_change"></a>

<table data-header-hidden><thead><tr><th width="150" align="center"></th><th width="534.3333333333333"></th></tr></thead><tbody><tr><td align="center">User</td><td><p>Признак, будет ли <a href="timer.md#get_value_changed"><code>ValueChanged</code></a> иметь значение True, если пользователь в графическом интерфейсе изменит значение объекта.</p><p></p><p>Обязательный атрибут. Ожидается логическое значение.</p></td></tr><tr><td align="center">Source</td><td><p>Признак, будет ли <a href="timer.md#get_value_changed"><code>ValueChanged</code></a> иметь значение True, если значение объекта перезагрузится из источника.</p><p></p><p>Если атрибут <code>Source</code> имеет значение False, и при этом значение из источника перезагрузилось, то <a href="timer.md#get_value_changed"><code>ValueChanged</code></a> будет иметь значение False.</p><p></p><p>Обязательный атрибут. Ожидается логическое значение.</p></td></tr><tr><td align="center">ValueSet</td><td><p>Признак, будет ли <a href="timer.md#get_value_changed"><code>ValueChanged</code></a> иметь значение True, если значение объекта будет присвоено из команды <a href="../commands/value_set_command.md"><code>ValueSetCommand</code></a>.</p><p></p><p>Если атрибут <code>ValueSet</code> имеет значение False, и при этом значение было присвоено из команды <a href="../commands/value_set_command.md"><code>ValueSetCommand</code></a>, то <a href="timer.md#get_value_changed"><code>ValueChanged</code></a> будет иметь значение False.</p><p></p><p>Обязательный атрибут. Ожидается логическое значение.</p></td></tr></tbody></table>

### ManualStart <a href="#manual_start" id="manual_start"></a>

Признак, определяющий, должен ли таймер запускаться вручную, а не сразу же после загрузки формы.

Необязательный тэг. Ожидается логическое значение.

По умолчанию используется значение False.

```xml
<ManualStart>False</ManualStart>
```

### StartTime <a href="#start_time" id="start_time"></a>

Дата и время начала работы таймера.

Необязательный тэг. Ожидается значение даты/времени.

Если значение тэга будет пустым, то таймер никогда не будет запущен.

Если тэг `<StartTime>` отсутствует, то ограничение на начало работы таймера не устанавливается.

Время, заданное в тэге `<StartTime>` не должно превышать текущее время работы программы больше чем на 2 147 483 647 миллисекунд (\~24 дня и 20 часов).

```xml
<StartTime>19.09.2014 13:57</StartTime>
```

### Interval <a href="#interval" id="interval"></a>

Интервал (в миллисекундах) между запусками цикла таймера.

Обязательный тэг. Ожидается положительное целочисленное значение.

```xml
<Interval>1000</Interval>
```

### StopCount <a href="#stop_count" id="stop_count"></a>

Количество выполненных циклов, требуемых для завершения работы таймера.

Необязательный тэг. Ожидается положительное целочисленное значение.

Если тэг `<StopCount>` отсутствует, то время работы таймера не ограничивается по количеству запусков.

```xml
<StopCount>5</StopCount>
```

### StopTime <a href="#stop_time" id="stop_time"></a>

Дата и время окончания работы таймера.

Необязательный тэг. Ожидается значение даты/времени.

Если тэг `<StopTime>` отсутствует, то время работы таймера не ограничивается по времени.

```xml
<StopTime>19.09.2014 14:04</StopTime>
```

### StopCondition <a href="#stop_condition" id="stop_condition"></a>

Прочее условие окончания работы таймера.

Необязательный тэг. Ожидается логическое значение.

Если тэг `<StopCondition>` отсутствует, то время работы таймера не ограничивается другими условиями.

```xml
<StopCondition>True</StopCondition>
```

### Commands <a href="#commands" id="commands"></a>

Список команд, которые будут выполнены в одном цикле таймера.

Необязательный тэг. В качестве значения тэга ожидается список тэгов [`<Command>`](timer.md#command) и/или конструкций [`<If>`](../values/if.md).

```xml
<Commands StopOnError="True"  Lock="">
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

<table data-header-hidden><thead><tr><th width="150" align="center"></th><th width="532.4285714285713"></th></tr></thead><tbody><tr><td align="center">StopOnError</td><td><p>Признак, определяющий, будет ли остановлено выполнение команд, если при выполнении очередной произойдет ошибка.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>По умолчанию используется значение True.</p></td></tr><tr><td align="center">Lock</td><td><p>Признак, определяющий, будет ли блокироваться форма при выполнении команд.</p><p></p><p>Необязательный атрибут. Ожидается логическое значение.</p><p></p><p>По умолчанию используется значение False.</p></td></tr></tbody></table>

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

## Get-проперти для получения свойств <a href="#get_property_timer" id="get_property_timer"></a>

### Value <a href="#get_value" id="get_value"></a>

Возвращает количество совершенных запусков таймера.

```xml
<Object Name="TimerName">
  <Property Name="Value" />
</Object>
```

### ValueChanged <a href="#get_value_changed" id="get_value_changed"></a>

Возвращает признак изменения количества совершенных запусков таймера.

Есть 3 способа изменить значение объекта:

1. Изменить значение прямым образом в графическом интерфейсе формы, с помощью set-проперти [`ValueChanged`](timer.md#set_value_changed).
2. Указать источник значения (ссылка на любые данные на форме). В случае изменения значения в источнике, автоматически изменится значение и самого объекта.
3. Присвоить значение объекту посредством команды [`ValueSetCommand`](../commands/value_set_command.md).

```xml
<Object Name="TimerName">
  <Property Name="ValueChanged" />
</Object>
```

### StartTime <a href="#get_start_time" id="get_start_time"></a>

Возвращает дату и время начала работы таймера.

```xml
<Object Name="TimerName">
  <Property Name="StartTime" />
</Object>
```

### Interval <a href="#get_interval" id="get_interval"></a>

Возвращает интервал (в миллисекундах) между запусками цикла таймера.

```xml
<Object Name="TimerName">
  <Property Name="Interval" />
</Object>
```

### StopCount <a href="#get_stop_count" id="get_stop_count"></a>

Возвращает количество выполненных циклов, требуемых для завершения работы таймера.

```xml
<Object Name="TimerName">
  <Property Name="StopCount" />
</Object>
```

### StopTime <a href="#get_stop_time" id="get_stop_time"></a>

Возвращает дату и время окончания работы таймера.

```xml
<Object Name="TimerName">
  <Property Name="StopTime" />
</Object>
```

### StopCondition <a href="#get_stop_condition" id="get_stop_condition"></a>

Возвращает прочее условие окончания работы таймера.

```xml
<Object Name="TimerName">
  <Property Name="StopCondition" />
</Object>
```

### Count <a href="#get_count" id="get_count"></a>

Возвращает количество совершенных запусков таймера.

```xml
<Object Name="TimerName">
  <Property Name="Count" />
</Object>
```

## Set-проперти для динамического задания свойств <a href="#set_property_timer" id="set_property_timer"></a>

### Value <a href="#set_value" id="set_value"></a>

Задает количество совершенных запусков таймера.

Ожидается целочисленное значение.

```xml
<Object Name="TimerName">
  <Property Name="Value">0</Property>
</Object>
```

### ValueChanged <a href="#set_value_changed" id="set_value_changed"></a>

Задает признак изменения значения количества совершенных запусков таймера.

Ожидается логическое значение.

```xml
<Object Name="TimerName">
  <Property Name="ValueChanged">False</Property>
</Object>
```

### StartTime <a href="#set_start_time" id="set_start_time"></a>

Задает дату и время начала работы таймера.

Ожидается значение даты/времени.

```xml
<Object Name="TimerName">
  <Property Name="StartTime">19.09.2014 14:09</Property>
</Object>
```

### Interval <a href="#set_interval" id="set_interval"></a>

Задает интервал (в миллисекундах) между запусками цикла таймера.

Ожидается положительное целочисленное значение.

```xml
<Object Name="TimerName">
  <Property Name="Interval">1000</Property>
</Object>
```

### StopCount <a href="#set_stop_count" id="set_stop_count"></a>

Задает количество выполненных циклов, требуемых для завершения работы таймера.

Ожидается положительное целочисленное значение.

```xml
<Object Name="TimerName">
  <Property Name="StopCount">5</Property>
</Object>
```

### StopTime <a href="#set_stop_time" id="set_stop_time"></a>

Задает дату и время окончания работы таймера.

Ожидается значение даты/времени.

```xml
<Object Name="TimerName">
  <Property Name="StopTime">19.09.2014 14:09</Property>
</Object>
```

### Count <a href="#set_count" id="set_count"></a>

Задает количество совершенных запусков таймера.

Ожидается целочисленное значение.

```xml
<Object Name="TimerName">
  <Property Name="Count">0</Property>
</Object>
```

### Start <a href="#set_start" id="set_start"></a>

Запускает таймер (при условии, что дата и время, соответствующие свойству [`<StartTime>`](timer.md#start_time), меньше текущего времени) и немедленно начинает выполнение его команд в соответствии с признаком ExecuteAfterStart.

```xml
<Object Name="TimerName">
  <!--Значение тэга Property: тэг Parameters со вложенными тэгами Parameter-->
  <Property Name="Start" >
    <Parameters>
      <!--Необязательный параметр. При отсутствии используется значение True-->
      <!--Значение тэга Parameter с атрибутом Name, равным ExecuteAfterStart: ожидается логическое значение-->
      <Parameter Name="ExecuteAfterStart">True</Parameter>
    </Parameters>
  </Property>
</Object>
```

### Stop <a href="#set_stop" id="set_stop"></a>

Останавливает выполнение команд таймера.

Значение тэга Property: не ожидается.

```xml
<Object Name="TimerName">
  <Property Name="Stop" />
</Object>
```
