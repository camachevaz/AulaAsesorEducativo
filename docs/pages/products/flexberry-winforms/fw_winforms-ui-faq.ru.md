---
title: WinForms UI FAQ
sidebar: flexberry-winforms_sidebar
keywords: Flexberry Winforms
summary: Часто задаваемые вопросы по Flexberry Winforms
toc: true
permalink: ru/fw_winforms-ui-faq.html
lang: ru
---

В процессе разработки приложения могут возникать вопросы, ответы на которые можно найти ниже.

## Вопрос 1

Например, есть объекты `Корпус` и `Аудитория`. `Корпус` является мастером для `Аудитории`. Требуется сделать форму для редактирования этих объектов примерно в таком формате: вверху [ObjectListView](fw_objectlistview.html) с `Корпусами`, внизу [GroupEdit](fw_group-edit.html) с аудиториями корпуса. При выборе в OLV корпуса, в GE подгружаются соответствующие аудитории. Аудитории в GE хочется редактировать, а не вызывать отдельно форму `АудиторияE`. Как лучше это сделать?

Создана дополнительная listform для представления `КорпусL`. Для нее сгенерировалась соответствующая .Net форма, куда требуется добавить `GroupEdit`. Но не ясно, как указать объект данных в нем. Открывается пустая форма с выбором пакетов.

Как решить данную проблему?

### Ответ

Для решения этой задачи надо зайти с другой стороны: нужна форма редактирования корпуса с детейлами (аудитории должны быть детейлами чтобы можно их было редактировать в GroupEdit). Затем нужно переключать мастера так как описано в статье [Редактирование объектов данных на формах](fw_edit-objects-on-forms.html).

В этом случае блокировки будут адекватно отрабатывать. Но, если аудитории отдельно тоже могут редактироваться (если существует отдельная форма редактирования для них), то `GroupEdit` должен быть настроен на работу с [блокированием редактируемых объектов](fw_lock-rows-in-groupedit.html).