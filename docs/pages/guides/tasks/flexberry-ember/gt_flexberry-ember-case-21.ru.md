---
title: Вариант 21 - «Горводоканал»
keywords: Tasks
sidebar: guide-tasks_sidebar
toc: true
permalink: ru/gt_flexberry-ember-case-21.html
lang: ru
summary: Вариант сквозного задания на проектирование и разработку с использованием фреймворка Flexberry Ember
---

## Задание

В рамках выполнения практической части курса вами будет разработан сквозной пример: приложение «Сменные задания бригад Горводоканала» (ИС для автоматизации учета заявок и выполнения работ по ним).

Первая часть практического задания будет посвящена освоению базовых технологий, таких как C#, базы данных, клиентские технологии и т.п., вторая часть будет включать изучение возможностей платформы Flexberry для эффективного создания приложений.

## Общее описание предметной области

Диспетчерская водоканала принимает от жителей обращения об авариях в городе, на их основе составляет аварийные заявки, которые включают в свои сменные задания мобильные бригады. Каждая заявка имеет адрес и включает в себя несколько работ (например, раскопать, заварить трубу, закопать). У каждой работы есть плановая и фактическая длительность в часах. Сменное задание представляется в виде списка пунктов, в рамках одного пункта (строки) сменного задания может быть проведена одна или несколько работ по одной заявке.

Технические требования:

*	Приложение реализуется в виде [SPA-приложения](https://ru.wikipedia.org/wiki/%D0%9E%D0%B4%D0%BD%D0%BE%D1%81%D1%82%D1%80%D0%B0%D0%BD%D0%B8%D1%87%D0%BD%D0%BE%D0%B5_%D0%BF%D1%80%D0%B8%D0%BB%D0%BE%D0%B6%D0%B5%D0%BD%D0%B8%D0%B5) с бакендом на C# и фронтендом на EmberJS.
*	Данные хранятся в БД Postgres.

## Практическое задание №1 - Серверная разработка (C#, .NET, ASP.NET)

Для реализации потребуется:

* Microsoft Visual Studio 2017
* Git for Windows

### Задание

Требуется реализовать алгоритм вычисления оптимального распределения работ по сменным заданиям мобильных бригад в рамках суток. Каждая заявка имеет свою важность от 0 до 4 (наиболее важная), каждая работа в заявке имеет плановую длительность выполнения.
Между точками заявок бригады перемещаются за 1 час. Незаконченная заявка считается невыполненной.

На вход алгоритму подаётся:

*	Массив заявок: порядковый номер, важность
*	Массив работ: наименование, плановая длительность выполнения, номер заявки
*	Массив бригад: наименование, время начала смены, время окончания смены

На выходе должен быть получен двумерный массив, в котором каждая строка представляет одну бригаду, а каждый элемент в строке – порядковый номер обхода заявок.

Реализацию следует сделать в виде .Net-библиотеки и подготовить модульные тесты для неё (xUnit), продемонстрировать процент покрытия кода модульными тестами (чем больше, тем лучше).


### Предоставление результатов выполнения работы на проверку

Реализованное решение (Visual Studio Solution) полностью разместить в репозитории на GitHub (решение должно компилироваться и запускаться). Ссылку на репозиторий предоставить преподавателям курса.

## Практическое задание №2 - Клиентская разработка (HTML, CSS, JS, jQuery)

Для реализации потребуется:

* Редактор кода для клиентской разработки: Visual Studio Code
* Git for Windows

### Задание

С использованием возможностей HTML, CSS, JS, jQuery сверстать форму, на которой пользователь может указать мобильную бригаду, дату и получить информацию о её сменном задании на неделю. Форма должна напоминать почасовой календарь в разрезе недели. В каждой ячейке таблицы должна быть указана строка сменного задания, которое выполнялось или будет выполняться бригадой.

### Предоставление результатов

Реализованный проект разместить в репозитории на GitHub в виде встроенных страниц GitHub Pages, позволяющих просматривать готовый результат. Ссылку на репозиторий и опубликованный таким образом проект предоставить преподавателям курса.

## Практическое задание №3 - Клиентская разработка с использованием SPA-фреймфорка (EmberJS)

Для реализации потребуется:

* Редактор кода для клиентской разработки: Visual Studio Code
* Git for Windows

### Задание

Требуется реализовать EmberJS приложение, в котором будет реализована форма, на которой пользователь может указать бригаду и дату и получить информацию о её сменном задании на неделю. Форма должна напоминать почасовой календарь в разрезе недели. В каждой ячейке таблицы должна быть указана строка сменного задания, которое выполнялось или будет выполняться бригадой. Под календарём должен выводиться список предлагаемых заявок для подразделения (компонент Ember.js).

В виде Ember.js-утилиты требуется реализовать алгоритм вычисления оптимального распределения заявок по бригадам в рамках смен (см. задание №1).

Требуется реализовать компонент, в который передаётся id бригады и дата, а он будет отображать список заявок, которые могут быть выполнены бригадой с наибольшей выгодой для Горводоканала. Использовать в компоненте Ember.js-утилиту, реализующую алгоритм вычисления оптимального распределения заявок.

### Предоставление результатов

Реализованный проект разместить в репозитории на GitHub в виде проекта Ember.js и опубликованного приложения на GitHub Pages, которые позволяют просматривать готовый результат. Ссылку на репозиторий и опубликованный таким образом проект предоставить преподавателям курса.

## Практическое задание №4 - Базы данных

Для реализации потребуется:

*	Postgres
*	pgAdmin
*	Git for Windows

### Задание

Для указанной предметной области реализовать базу данных, заполнить базу скриптами (минимум по 5 записей на таблицу). Реализовать скрипты по созданию ограничений, индексов.

Подготовить SQL-скрипты для получения следующей информации:

1.	Вывести топ-5 адресов с наибольшим количеством аварий
2.	Вывести информацию о количестве устранённых заявок каждой бригадой в порядке убывания
3.	Вывести информацию о среднем времени выполнения каждого типа работ
4.	Вывести информацию об общем времени работы всех бригад по месяцам
5.	Вывести топ-5 бригад, которые больше всего простаивают


### Предоставление результатов

Реализованные скрипты создания БД и заполнения, бекап БД закоммитить в GitHub-репозиторий. Ссылку на репозиторий предоставить преподавателям курса.

## Практическое задание №5 - Проектирование ИС

Для реализации потребуется:

*	Flexberry Designer

### Задание

Нарисовать UML-диаграммы для обозначенной предметной области. Состав диаграмм определяется самим слушателем курсов, но должен обеспечивать полноценное описание предметной области.

### Предоставление результатов

Результатом работы является выгруженная в формате CRP стадия из Flexberry Designer. Стадию (файл с расширением *.CRP) следует закоммитить в репозиторий на GitHub, ссылку предоставить преподавателям курса.

## Практическое задание №6 - Объектный дизайн и генерация приложений

Для реализации потребуется:

*	Flexberry Designer
*	Microsoft Visual Studio 2017
*	Postgres
*	Git for Windows

### Задание

Выполнить объектный дизайн и генерацию Ember-приложения для описанной предметной области. В качестве основы использовать реализованные ранее UML-модели. Генерация приложения и БД должна быть выполнена средствами Flexberry Designer приложение должно соответствовать требованиям и быть полностью работоспособным. Представления должны быть качественно настроены, подписи к классам и атрибутам на формах должны быть адекватными. Перечень форм и атрибутивный состав должны соответствовать предметной области и покрывать все требуемые бизнес-функции.

### Предоставление результатов

Сгенерированное приложение и скрипты создания БД следует выложить в репозиторий на GitHub. Предоставить преподавателям ссылку на репозиторий.

## Практическое задание №7 - Разработка бизнес-логики приложений

Для реализации потребуется:

* Flexberry Designer
* Microsoft Visual Studio 2017
* Postgres
* Git for Windows

### Задание

В сгенерированном при помощи Flexberry Designer приложении требуется реализовать следующую бизнес-логику.

1.	Реализовать бизнес-сервер, который будет контролировать, что бригада не получает больше одного сменного задания за смену. Должно быть сгенерировано событие, которое свидетельствует о недопустимости события.
2.	Реализовать бизнес-сервер, который будет запрещать удаление смен с со сменными заданиями, по которым уже были проведены работы.
3.	Реализовать бизнес-сервер, который будет контролировать указали ли все фактические значения о выполнении работ в сменном задании и генерирует событие-исключение в противном случае
4.	Добавить не хранимое поле в класс Строка Сменного задания, которое будет отражать полную информацию о нём: дату, бригаду, адрес
5.	Добавить не хранимое поле Состояние заявки, которое будет показывать проведены ли работы по устранению аварии.

### Предоставление результатов

Доработанная бизнес-логика должна быть включена в разрабатываемое приложение и закоммичена в соответствующий репозиторий. Ссылка на репозиторий предоставляется для проверки преподавателям курса.

## Практическое задание №8 - Разработка UI-логики приложения

Для реализации потребуется:

*	Microsoft Visual Studio 2017
*	Postgres
*	Редактор кода для клиентской разработки: Visual Studio Code
*	Git for Windows

### Задание

Привязать реализованные ранее EmberJS дополнительные формы и компоненты к данным из БД.  
Перенести в сгенерированное приложение и реализовать интеграцию формы из задания №3 с бизнес-логикой приложения. 
На форме для элементов управления с выбором - данные должны браться из БД (через ORM и Lookup). Заполнение данных также должно работать с сохранением в БД. 
Требуется настроить красивый внешний вид для всех форм приложения. Улучшить визуальную тему оформления. Реализовать ярлыки на рабочем столе приложения для быстрого доступа к часто используемым функциям.  
Реализовать дополнительные формы, которые будут выводить результаты выполнения запросов из задания по БД.

### Предоставление результатов

Доработанная UI-логика должна быть включена в разрабатываемое приложение и закоммичена в соответствующий репозиторий. Ссылка на репозиторий предоставляется для проверки преподавателям курса.

## Практическое задание №9 - Функциональные подсистемы Flexberry

Для реализации потребуется:

*	Flexberry Designer
*	Microsoft Visual Studio 2017
*	Редактор кода для клиентской разработки: Visual Studio Code
*	Postgres
*	Git for Windows

### Задание

Для реализованного приложения настроить подсистему полномочий. Сотрудники и карты должны заводиться администратором приложения. Авторизация на основе форм. Создать иерархию ролей, добавить операции на просмотр сведений и выдать права только администраторам. Настроить несколько ролей и назначить эти роли пользователям.  
Настроить подсистему аудита. В разрабатываемом приложении все изменения объектов данных должно фиксироваться в подсистеме аудита. В навигационное меню следует добавить формы аудита, которые должны показываться только администраторам.

### Предоставление результатов

Доработанное приложение должно быть закоммичено в соответствующий репозиторий. Дополнительно в репозиторий должны быть добавлены SQL-скрипты, которые нужно выполнить для функционирования приложения с подсистемой полномочий и аудита. Ссылка на репозиторий предоставляется для проверки преподавателям курса.