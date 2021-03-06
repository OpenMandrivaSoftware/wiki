---
title: OpenMandriva QA Издања
description: 
published: true
date: 2020-04-10T19:38:09.580Z
tags: 
---

# OpenMandriva QA Издања
> 
> **ПРОЦЕС ИЗДАЊА**
{.is-info}


## Инсталација ISO-а
#### Инсталација
Дистрибуција треба да се покрене са DVD ISO
Дистрибуција би требала да се покрене са основног меморијског флеша креираног помоћу команде
`dd if=”openmandriva iso” of=”dev/sd*” bs=4M`

Графичка и текстуална инсталација би требало да фунцкионише како је дефинисано.

Инсталациони процес мора радити и са другим језицима, нпр. без недостајућих превода.
Алтернативни распореди тастатуре морају радити.

#### Графичка инсталација
Графичка инсталација би требала да се прикаже у најоптималнијој резолуцији и броју боја које су доступни на систему а минимална резолуција од 1024 x 768 би требало да је подржана.

#### Администрација и Дизајн
Име издања би требало да буде текуће.
Уговор о лиценци би требало да буде приказан и исправан у свом садржају  (sign off docs reqd)
Напомене о издању би требало да буду оне за текуће издање и тако би и требало да буде означено. (sign off docs reqd)
Цео дизајн треба да буде онај који је одобрен у текућем издању. (sign off docs reqd)

#### Општа својства
Ниједна радња инсталације која захтева интервенцију корисника не би требало да се појави изван екрана за изабрану резолуцију (ОК тастери; APPLY тастери итд.).
Када је то могуће, корисник би требао бити у могућности да се врати на претходни корак у поступку инсталације. Ако то није могуће, корисника треба упозорити да не постоји реверзија или могућност ревизије из следећег корака (нпр. Форматирање партиције).

#### Менаџер за покретање
Mенаџер за покретање мора радити са другим инсталираним ОС-овима
Менаџер за покретање се мора исправно ажурирати у случају инсталације алтернативног кернела.

#### Хардвер
Издање се мора инсталирати на назначене хардверске платформе.

#### Мрежа
И жична и бежична конфигурација треба да буде достпуна уз минималну интеракцију корисника

#### Репозиторијуми
Уколико је мрежа доступна инсталациони процес би требао успешно да их дода у менаџер пакета

#### Графички сервер
Аутоматско подешавање Графичког сервера би требало да ради тамо где драјвери нису функционални за инсталирану графичку картицу Графички сервер би требао да обезбеди VESA драјвере као резервну опцију.

#### Менаџер прозора
Изабрани менаџер прозора би требало да се инсталира без грешака а ако не успе онда алтернативни основни менаџер прозора би требало да буде понуђен. Аутоматско покретање менаџера прозора би требало да буде понуђено при инсталацији.

#### Штампање
cups сервер би требало да буде инсталиран током процеса инсталације система.

#### Звук
Сервер звука би требало да се аутоматски инсталира што би требало да потврди за корисника звучни сигнал. Уколико нема звучне картице или уколико не успе инсталација звука одговарајућа порука треба бити приказана.

#### Подешавање корисника
Програм за инсталацију треба да затражи root лозинку.
Инсталер би требало да захтева креирање најање једног корисника.


## Покретање
#### Иницијално покретање
Приказ за иницијално покретање требало би исправно приказати на монитору, без померене слике.

Менаџер за покретање треба да прикаже одговарајуће опције за покретање система као минимум:

*Open-Mandriva Linux
Failsafe boot (boot to single user root terminal)
Rescue system
SuperGrub Iso?*

#### Графичко пријављивање
Графички менаџер за пријављивање The graphical login maби требало да прикаже све кориснике (без системских корисника).
Изабрани корисник би требало да буде онај који се последњи пријавио. У случају нове инсталације то би требало да буде први унос где су корисници сортирани по абецеди (a до z)
Курсор тастатуре би требао да буде активан у пољу за унос лозинке.
Уколико је мени за гашење/опште намене укључен све функције морају исправно функционисати.
Менаџер за пријављивање мора онемогућити приступ менаџеру прозора без лозинке.
Требало би да буде могуће покретање конзолног окружења за пријављивање из графичког менаџера за пријављивање.

#### Менаџер прозора
Након пријаве изабрани менаџер прозора би требало да се покрене без грешака
Видљиви индикатор за прикључене USB уређаје би требало да буде лако видиљив. (укључујући бежичне и жичне мрежне уређаје)
У случају USB дискова/cdrom/меморија они би требало да су нормално монтирани за следеће фајл системе  ext2, ext3, ext4, fat32, ntfs3g а било који системски драјвер за криптовани фајл систем мора бити укључен у оперативни систем. 

#### Сервери
Као минимум Samba, Cups, ssh, nfs и ftp сервери морају исправно функционисати

#### Одржавање софтвера
Систем за аутоматску надоградњу мора исправно функционисати када је доступан интернет.

#### Подешавање
Open Mandriva drakconf систем мора бити потпуно функционалан.

#### Основне графичке апликације
Следећа листа апликација које треба да се покрећу без грешака и да имају минималан број багова.

#### Систем
Плазма Десктоп
KDE конфигурациони алати
Сервер звука (мрежни звук би такође требало да буде функционалан)
Akonadi сервер
Индексирање фајлова
Конзола

#### Канцеларија
Libre Office
Okular

#### Интернет
Falkon
Firefox
Chromium
Chromium-pepper-flash
Browser Plugins
PDF support
Java
Kmail
Mozilla Thunderbird
Konversation IRC Client

#### Фајл Менаџер
Dolphin
(уграђени приступ мрежи такође мора радити)
Krusader

#### Едитор фајлова
Kwrite
Kate

#### Развој
Kdevelop
Eclipse

#### Графика
Gwenview
Krita
DigiKam

#### Звук и Видео
...

#### Алати
...

#### Алатке
...

#### CLI Основне Апликације

mc
vim
ed
vi
nano
emacs?
Bash
sh
binutils
man
less
netstat
bind
dhclient
M4
bison
grep
awk
sed
make
Autoconf
libtool
pkgconfig
scons
rpm
urpmi
perl
python


## Критеријум за одобрење издања
- Сви програми на листи горе морају бити функционални и бити у могућности да се отворе, раде, затворе и сачувају фајл где је потребно. Не сме бити битних сигурносних проблема.
- Не сме бити грешака које могу озбиљно да угрозе функционалност система бар што се тиче корисника за горе наведене пакете. Грешке у додатним и contib пакетима који у основи не утичу на рад система се могу толерисати. Грешке које се не могу толерисати је прекомерна употреба диска, велико трошење ресурса система, цурење меморије, закључавање менаџера за прозоре и било која форма замрзавања система. 
- Мора бити омогућено исталирање друге верзије кернела са OM репоа без проблема. Скрипта за инсталацију кернела мора исправно ажурирати менаџер за покретање и приказати доступност новог кернела на екрану за покретање система. Оргинални кернел се мора преименовати на начин које се даје до знања да је у питању оргинални подразумевани кернел. Симболички линкови који упућују на подразумевани кернел морају бити исправно ажурирани.
- Мора бити могуће коришћење dkms система за надоградњу драјвера доступних у подразумеваној дистрибуцији. Ово би требало да укључи власничке графичке драјвере;
- Мора бити омогућен приступ мрежној вези и где је могуће приступ интернету. Ово би требало да буде могуће и за жичне и бежичне конекције;
- Ниједан често коришћени сервер не сме остати не покренут;
- Систем мора бити у могућности да штампа из свих апликација које омогућавају овај сервис;
- Систем пакета и репоа мора бити у функцији укључујући OpenMandriva аутоматску надоградњу.
- ISO-ои поднешени за издање морају бити исправно именовани и датирани.


## Листа за проверу
QA Тим и тестери се охрабрују да креирају детаљне листе за проверу за ISO-е са листама откривених грешака.<br />
Требало би да садржи уобичајене случајеве коришћења попут:

1. Да ли се iso нарезује на usb меморију
1. Да ли се појављује grub/boot екран
1. Да ли раде опције на grub/boot екрану
1. Да ли се ISO покреће у  multi-user.target
1. Да ли се ISO покреће у graphical.target
1. Да ли ради аутоматско логовање за live кориснике
1. Да ли се подразумевани графички десктоп приказује након аутоматског пријављивања
1. Да ли је подразумевани графички десктоп употребљив (основе, пупут менија, фајл менаџера, веб претраживача)
1. Да ли се ISO покреће у VirtualBox-у
1. Да ли се ISO инсталира у VirtualBox-у

