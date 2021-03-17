--- 
title: DisableInsertPropertyAttribute 
sidebar: flexberry-orm_sidebar 
keywords: data Objects, Flexberry ORM, database queries 
summary: Exception object from the request 
toc: true 
permalink: en/fo_disable-insert-property-attribute.html 
lang: en 
autotranslated: true 
hash: 59e4711c988ec1e7fc56a040860119afa588f47a8baa8c312fcaba8629781cd2 
--- 

[Attribute](fo_attributes-class-data.html) `DisableInsertPropertyAttribute` allows you to exclude the class property of the Insert queries generated by [service data](fo_data-service.html). It is recommended to use if there is a default value defined in database which should be used when creating [object](fo_data-object.html), or if the database itself when you insert correctly initialisere this value (different IDs). 

``` csharp
private int fId = 100;
[DisableInsertPropery(true))
public virtual int Id
{
	get
	{
		int result = this.fId;
		return result;
	}
	set
	{
		this.fId = value;
	}
}
``` 



{% include callout.html content="Переведено сервисом «Яндекс.Переводчик» <http://translate.yandex.ru>" type="info" %}