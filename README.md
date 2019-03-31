# Linux
[Контест: *Задания по Linux*](https://school9.perm.ru/gate/tester/?)
## О системе
---
**Linux** - ядро ОС, разработка начата финским студентом Линусом Торвальдсом 
*  Ядро - наиболее низкий уровень абстракции для доступа приложений к ресурсам системы, необходимым для их работы.
*  Пространства ядра(*Kernel Space*) - адресное пространство, которое резервируется для работы ядра операционной системы
 
**GNU/Linux** - операционные системы, основанные на ядре Linux и системных библиотеках GNU (а часто и другом ПО)
* Пользовательское пространство(*User space*) — адресное пространство виртуальной памяти операционной системы, отводимое для пользовательских программ

Системы **GNU/Linux** и все их компоненты распростаняются по лицензии **GNU GPL**, а значит имеют открытый исходный код, который может быть отредактирован любым желающим

| Kernel space and user space | Ring 0 | Ring 1-3 |
|-|-|-|
|![Spaces](https://blog.codinghorror.com/content/images/uploads/2008/01/6a0120a85dcdae970b0120a86db3ea970b-pi.png) | Kernel space | User space |

## Дистрибутивы
---
Дистрибутив **GNU/Linux** — общее определение операционных систем, использующих ядро Linux, представляющий собой настроенную систему с предустановленным комплектом приложений. У каждого дистрибутива свои правила и свое сообщество

В настоящее время существует более шестисот дистрибутивов **GNU/Linux**; более половины из них поддерживаются в актуальном состоянии, что обеспечивается регулярным выпуском обновлений разработчиками дистрибутива

Современные диструбутивы берут начало от трех старейших: **Slackware**, **Debian**, **Red Hat**

*Андрей, админ школы 9:*
> Слава Редхату!!!1

##### [GNU/Linux Distributions Timeline](https://upload.wikimedia.org/wikipedia/commons/1/1b/Linux_Distribution_Timeline.svg)

## Применение
---
Благодаря возможностями трансформации и масштабирования **GNU/Linux** ее можно встретить во всех областях компьютерной техники

* Лидер на рынке серверов
* Лидер на рынке мобильных ОС (*ОС Android*)
* Лидер на рынке встраеваемых систем
* Главный элемент кластеров и моделей распределенных вычислений
* 100% суперкомпьютеров из ТОП-500 мира работают на linux
* Востребован наукоемкими специальностями благодаря высокой скорости вычислений
* 3 по популярности ОС для десктопа(после **Windows**, **Mac OS**)

![Применение](https://www.ibm.com/developerworks/ru/library/l-linuxuniversal/figure2.gif)

## Работа c cистемой
---
### Графический интерфейс
Внешний вид linux очень близок к популярным **Windows** или **Mac OS**, поэтому новым пользователям не придется долго привыкать к системе. С другой стороны, под linux существует множество графических оболочек на любой вкус, цвет и характеристики компьютера. Любую из них можно настроить до мелочей

[Примеры](https://www.reddit.com/r/unixporn/hot/)

### Терминалы и консоль

Куда более интересная часть системы. Взаимодействуя с компьютером через консоль можно сделать все то же, что и через графический интерфейс, и даже много больше

* Терминал - это устройство, при помощи которого человеки взаимодействуют с компьютером 
* Эмулятор терминала - это программа, которая выдаёт себя за терминал, но на деле им не является. Она может отличаться от настоящего терминала интерфейсом, архитектурой, функционалом, чем угодно. С эмуляторами терминалов можно взаимойдествовать из графического интерфейса
* Консолями сейчас называют обобщённо терминалы и их эмуляторы

Взаимодейсвтие с компьютером осуществляется посредством команд, которые имеют следующий вид: 
```
[название команды] <опции> [аргументы]
```
![cowsay](https://github.com/Vladius25/linuxcourse/blob/master/cowsay.png?raw=true)

| Название | cowsay|
| - | - |
| Опция | -e99 
|  Аргумент | "Hello, world" |

*На самом деле, команды - это программы, все так же с открытым исходным кодом, который можно редактировать*

### Файловая система. Права
Отдельно стоит упамянуть о файловой системе(ФС) и правах доступа. В отличие от **Windows** в **GNU/Linux** используется ФС **ext4**, более гибкая и функциональная. Одним из основных ее отличий является поддержка **прав доступа** к файлам и папкам

Права бывают трех типов:
 * Read(**r**) - чтение файлов или папок
 * Write(**w**) - запись в файл или папку
 * Execute(**x**) - запуск программ

Правами могут обладать:
* Владелец файла или папки
* Группа пользователей
* Все остальные, не входящие в первые 2 группы

Так выглядит полная информация о правах на файл в ФС **ext4**:
```
-rwx rw- r-- vladius wheel devyatka.cpp
```

Это значит, что права на файл *devyatka.cpp* распределены следующим образом:

|Роль|Права|Обозначение в примере|
|-|-|-|
|Владелец(*vladius*)|read/write/execute|rwx|
|Группа(*wheel*)|read/write|rw-|
|Остальные|read|r--|

# Список часто используемых команд с пояснением
---
Если хотите быстро понять, что делает команда, что означают ее опции и аргументы, зайдите на [explainshell.com](https://www.explainshell.com/). К сожалению, ресурс заблокирован в России
### man
---
* `man <команда>` - подробная информация о команде *<команда>*
### pwd
---
* `pwd` - текущая директория
### cd
---
* `cd <директория>` - сменить текущую директорию на <директория>
    * Директориями в **GNU/Linux** называются папки
    * `~` - домашняя директория пользователя
### ls
---
* `ls` - список файлов и папок в текущей директории
    * `ls -l` - подробный список(включает права, владельца, группу, размер и время редактирования)
    * `ls -a` - скрытые файлы и папки(которые начинаются с `.`)
    * `ls -la` - две опции вместе
    * `ls <дир>` - список файлов в директории *<дир>*
### cp
---
* `cp <файл1> <файл2>` - копировать *<файл1>* в *<файл2>*
    * `cp -r <дир1> <дир2>` - копировать директорию *<дир1>* в *<дир2>*
### mv
---
* `mv <1> <2>` - переместить файл или директорию <1> в <2>
### ping
---
* `ping <хост>` - проверить доступность <хост> в сети
    * Например, `ping school9.perm.ru`
    * Чтобы остановить нажмите **Ctrl-C**
### ssh
---
* `ssh <пользователь>@<хост>` - удаленно подключиться к компьютеру *<хост>* и зайти под пользователем *<пользователь>*
    * **SSH** -  сетевой протокол, позволяющий производить удалённое управление операционной системой
    * Когда вы подключитесь к *<хост>*, увидите ту же консоль
### scp
---
* `scp <файл> <пользователь>@<хост>:<дир>` - отправить файл *<файл>* по протоколу **SSH** на компьютер *<хост>* под пользователем *<пользователь>* в директорию *<дир>*
    * Например, `scp task.xml root@cab13c1.linux.sch9.lan:/home/vasyan/`
    * `scp -r <дир1> <пользователь>@<хост>:<дир2>` - то же самое для директории
### hostname
---
* `hostname` - имя компьютера

# Предложения и пожелания
---
Засылайте ваши PR [сюда](https://github.com/Vladius25/Linuxcourse)
