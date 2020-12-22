---
title: Стилски водич за вики
description: 
published: true
date: 2020-05-04T22:36:55.975Z
tags: документација, вики
---

# Стилски водич за вики

## Општe смернице
Следећа секција даје смернице за коришћење синтаксе и састав реченица.
Користите ове смернице да би обезбедили да тон ваших докумената у складу са оним што је у другој OpenMandriva документацији.

### Састав

#### Глас
Инструкције и правила користе * активни глас *, представљајући поверење читаоцу а да не звучи захтевно.
Активни глас даје јасан правац. То показује читаоцу шта да ради и даје очекиване резултате.
Активни глас оставља читаоцу утисак да аутор стоји иза написаног дела. 

#### Избегавај Пасивни глас осим уколико није неопходан
* Пасивни глас * је граматички потпуно исправан, али представља препреку читаочевом разумевању.
Пасивни глас врти се око конвенционалне реченице. Она помера глагол и усмерава предмет према првој половини реченице, а главни тему поставља у другу половину реченице. Често једноставно реструктурирање реченице чини је активном.
Дуге пасивне реченице често траже више читања пре него што читалац схвати потпуно значење.

`АКТИВАН:  Изаберите јаку лозинку да би унапредили личну сигурност.`

`ПАСИВАН: Лична сигурност се унапређује избором јаке лозинке.`

#### Контекст

Избегавајте писање ван контекста.
Пажљиво се придржавајте теме документа, поглавља, одељка и става.
Користите референце, према потреби, структурирајући докуменат тако да се сваки нови део надограђује на претходни.
Избегавајте да читалац прескаче унапред да би тренутне делове ставио у контекст.
Наведите везу до сродне документације ако ће је читаоцу можда требати ради појашњења.

#### Наглашавање

Наглашавање је најефикасније када се употребљава умерено.
Користите методе нагласка као што су подебљање, подвлачење или коси текст да бисте скренули пажњу на нови појам.
Употребите напомене да бисте нагласили битан материјал.
Још један прихватљив начин да се истакне тачка је различито формирање реченица или избор речи.
Најбољи писци документације планирају унапред нагласак, примјењујући га са пажњом у доследно са документом.

#### Прецизност и Тачност

Прецизност и тачност праве или кваре било који документ.
Овај аксиом се подједнако односи на техничку и књижевну тачност.
Изаберите речи након што размотрите што је више могуће случајева. На пример, „иди на“ није тако прецизно као „кликни“, али „кликни“ можда није тачно за све интеракције интерфејса. Израз "изабери" је тачан у сваком случају употребе и довољно прецизан.
Не будите преокупирани покушајем да покријете све могуће случајеве употребе. Покривање ретких споредних случајева продужава документ без разлога, а читалац губи фокус.

#### Временско стање

Временско стање је оно време у коме се дешава радња.
Постоје три главна времена: прошлост, садашњост и будућност. Изаберите одговарајуће временско стање за документ и примените га на документ.
За техничку документацију, треба користити садашње стање када год је то могуће.
Одражавање истог стања за сваку тврдњу у документу је од виталног значаја за јасноћу.
Задржите исто стање за све редне задатке у поступку.

## Употреба

### Скраћивање

Избегавајте скраћивање, комбинацију две речи са апострофом који замењује једно или више слова.
Скраћивања смањују читљивост докумената и отежавају превођење.
Друге културе и језици различито тумаче скраћивања, а ова конфузија у сукобу је са циљевима Пројекта документације за OpenMandriva.

### Заменице

Заменице су речи који језик користи да би замени одређени именични израз.
Добри писци морају погодити баланс између преише понављање именичних фраза, и коришћење заменица које замењују именице. Опште правило за очување јасноће је да никада не треба понављати замену именице са заменицом у две узастопне реченице.
Читаоци техничке документације требају стално подсећање на праву тему о којој аутор пише. Претерано коришћење заменица може узроковати да читаоци погађају тему на коју реченица упућује.
Ове претпоставке умањују ефикасност документа.

Избегавајте личне заменице у документацији, укључујући следеће:
* Субјектне личне заменице ("Ја," "он," "она," "то," "ми,")
* Објектне личне заменице ("мени," "њој," "њему," "нама")
* Присвојне личне заменице ("моје," "њено," "његово," "наше")

Такође избегавајте:
* Друге личне заменице попут "себи" or "собом"
* Друге личне заменице попут "он сам" или "(ти) уради то сам"
* Одуприте се претераном коришћењу "ти", "твој", и "један/нечији"

Повремено ситуације захтевају другу личну заменицу "ви" и њене пратеће форме због јасноће.
Одржавање активног гласа је најважније преко избегавање других личних заменица. "Ви" и "ваше" су одговарајуће речи које означавају радњу или поседовање са стране читаоца.
Неодређене заменице попут "ово" или "оно" без члана испред чине читаоцу тешко да следи смисао аутора.
Фаворизујте писање прецизне именичог изразакад год је то могуће уместо нејасних речи  попут „ово“, „ови“, „оно“ и „то“.

`НЕИСПРАВНО: Уредите ваш yum конфигурационе фајлове да би користити географски најближе мироре. Ово вам омогућава да брже надоградите свој систем.`

`ИСПРАВНО:  Уредите yum конфигурационе фајлове да би користили географски најближе мироре за бржу надградњу система.`

Када елиминишете неодређене заменице, гломазна дуга реченица може бити резултат придруживања превише чланова.
Употребите неодређене заменице да бисте раздвојили дуге реченице ради побољшања јасноћe, али увек осигурајте одговарајући претходни члан.

`НЕИСПРАВНО: Останите у току са препорученим надоградњама вашег оперативног система да бисте побољшали функционалност
апликација, уклоните сигурносне ризике и аутоматски решите проблеме са перформансама које су решени на основу извештаја о грешкама.`

`ИСПРАВНО: Останите у току са препорученим надоградњама вашег оперативног систем. Ове надоградње унапређују функционалност
апликација, уклања сигурносне ризике, и аутоматски режава проблеме са перформансама који су речени на основу извештаја о грешкама.`

### Формирање реченице

Задржите реченице што је краћим могуће.
Избацивање непотребних речи је од пресудног значаја за ојачање значења.
Постоји одређени број уобичајених замки у које упадају креатори техничке документације што доводи до дугачких реченица.

#### Индиректан говор

Идиректан говор се односи на употребу "то" као прилога тврдњи, чињеници, или осећају у реченици без употребе наводника.
У уобичајеном писању, оно слаби изјаву чињенице.
Писци документације могу унапредити утица реченице уклањањем "то" и "које".

`НЕИСПРАВНО: Mandriva је оперативни систем отвореног кода који је покретач за многе друге пројекте отвореног кода.`

`ИСПРАВНО: Mandriva је покретачки оперативни систем отвореног кода за многе друге пројекте отвореног кода.`

#### Остале непотребне комбинације речи

Избегавајте непотребу реч "тада" које прати тврдња "уколико".
Када реченице почињу са тврдњом "уколико",  коју прати зарез и цела реченица са комплетном тврдњом.

`НЕИСПРАВНО: уколико клијент ел.поште не шаље или не прима поруке, тада кликните на Мени Фајл и проверите да ли је "Рад без мреже" деселектован.`

`ИСПРАВНО: Уколико клијент ел.поште неће да шаље и прима поруке, проверите у менију Фајл и проверите да ли је "Рад без мреже" деселектован.`

Многе речи које користимо у свакодневној конверзацији умањују утицај штампаних материјала зато што "остављају излаз напоље".
Ово су речи које стоје испред глагола и именица ради умањења значаја реченице. Ово није преобина листа, али пажљиви писци документације ће умањити коришћење тих речи и других сличне природе. 

#### Избегавајте умањивање значаја са непотребним речима
Следеће ечи умањују значај склоп глагола или именице у реченици.
Друге речи такође могу упасти у ову категорију, али ова кратка листа има за циљ да помогне писцу документације да утврди речи ове природе и уклони их из свог писања: ** треба, може, може бити, могуће, можда, неки, многи, већина, бројни, неколико, понешто, донекле, шта год, по могућности, може повремено и често**.

#### Промене реченице
За највећи значај, задржите прву и последњу реченицу у параграфу што је краћом могуће.
Мењањем дужине реченице у параграфу и кроз цео документ држи пажњу читаоца. Кратка и једноставна чињеница се лако прихвата и користи за анализу теме следеће реченице. Не постији ништа погрешно у коришћењу дуже реченице ради објашњења сложене идеје или концепта. Покушајте да користите једноставне реченице на крају сваког параграфа да би читаоу дали могућност да обухвати све битне информације.
Кратка последња реченица остаје са читаоцем за следећу секцију. 

#### Велика слова

У реченицама, велико слово треба ставити у прво реч-
Не почињите реченице са командом, пакетом или опционим именом.

`НЕИСПРАВНО: <code>smolt</code> омогућава профилисање хардвера.`

`ИСПРАВНО: Пакет <code>smolt</code> омогућава профилисање хардвера.`

#### Знакови интерпукције

Интерпукција је најбитнија компонента за разумевање написаног.
Лоше постављен, зарез, тачка зарез или неправилно коришћење знакова интерпукције може потпуно променити значење реченице. Интерпукцијске ознаке су затварачи у пишчевом алату. Читаоци су навикнути на уобичајене ознаке, попут зареза или три тачке, а мање познате ознаке лако скрећу пажњу читаоцима.
Сложене интерпукцијске ознаке нису универзалне, и отежавају напоре за превођење OpenMandriva документације. 

Смањите употребу следећих интерпукцијских ознака у документацији:
* Заграде или црте
Ради замене, промените редослед реченице, или је раздвојите у две целине
* Тачка зарез
Она је добра само уколико су две мисли повезане, морају бити сједињене ради јасноће, а уклањају потребу за спајањем.
* Двотачка
Уколико постоје више од три појма, треба користити листу ради лакшег разумевања
* три тачке
Немојте их користити због стилског наглашавања... само ради обавештавања о непрекидном настављању садржаја у примеру
* Наводници
У техничком писању они су прихватљиви само за коришћење последње решење за навођење "упозорења", не за наглашавање
* Знак &
Реч "и" треба написати, а овај знак користити само уколико је део рачунарске команде 
* Косе црте
Немојте користити косе црте за скраћивање попут "он или она" коришћењем он/она уместо речи "и", "или" или "ни". Косе црте се често користе у путањама фајлова и њихово коришћење у друге сврхе може направити конфузију

## Друга питања везана за писање

Сваки писац наиђе на препреке у писању. Постаје тешко адекватно формулисати нешто или речи једноставно не звуче исправно.
Због тога је Опенмандрива пројекат тимски напор. Позовите колеге писце документације на листи за слање или цхат соби за помоћ у вези са формулацијама и проблемима у формату.
Још један трик који професионални писци користе свакодневно је време далеко од пројекта. Одмакните се од документа. Повратак на проблематично место свјежим очима често је све што је потребно за превазилажење препрека писања.

Општи циљ документационог пројекта OpenMandriva је пружање помоћи корисницима ОpenMandriva на лако разумљивом језику.
Не морате писати да бисте импресионирали професора енглеског језика или показали своју стручност у вези са неком темом. Кратке реченице, честе дефиниције нових и непознатих термина, као и референтне везе, су помоћ која наша публика највише цени.
Пишите имајући на уму циљану публику, и то ће бити ваши доприноси у документацији са највећим бројем посета корисника којима је потребан одговор.



*Заслуге:
Преузето iz* [Стилски водич Fedora пројекта](http://Fedoraproject.org/wiki/Docs_Project_Style_Guide_-_General_Guidelines)

----
## Посебни стилски водич OpenMandriva викија

Прочитајте и [Посебни стилски водич OpenMandriva викија](/en/doc/omawiki-style-guide)




