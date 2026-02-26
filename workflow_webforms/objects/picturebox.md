---
description: Графический объект; поле с изображением.
---

# PictureBox

## Шаблон PictureBox <a href="#template_picturebox" id="template_picturebox"></a>

Перечень всех возможных тэгов объекта:

```xml
<MyObject Name="" Type="PictureBox" Assembly="BaseControls" ChangeForm="">
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
  <!--Тэги, специфичные для PictureBox-->
  <SizeMode></SizeMode>
  <NullImage></NullImage>
  <Image></Image>
</MyObject>
```

## Описание PictureBox <a href="#description_picturebox" id="description_picturebox"></a>

```xml
<MyObject Name="PictureBoxName" Type="PictureBox" Assembly="BaseControls">
  <!--Тэги, общие для всех графических объектов-->
  <!--Тэги, специфичные для PictureBox-->
</MyObject>
```

### Получение значения PictureBox <a href="#get_value_picturebox" id="get_value_picturebox"></a>

Значением PictureBox считается источник текущего отображаемого изображения.

```xml
<Object Name="PictureBoxName" />
```

### Задание значения PictureBox <a href="#set_value_picturebox" id="set_value_picturebox"></a>

Значение объекта: любое значение будет интерпретировано как источник.

```xml
<Object Name="PictureBoxName"></Object>
```

## Тэги, специфичные для PictureBox <a href="#tags_picturebox" id="tags_picturebox"></a>

### SizeMode <a href="#size_mode" id="size_mode"></a>

Название типа размера изображения.

Необязательный тэг. Ожидается название одного из типов размеров изображения:

<table data-header-hidden><thead><tr><th width="151.29466359193583" align="center"></th><th width="540.1606663084364"></th></tr></thead><tbody><tr><td align="center">Normal</td><td><p>Изображение не масштабируется. Помещается в левом верхнем углу. <br>Если размер <code>PictureBox</code> больше размера изображения - изображение помещается в центре <code>PictureBox</code>.</p><p>Если размер изображения больше размера <code>PictureBox</code>, его края будут обрезаны.</p></td></tr><tr><td align="center">StretchImage</td><td><p>Изображение растягивается или сжимается, чтобы в точности соответствовать размеру <code>PictureBox</code>.</p><p>Пропорции изображения не сохраняются.</p></td></tr><tr><td align="center">None</td><td><p>Изображение не масштабируется. Помещается в левом верхнем углу.</p><p>Если размер изображения больше размера <code>PictureBox</code>, его края будут обрезаны.</p></td></tr><tr><td align="center">CenterImage</td><td>Изображение не масштабируется. Помещается в центре.<br>Если размер изображения больше размера <code>PictureBox</code>, его края будут обрезаны.</td></tr><tr><td align="center">Zoom</td><td>Размер изображения изменяется, чтобы в соответствовать высоте или ширине <code>PictureBox</code>.<br>Пропорции изображения сохраняются.</td></tr></tbody></table>

По умолчанию используется значение Zoom.

```xml
<SizeMode>Zoom</SizeMode>
```

### NullImage <a href="#initial_image" id="initial_image"></a>

Источник изображения, которое будет использоваться в качестве изображения поля, если значение поля установлено в NULL.

Необязательный тэг. Ожидается источник изображения.

Если тэг `<NullImage>` отсутствует, то используется системное изображение.

```xml
<NullImage>Images\NullImage.png</NullImage>
```

### Image <a href="#image" id="image"></a>

Источник изображения, которое будет использоваться в качестве начального отображаемого изображения при загрузке формы.

Необязательный тэг. Ожидается источник изображения.

```xml
<Image>http://wfsys.ru/image.bmp</Image>
```

#### Источники изображений <a href="#image_sources" id="image_sources"></a>

1. Сокращенный путь до файла - например, "Images\Sample.png" (в качестве исходной папки будет взята папка с расположением формы, на которой описано данное поле).
2. Полный путь до файла изображения на Engine (в случае, если Engine и Workflow WebForms запущены на одном компьютере и соответствующая настройка указана в конфигурационном файле WebForms).
3. Ссылка на интернет-ресурс по протоколам http://, https:// или ftp:// - например, "[http://wfsys.ru/sample.png](http://wfsys.ru/sample.png)".
4. GUID файла, расположенного на сервере, - например, "cbed3d33-7591-49ff-8119-8ad7e3c81599".

## Get-проперти для получения свойств <a href="#get_property_picturebox" id="get_property_picturebox"></a>

### SizeMode <a href="#get_size_mode" id="get_size_mode"></a>

Возвращает название типа размера изображения.

```xml
<Object Name="PictureBoxName">
  <Property Name="SizeMode" />
</Object>
```

### NullImage <a href="#get_null_image" id="get_null_image"></a>

Возвращает [источник изображения](picturebox.md#image_sources), которое будет использоваться в качестве изображения поля, если значение поля установлено в NULL.&#x20;

```xml
<Object Name="PictureBoxName">
  <Property Name="NullImage" />
</Object>
```

### Image <a href="#get_image" id="get_image"></a>

Возвращает [источник изображения](picturebox.md#image_sources), которое будет использоваться в качестве начального отображаемого изображения при загрузке формы.&#x20;

```xml
<Object Name="PictureBoxName">
  <Property Name="Image" />
</Object>
```

## Set-проперти для динамического задания свойств <a href="#set_property_picturebox" id="set_property_picturebox"></a>

### SizeMode <a href="#set_size_mode" id="set_size_mode"></a>

Задает название типа размера изображения.

Ожидается название одного из типов размеров изображения.

```xml
<Object Name="PictureBoxName">
  <Property Name="SizeMode">StretchImage</Property>
</Object>
```

### NullImage <a href="#set_null_image" id="set_null_image"></a>

Задает [источник изображения](picturebox.md#image_sources), которое будет использоваться в качестве изображения поля, если значение поля установлено в NULL.

Ожидается источник изображения.

```xml
<Object Name="PictureBoxName">
  <Property Name="NullImage">\\SHARE\Images\NullImage.png</Property>
</Object>
```

### Image <a href="#set_image" id="set_image"></a>

Задает [источник изображения](picturebox.md#image_sources), которое будет использоваться в качестве начального отображаемого изображения при загрузке формы.

Ожидается источник изображения.

```xml
<Object Name="PictureBoxName">
  <Property Name="Image">guid://26c7d4b6-2b4a-48f3-bde1-def012932219</Property>
</Object>
```
