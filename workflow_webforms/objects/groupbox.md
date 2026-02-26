---
description: Графический объект; группирующая панель с каймой и заголовком.
---

# GroupBox

## Шаблон GroupBox <a href="#template_groupbox" id="template_groupbox"></a>

Перечень всех возможных тэгов объекта:

```xml
<MyObject Name="" Type="GroupBox" Assembly="BaseControls" ChangeForm="">
  <!--Тэги, общие для всех графических объектов-->
  <Top></Top>
  <Bottom></Bottom>
  <Left></Left>
  <Right></Right>
  <Height></Height>
  <Width></Width>
  <FontStyle></FontStyle>
  <ForeColor></ForeColor>
  <BackColor></BackColor>
  <Enabled></Enabled>
  <Visible></Visible>
  <Hint></Hint>
  <Change User="" Source="" ValueSet="" />
  <!--Тэги, специфичные для GroupBox-->
  <Text></Text>
  <MyObject Name="" Type="" Assembly="" />
  <MyObject Name="" Type="" Assembly="" />
</MyObject>
```

## Описание GroupBox <a href="#description_groupbox" id="description_groupbox"></a>

```xml
<MyObject Name="GroupBoxName" Type="GroupBox" Assembly="BaseControls">
  <!--Тэги, общие для всех графических объектов-->
  <!--Тэги, специфичные для GroupBox-->
</MyObject>
```

### Получение значения GroupBox <a href="#get_value_groupbox" id="get_value_groupbox"></a>

Значением GroupBox считается текст его заголовка.

```xml
<Object Name="GroupBoxName" />
```

### Задание значения GroupBox <a href="#set_value_groupbox" id="set_value_groupbox"></a>

Любое значение будет переведено в текстовое.

```xml
<Object Name="GroupBoxName"></Object>
```

## Тэги, специфичные для GroupBox <a href="#tags_groupbox" id="tags_groupbox"></a>

### Text <a href="#text" id="text"></a>

Заголовок панели.

Необязательный тэг. Любое значение будет переведено в текстовое.

```xml
<Text>Заголовок</Text>
```

### MyObject <a href="#my_object" id="my_object"></a>

Объект, расположенный на данной панели.

Необязательный тэг. Тэгов `<MyObject>` может быть несколько.

```xml
<MyObject Name="ObjectName1" Type="ObjectType1" Assembly="ObjectAssembly1" />
<MyObject Name="ObjectName2" Type="ObjectType2" Assembly="ObjectAssembly2" />
```

## Get-проперти для получения свойств <a href="#get_property_groupbox" id="get_property_groupbox"></a>

### ContainerChanged <a href="#get_container_changed" id="get_container_changed"></a>

Возвращает признак изменения объекта-контейнера (определяется как совокупность get-проперти `ValueChanged` всех его дочерних объектов на любом уровне вложенности).

```xml
<Object Name="GroupBoxName">
  <Property Name="ContainerChanged" />
</Object>
```

### ChangedObjects <a href="#get_changed_objects" id="get_changed_objects"></a>

Возвращает список изменённых объектов.

```xml
<Object>
  <Property Name="ChangedObjects" />
</Object>
```

### Text <a href="#get_text" id="get_text"></a>

Возвращает заголовок панели.

```xml
<Object Name="GroupBoxName">
  <Property Name="Text" />
</Object>
```

## Set-проперти для динамического задания свойств <a href="#set_property_groupbox" id="set_property_groupbox"></a>

### ContainerChanged <a href="#set_container_changed" id="set_container_changed"></a>

Задаёт признак изменения объекта-контейнера (определяется как совокупность get-проперти `ValueChanged` всех его дочерних объектов на любом уровне вложенности).

Ожидается логическое значение.

```xml
<Object Name="GroupBoxName">
  <Property Name="ContainerChanged" />
</Object>
```

### Text <a href="#set_text" id="set_text"></a>

Задает заголовок панели.

Любое значение будет переведено в текстовое.

```xml
<Object Name="GroupBoxName">
  <Property Name="Text">Заголовок</Property>
</Object>
```
