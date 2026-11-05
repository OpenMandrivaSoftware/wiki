---
title: Документация по созданию страниц выпусков
description: 
published: true
date: 2021-09-26T21:47:46.114Z
tags: документация, wiki
editor: markdown
dateCreated: 2020-03-07T18:55:42.072Z
---

# Документация по созданию страниц выпусков

Для каждого нового выпуска необходимо создать:

## Финальный выпуск (GA)

### Главная страница «Обзор»

Шаблон пути:
`/releases/omlxNN`
Пример: /releases/omlx42

### Вложенные страницы
#### 'Что Нового?'
Шаблон пути:
`/releases/omlxNN/`
Пример: /releases/omlx42/new

#### 'Примечания'
Шаблон пути:
`/releases/omlxNN/`
Пример: /releases/omlx42/notes

#### 'Известные проблемы и ошибки'
Шаблон пути:
`/releases/omlxNN/errata`
Пример: /releases/omlx42/errata

## Предварительные выпуски (Alpha, Beta, RC)

### Вложенные страницы
Шаблон пути:
`/releases/omlxNN/alpha`
`/releases/omlxNN/beta`
`/releases/omlxNN/rc`

`/releases/omlxNN/alpha/notes`
`/releases/omlxNN/beta/notes`
`/releases/omlxNN/rc/notes`

`/releases/omlxNN/alpha/errata`
`/releases/omlxNN/beta/errata`
`/releases/omlxNN/rc/errata`

Пример: /releases/omlx42/alpha
Пример: /releases/omlx42/beta
Пример: /releases/omlx42/rc

Пример: /releases/omlx42/alpha/notes
Пример: /releases/omlx42/beta/notes
Пример: /releases/omlx42/rc/notes

Пример: /releases/omlx42/alpha/errata
Пример: /releases/omlx42/beta/errata
Пример: /releases/omlx42/rc/errata

## Дополнение — пути
Пути должны содержать только строчные буквы. Для разделения слов используйте дефисы.
Знаки препинания не допускаются, за исключением дефисов и/или символов подчёркивания.

Пути не могут содержать следующие символы:
-Пробелы (вместо них используйте дефисы)
-Точки (зарезервированы для расширений файлов)
-Небезопасные символы URL (например, знаки препинания, кавычки, математические символы и т. д.)

Поскольку нам часто приходится указывать номера версий выпусков (4.0, 4.1, 4.2 и т. д.), при создании новых страниц просто убирайте точку из номера версии в пути, используя `40`, `41`, `42` и т. д.

