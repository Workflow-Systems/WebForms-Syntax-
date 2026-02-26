---
description: Объект; не имеет графического отображения.
---

# Variable

## Шаблон Variable <a href="#template_variable" id="template_variable"></a>

```xml
<MyObject Name="" Type="Variable" Assembly="SimpleControls" ChangeForm="">
  <Change User="" Source="" ValueSet="" />
  <Value></Value>
</MyObject>
```

## Описание Variable <a href="#description_variable" id="description_variable"></a>

```xml
<MyObject Name="" Type="Variable" Assembly="SimpleControls" ChangeForm="True">
  <!--Тэги, специфичные для Variable-->
</MyObject>
```

#### Атрибуты объекта Variable <a href="#attributes_variable" id="attributes_variable"></a>

<table data-header-hidden><thead><tr><th align="center"></th><th width="428.3333333333333"></th></tr></thead><tbody><tr><td align="center">Name</td><td><p>Название объекта Variable.</p><p>Обязательный атрибут.</p></td></tr><tr><td align="center">Type</td><td><p>Название типа объекта Variable в сборке.</p><p>Обязательный атрибут.</p></td></tr><tr><td align="center">Assembly</td><td><p>Название сборки (библиотека).</p><p>Обязательный атрибут.</p></td></tr></tbody></table>

### Получение значения Variable <a href="#get_value_variable" id="get_value_variable"></a>

Значением Variable считается значение, указанное в тэге [`<Value>`](variable.md#value).

```xml
<Object Name="VariableName" />
```

Значение объекта: любое значение.

### Задание значения Variable <a href="#set_value_variable" id="set_value_variable"></a>

```xml
<Object Name="VariableName"></Object>
```

## Тэги, специфичные для Variable <a href="#tags_variable" id="tags_variable"></a>

### Change <a href="#change" id="change"></a>

Настройки изменения проперти [`ValueChanged`](variable.md#valuechanged) объекта.

Необязательный тэг.

Если тэг `<Change>` отсутствует, то для атрибутов `User`, `Source` и `ValueSet` используются значения True, True, и True соответственно.

```xml
<Change User="True" Source="False" ValueSet="True" />
```

#### Атрибуты тэга \<Change> <a href="#attributes_tag_change" id="attributes_tag_change"></a>

<table data-header-hidden><thead><tr><th width="177.95518753044328" align="center"></th><th width="534.3333333333333"></th></tr></thead><tbody><tr><td align="center">User</td><td><p>Признак, будет ли <a href="variable.md#valuechanged"><code>ValueChanged</code></a> иметь значение True, если пользователь в графическом интерфейсе изменит значение объекта.</p><p></p><p>Обязательный атрибут. Ожидается логическое значение.</p></td></tr><tr><td align="center">Source</td><td><p>Признак, будет ли <a href="variable.md#valuechanged"><code>ValueChanged</code></a> иметь значение True, если значение объекта перезагрузится из источника.</p><p></p><p>Если атрибут <code>Source</code> имеет значение False, и при этом значение из источника перезагрузилось, то <a href="variable.md#valuechanged"><code>ValueChanged</code></a> будет иметь значение False.</p><p></p><p>Обязательный атрибут. Ожидается логическое значение.</p></td></tr><tr><td align="center">ValueSet</td><td><p>Признак, будет ли <code>ValueChanged</code> иметь значение True, если значение объекта будет присвоено из команды <a href="../commands/value_set_command.md"><code>ValueSetCommand</code></a>.</p><p></p><p>Если атрибут <code>ValueSet</code> имеет значение False, и при этом значение было присвоено из команды <a href="../commands/value_set_command.md"><code>ValueSetCommand</code></a>, то <code>ValueChanged</code> будет иметь значение False.</p><p></p><p>Обязательный атрибут. Ожидается логическое значение.</p></td></tr></tbody></table>

### Value <a href="#value" id="value"></a>

Значение объекта Variable.

Необязательный тэг. Значение тэга `<Value>`: любое значение.

Если тэг `<Value>` отсутствует, то используется значение NULL.

```xml
<Value>Value</Value>
```

## Get-проперти для получения свойств <a href="#get_property_variable" id="get_property_variable"></a>

### Value <a href="#get_value" id="get_value"></a>

Возвращает значение объекта Variable, если он его имеет.

```xml
<Object Name="VariableName">
  <Property Name="Value" />
</Object>
```

### ValueChanged <a href="#get_value_changed" id="get_value_changed"></a>

Возвращает признак того, было ли изменено значение объекта Variable в процессе работы.

Есть 3 способа изменить значение объекта:

1. Изменить значение прямым образом в графическом интерфейсе формы, с помощью set-проперти [`ValueChanged`](variable.md#valuechanged-1).
2. Указать источник значения (ссылка на любые данные на форме). В случае изменения значения в источнике, автоматически изменится значение и самого объекта.
3. Присвоить значение объекту посредством команды [`ValueSetCommand`](../commands/value_set_command.md).

```xml
<Object Name="VariableName">
  <Property Name="ValueChanged" />
</Object>
```

## Set-проперти для динамического задания свойств <a href="#set_property_variable" id="set_property_variable"></a>

### Value <a href="#set_value" id="set_value"></a>

Задает значение объекта Variable.

Значение тэга `<Property>`: любое значение.

```xml
<Object Name="VariableName">
  <Property Name="Value">Value</Property>
</Object>
```

### ValueChanged <a href="#set_value_changed" id="set_value_changed"></a>

Задает признак изменения значения объекта Variable.

Значение тэга `<Property>`: ожидается логическое значение.

```xml
<Object Name="VariableName">
  <Property Name="ValueChanged">False</Property>
</Object>
```

## Примеры <a href="#examples_variable" id="examples_variable"></a>

Работают только со числами. Со строками не работают вообще.

### Пример 1. Работающий. <a href="#example_1" id="example_1"></a>

```xml
<MyObject Name="Variable" Type="Variable" Assembly="SimpleControls">
  <Value>
	<Calculate>
	  <Expression>if({0}={1}, 1, 2)</Expression>
	  <Items>
		<Item>1</Item>
		<Item>0</Item>
	  </Items>
	</Calculate>
  </Value>
</MyObject>
```

### Пример 2. Не работающий. <a href="#example_2" id="example_2"></a>

```xml
<MyObject Name="Variable" Type="Variable" Assembly="SimpleControls">
  <Value>
	<Calculate>
	  <Expression>if({0}='test', 1, 2)</Expression>
	  <Items>
		<Item>test</Item>
		<Item>0</Item>
	  </Items>
	</Calculate>
  </Value>
</MyObject>
```
