---
title: Как установить аватар пользователя в OMLx
description: 
published: true
date: 2021-09-26T21:36:21.553Z
tags: documentation, howto, user-guide
editor: markdown
dateCreated: 2020-03-09T18:24:08.289Z
---

# Как установить аватар пользователя в OMLx

### Сначала убедитесь, что в вашей системе установлен пакет `om-user-manager`:

```
$ rpm -q om-user-manager
om-user-manager-0.0.1-1.x86_64
```

Если команда не выводит никаких результатов в консоли, выполните:
```
$ sudo dnf --refresh install om-user-manager
```
![om-user-manager-01.jpg](/images/om-user-manager-01.jpg)

### Откройте «Параметры системы».

![om-user-manager-02.jpg](/images/om-user-manager-02.jpg)

### Сведения об учётной записи > Учётная запись пользователя

![om-user-manager-03.jpg](/images/om-user-manager-03.jpg)

### Нажмите на своё имя пользователя.

![om-user-manager-04.jpg](/images/om-user-manager-04.jpg)

### Затем нажмите на изображение пользователя по умолчанию.

![om-user-manager-05.jpg](/images/om-user-manager-05.jpg)

### Откроется диалоговое окно, в котором можно выбрать аватар.

![om-user-manager-06.jpg](/images/om-user-manager-06.jpg)

### Увеличьте размер значков, чтобы было удобнее просматривать доступные изображения.

![om-user-manager-07.jpg](/images/om-user-manager-07.jpg)

### Выберите понравившееся изображение.

![om-user-manager-08.jpg](/images/om-user-manager-08.jpg)

![om-user-manager-09.jpg](/images/om-user-manager-09.jpg)

### Применить

> Перед выходом потребуется ввести пароль root.
{.is-warning}


Готово

![om-user-manager-10.jpg](/images/om-user-manager-10.jpg)

![om-user-manager-11.jpg](/images/om-user-manager-11.jpg)

![om-user-manager-12.jpg](/images/om-user-manager-12.jpg)

–
### Возможно, вы захотите использовать собственное изображение в качестве аватара.
Для этого сначала поместите его в соответствующий каталог.

![om-user-manager-13.jpg](/images/om-user-manager-13.jpg)

### Откройте терминал в каталоге, содержащем нужное изображение.
И скопируйте его в `/usr/share/mdk/faces/`.

![om-user-manager-14.jpg](/images/om-user-manager-14.jpg)

![om-user-manager-15.jpg](/images/om-user-manager-15.jpg)

### Затем выполните те же действия, что и ранее:
Параметры системы > Сведения об учётной записи > Учётная запись пользователя

### Выберите свой новый аватар.

![om-user-manager-16.jpg](/images/om-user-manager-16.jpg)

Готово!

![om-user-manager-17.jpg](/images/om-user-manager-17.jpg)


