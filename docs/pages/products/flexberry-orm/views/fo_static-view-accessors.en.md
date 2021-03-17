--- 
title: Static properties to access the class representation 
sidebar: flexberry-orm_sidebar 
keywords: Flexberry ORM, data objects, performance 
summary: the benefits of using static class representations in application development 
toc: true 
permalink: en/fo_static-view-accessors.html 
lang: en 
autotranslated: true 
hash: 6fa8a18474617b3a75b9c4fb5f2ed011ed131516b75607a90aae955c28e1f9cb 
--- 

When loading objects almost always need to specify a [view](fd_view-definition.html). To this may be a string name of the desired view. This involves the following challenges: 

* The existence of a representation cannot be checked at compile time. 
* When writing code there is no convenient way to choose representation from a list of all class representations. 

For convenience, the classes of data objects added static properties to access all static [concepts class](fd_view-definition.html). For each generated service class, the nested class `Views`, and for each view is generated by a property to access this view. 

It is recommended to use these properties in any work ideas class. This allows to timely detect errors associated with the deletion or renaming of PDW submissions (this error will occur at compile time and not at run time). 

### Examples 

Without using static properties: 

``` csharp
View view = Information.GetView("КошкаL", typeof(Кошка));
``` 

Using static properties: 

``` csharp
View view = Кошка.Views.КошкаL;
``` 

Example of specifying the static properties is available at [https://github.com/Flexberry/FlexberryORM-DemoApp/blob/master/FlexberryORM/CDLIB/Objects/CDDA.cs](https://github.com/Flexberry/FlexberryORM-DemoApp/blob/master/FlexberryORM/CDLIB/Objects/CDDA.cs). 



{% include callout.html content="Переведено сервисом «Яндекс.Переводчик» <http://translate.yandex.ru>" type="info" %}