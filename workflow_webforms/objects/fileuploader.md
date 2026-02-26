---
description: Объект, предназначенный для загрузки файлов пользователем
---

# FileUploader

## Шаблон FileUploader <a href="#template_datetimepicker" id="template_datetimepicker"></a>

Перечень всех возможных тэгов объекта:

```xml
<MyObject Name="" Type="FileUploader" Assembly="BaseControls" ChangeForm="">
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
  <!--Тэги, специфичные для FileUploader-->
  <FileExtensions></FileExtensions>  
  <MaxAllowedFiles></MaxAllowedFiles> 
  <MaxFileSize></MaxFileSize>
</MyObject>
```

## Описание FileUploader <a href="#description_datetimepicker" id="description_datetimepicker"></a>

```xml
<MyObject Name="FileUploaderName" Type="FileUploader" Assembly="BaseControls">
  <!--Тэги, общие для всех графических объектов-->
  <!--Тэги, специфичные для FileUploader-->
</MyObject>
```

### Получение значения FileUploader <a href="#get_value_datetimepicker" id="get_value_datetimepicker"></a>

Значением `FileUploader` является список Guid-ов тех файлов, которые были загружены на Engine. Для получения списков Guid-ов файлов используется get-проперти `GuidList`:

```xml
<Object Name="FileUploaderName">
  <Property Name="GuidList" />
</Object>
```

### Задание значения FileUploader <a href="#set_value_datetimepicker" id="set_value_datetimepicker"></a>

Задать значение `FileUploader` нельзя.

## Тэги, специфичные для FileUploader

### FileExtensions

Допустимые расширения файлов (в диалоговом окне выбора файлов у пользователя).

Необязательный тэг. Любое значение будет переведено в текстовое. Ожидается список расширений файлов через запятую или специальные значения, обозначающие группы файлов. Подробнее по [ссылке](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/accept).

```xml
<FileExtensions>.doc, .docx</FileExtensions>
```

```xml
<FileExtensions>image/*</FileExtensions>
```

### MaxAllowedFiles

Максимальное допустимое количество файлов при загрузке.

Необязательный тэг. Ожидается целочисленное значение.

По умолчанию используется значение 1.

```xml
<MaxAllowedFiles>3</MaxAllowedFiles>
```

### MaxFileSize

Максимально допустимый размер файла (в Мб).

Необязательный тэг. Ожидается целочисленное значение.

По умолчанию используется значение 10.

{% hint style="warning" %}
Не рекомендуется указывать слишком большой допустимый размер файла, т.к. это может привести к серьезному увеличению нагрузки на сервер, где расположены WebForms.
{% endhint %}

```xml
<MaxFileSize>5</MaxFileSize>
```

## Get-проперти для получения свойств

### FileExtensions

Возвращает список допустимых расширений файлов.

```xml
<Object Name="FileUploaderName">
  <Property Name="FileExtensions" />
</Object>
```

### MaxAllowedFiles

Возвращает максимально допустимое количество файлов при загрузке.

```xml
<Object Name="FileUploaderName">
  <Property Name="MaxAllowedFiles" />
</Object>
```

### MaxFileSize

Возвращает максимально допустимый размер файла.

```xml
<Object Name="FileUploaderName">
  <Property Name="MaxFileSize" />
</Object>
```

### GuidList <a href="#get_password" id="get_password"></a>

Возвращает массив Guid-ов файлов, которые были успешно загружены на Engine.

```xml
<Object Name="FileUploaderName">
  <Property Name="GuidList" />
</Object>
```

## Set-проперти для динамического задания свойств

### FileExtensions

Задает допустимые расширения файлов (в диалоговом окне выбора файлов у пользователя).

Ожидается список расширений файлов через запятую или специальные значения, обозначающие группы файлов. Подробнее по [ссылке](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/accept).

```xml
<Object Name="FileUploaderName">
  <Property Name="FileExtensions">.jpg</Property>
</Object>
```

### MaxAllowedFiles

Задает максимальное допустимое количество файлов при загрузке.

Ожидается целочисленное значение.

```xml
<Object Name="FileUploaderName">
  <Property Name="MaxAllowedFiles">3</Property>
</Object>
```

### MaxFileSize

Задает максимально допустимый размер файла (в Мб).

Ожидается целочисленное значение.

```xml
<Object Name="FileUploaderName">
  <Property Name="MaxFileSize">5</Property>
</Object>
```
