---
title: Консоль управления полномочиями (Security Console)
sidebar: ember-flexberry-security_sidebar
keywords: Flexberry Security
toc: true
permalink: ru/efs_security-console.html
lang: ru
---

## Консоль управления полномочиями (Security Console)

В консоли управления [полномочиями](efs_right-manager-module.html) задаются права на классы и на операции.

Консоль управления полномочиями собрана под 3.5 .NET Framework.

Основные нюансы работы с консолью управления полномочиями:

* Пермиссия `Full` (Полный доступ) означает что на запрос по любому из запросов на этот объект (`Update`, `Read` и т.д.) вернётся положительный ответ, т.е. права есть. Следует помнить, что пермиссии за исключением `Full` являются независимыми, т.е. наличие прав на обновление не даёт автоматически права на чтение этого объекта (такое разделение реально может использоваться, например, при работе бизнес-сервера, когда объект обновляется, но пользователь его не вычитывает).
* Наименование операции не может содержать символ _ (нижнее подчеркивание), так как этот символ будет использоваться как разделитель в системных целях и приведет к ошибкам в дальнейшем.
* В версии после 18.07.2014 в win-консоли добавлена следующая логика: если пользователь выбирает пермиссию `Full`, то галочки на остальные пермиссии (`Update`, `Read` и т.д.) убираются и блокируются (их нельзя поставить, пока выставлена пермиссия `Full`). При этом старые пермиссии при открытии новой версией консоли изменяться самостоятельно не будут.

## Смотрите также

* [Сценарии использования подсистемы полномочий](efs_rights-scenarios.html).
* [Сервис полномочий Flexberry Rights (CheckingLibrary)](efs_security-legacy-services.html)
* [Подсистема полномочий в WEB](fa_right-manager.html).
* [Проверка сложности пароля в консоли безопасности](efs_checking-password-complexity-in-security-console.html)
* [Добавление пользователей в БД системы полномочий при windows-аутентификации](fa_authentication-adapter.html).