# Ukrainian Security Filter

**Ukrainian Security Filter (Український безпековий фільтр)** — це фільтр шкідливих веб-ресурсів (фішинг, онлайн-шахрайство, шкідливе програмне забезпечення тощо), що орієнтовані на громадян України.

Щодня зловмисники активують нові шкідливі веб-ресурси за допомогою яких обманом виманюють в українців доступ до облікових записів банківських онлайн систем, реквізити платіжних карток, конфіденційну інформацію та гроші. Щодня реєструються десятки нових доменних імен, які згодом будуть використані у нових фішингових кампаніях та онлайн-шахрайстві. За таких обставин блокування шкідливих веб-ресурсів лише за назвою доменних імен не є ефективним. Саме тому Український безпековий фільтр містить три групи правил фільтрації:
1. `Стандартні правила` (domain-based blocklist) — це список блокувань за назвою доменного ім'я
2. `Індивідуальні правила` (page-specific filtering rules) дозволяють блокувати сторінки у соціальних мережах, посилання на групи або чат-боти у месенджерах тощо, тобто цільові веб-адреси (URL-адреси) ресурсів які є легітимними, проте, які використовуються зловмисниками
3. `Універсальні правила` (pattern-based filtering rules) дозволяють блокувати шкідливі веб-ресурси, навіть, якщо інформація про доменні імена таких ресурсів відсутня у фільтрі, адже блокування відбувається на основі [паттернів](https://mastodon.online/@braveinnovators/111364189029417720)

## Формати

### Adblock-style syntax

Цей формат фільтра сумісний з усіма браузерами, розширеннями та іншим програмним забезпеченням, що підтримує синтаксис AdBlock.

```
https://www.awwwwesome.org/ukrainian-security-filter.txt
```

### Domain-based blocklist

Усі веб-адреси (URL-адреси) відображені у такому форматі: `example.com`

```
https://raw.githubusercontent.com/braveinnovators/ukrainian-security-filter/main/domains/ukrainian-security-filter-domains.txt
```

### Hosts-based blocklist

Усі веб-адреси (URL-адреси) відображені у такому форматі: `0.0.0.0 example.com`

```
https://raw.githubusercontent.com/braveinnovators/ukrainian-security-filter/main/hosts/ukrainian-security-filter-hosts.txt
```

### dnsmasq

Усі веб-адреси (URL-адреси) відображені у такому форматі: `address=/example.com/`

```
https://raw.githubusercontent.com/braveinnovators/ukrainian-security-filter/main/dnsmasq/ukrainian-security-filter-dnsmasq.txt
```

## Сумісність з браузерами та розширеннями

Нижче наведений перелік браузерів (з вбудованими модулями фільтрації контенту) та сторонніх розширень з якими гарантована сумісність правил, які містяться у фільтрі:

* [Brave](https://brave.com/)
* [Opera](https://www.opera.com/)
* [Vivaldi](https://vivaldi.com/)
* [uBlock Origin](https://ublockorigin.com/)
* [Adblock Plus](https://adblockplus.org/)
* [AdBlock](https://getadblock.com/)

## Як імпортувати фільтр

#### Браузери з вбудованими модулями фільтрації контенту

### Brave

<details>
<summary>Операційні системи Windows, macOS та Linux</summary>

1. У меню Settings відкрити вкладку Shields й змінити налаштування Trackers & ads blocking на Aggressive
2. У вкладці Shields відкрити розділ Content filtering і у розділі Add custom filter lists у поле вводу вставити скопійовану адресу фільтра:

```
https://www.awwwwesome.org/ukrainian-security-filter.txt
```
</details>

<details>
<summary>Операційні системи Android та iOS</summary>

1. У меню Settings відкрити розділ меню Brave Shields & privacy й змінити налаштування Block trackers & ads на Aggressive
2. Вийти з меню, відкрити нову вкладку та ввести наступну адресу: brave://adblock
3. Перейти до розділу Subscribe to filter list, натиснути на кнопку Add filter list via URL і у поле вводу вставити скопійовану адресу фільтра, зберігши зміни шляхом натискання на кнопку Submit:

```
https://www.awwwwesome.org/ukrainian-security-filter.txt
```

Додаткова інструкція доступна за адресою: https://brave.com/privacy-updates/10-custom-filter-lists/
</details>

#### Розширення (extensions)

### uBlock Origin

<details>
<summary>Операційні системи Windows, macOS та Linux</summary>

1. Відкрити меню Preferences розширення uBlock Origin, клацнути мишею на вкладку Filter lists і прокрутити до розділу Custom
2. Клацнути мишею на Import... і у поле вводу вставити скопійовану адресу фільтра, зберігши зміни:

```
https://www.awwwwesome.org/ukrainian-security-filter.txt
```

Додаткова інструкція доступна за адресою: [https://github.com/gorhill/uBlock/wiki/Filter-lists-from-around-the-web](https://github.com/gorhill/uBlock/wiki/Filter-lists-from-around-the-web)
</details>

### Adblock Plus

<details>
<summary>Операційні системи Windows, macOS та Linux</summary>

1. Відкрити меню налаштування розширення Adblock Plus, клацнути мишею на вкладку Advanced і прокрутити до розділу My filter list
2. У поле вводу вставити скопійовану адресу фільтра, зберігши зміни:

```
https://www.awwwwesome.org/ukrainian-security-filter.txt
```

Додаткова інструкція доступна за адресою: [https://help.adblockplus.org/hc/en-us/articles/360062859913-Add-a-custom-filter](https://help.adblockplus.org/hc/en-us/articles/360062859913-Add-a-custom-filter)
</details>

## Особливості

Кожен веб-ресурс перед додаванням до фільтра проходить перевірку на дійсність реєстрації доменного ім'я (така перевірка відбувається на постійній основі, що, у підсумку, виключає наявність у фільтрі ресурсів з анульованою реєстрацією).

Неактивність веб-ресурсу за зазначеною у фільтрі адресою не є підставою для його виключення з фільтра, оскільки зловмисник може у будь-який момент відновити роботу сервера й тому ми орієнтуємося саме на дійсність реєстрації доменного ім'я, а не на технічну доступність безпосередньо веб-ресурсу.

Веб-ресурси, які виключаються з фільтра через анулювання або закінчення дії реєстрації доменного ім'я, вносяться до архівного списку, який також регулярно перевіряється на предмет повторної реєстрації доменного ім'я та активації зловмисних веб-ресурсів (у такому випадку ці ресурси знову додаються до фільтра).

## Джерела інформації

* Власна моніторингова команда
* Урядова команда реагування на комп'ютерні надзвичайні події України (CERT-UA)
* Комісія з регулювання азартних ігор та лотерей (КРАІЛ)
* BlackList EMA

## Партнери проекту

* [DNSlytics](https://dnslytics.com)

## Ліцензія

На Ukrainian Security Filter (Український безпековий фільтр) поширюються умови ліцензії [GNU General Public License v3.0](https://github.com/braveinnovators/ukrainian-security-filter/blob/main/LICENSE)
