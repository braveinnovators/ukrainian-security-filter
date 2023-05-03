# Ukrainian Malicious URL Blocklist

Фільтр (список блокувань) фішингових сайтів, які обманом виманюють в українців доступ до облікових записів банківських онлайн систем, реквізити платіжних карток, конфіденційну інформацію та гроші. У фільтр додаються виключно шахрайські вебресурси, які орієнтовані саме на громадян України і які відсутні в інших наявних фільтрах.

Фільтр містить три групи правил фільтрації: стандартні правила, універсальні правила (pattern-based filtering rules) та індивідуальні правила (page-specific filtering rules). Універсальні правила дозволяють блокувати фішингові веб-ресурси, навіть, якщо інформація про доменні імена таких ресурсів відсутня у фільтрі. Індивідуальні правила дозволяють блокувати сторінки у соціальних мережах, посилання на групи або чат-боти у месенджерах тощо, тобто цільові веб-адреси (URL-адреси) ресурсів які є легітимними, проте, які використовуються зловмисниками.

## Формати

### Domain-based blocklist

До фільтра у форматі domain-based blocklist вносяться лише домени, що дає можливість блокувати доступ до ресурсу без жорсткої прив'язки до субдоменів та (або) шляху/параметрів URL (виключення: посилання на соціальні мережі, блоги та інші ресурси які є легітимними, проте, які використовуються зловмисниками).

Цей формат фільтра сумісний практично з усіма браузерами, розширеннями та іншим програмним забезпеченням, що підтримує синтаксис AdBlock.

Усі веб-адреси (URL-адреси) відображені у такому форматі: `||example.com^`

```
https://www.awwwwesome.org/url-blocklist/url-blocklist.txt
```

### Domain-based blocklist (без синтаксису AdBlock)

Усі веб-адреси (URL-адреси) відображені у такому форматі: `example.com`

```
https://github.com/braveinnovators/url-blocklist/raw/main/filters/url-blocklist-domains.txt
```

### Hosts-based blocklist

Усі веб-адреси (URL-адреси) відображені у такому форматі: `0.0.0.0 example.com`

```
https://github.com/braveinnovators/url-blocklist/raw/main/filters/url-blocklist-hosts.txt
```

### dnsmasq

Усі веб-адреси (URL-адреси) відображені у такому форматі: `address=/example.com/`

```
https://github.com/braveinnovators/url-blocklist/raw/main/filters/url-blocklist-dnsmasq.txt
```

## Сумісність з браузерами та розширеннями

Нижче наведений перелік браузерів та сторонніх розширень з якими гарантована сумісність правил, які містяться у фільтрі Ukrainian Malicious URL Blocklist.

#### Браузери (з власними модулями фільтрації контенту)
* Brave: [https://brave.com](https://brave.com/)
* Opera: [https://www.opera.com](https://www.opera.com/)
* Vivaldi: [https://vivaldi.com](https://vivaldi.com/)

#### Розширення
* uBlock Origin: [https://ublockorigin.com](https://ublockorigin.com/)
* Adblock Plus: [https://adblockplus.org/features](https://adblockplus.org/features)
* AdBlock: [https://getadblock.com](https://getadblock.com/)

## Як додати фільтр

### Brave

- У меню Settings відкрити вкладку Shields й змінити налаштування Trackers & ads blocking на Aggressive
- У вкладці Shields відкрити розділ Content filtering і у розділі Add custom filter lists у поле вводу вставити скопійовану адресу фільтра:

```
https://www.awwwwesome.org/url-blocklist/url-blocklist.txt
```

Додаткова інформація: [https://github.com/braveinnovators/url-blocklist/wiki/Brave](https://github.com/braveinnovators/url-blocklist/wiki/Brave)

### uBlock Origin

- Відкрити меню Preferences розширення uBlock Origin, клацнути мишею на вкладку Filter lists і прокрутити до розділу Custom
- Клацнути мишею на Import... і у поле вводу вставити скопійовану адресу фільтра, зберігши зміни:

```
https://www.awwwwesome.org/url-blocklist/url-blocklist.txt
```

Додаткова інформація: [https://github.com/braveinnovators/url-blocklist/wiki/uBlock-Origin](https://github.com/braveinnovators/url-blocklist/wiki/uBlock-Origin)

### Adblock Plus

- Відкрити меню налаштування розширення Adblock Plus, клацнути мишею на вкладку Advanced і прокрутити до розділу My filter list
- У поле вводу вставити скопійовану адресу фільтра, зберігши зміни:

```
https://www.awwwwesome.org/url-blocklist/url-blocklist.txt
```

Додаткова інформація: [https://github.com/braveinnovators/url-blocklist/wiki/Adblock-Plus](https://github.com/braveinnovators/url-blocklist/wiki/Adblock-Plus)

## Особливості

Кожен веб-ресурс перед додаванням до фільтра проходить перевірку на дійсність реєстрації доменного ім'я (така перевірка відбувається на постійній основі, що, у підсумку, виключає наявність у фільтрі ресурсів з анульованою реєстрацією).

Неактивність веб-ресурсу за зазначеною у фільтрі адресою не є підставою для його виключення з фільтра, оскільки зловмисник може у будь-який момент відновити роботу сервера й тому ми орієнтуємося саме на дійсність реєстрації доменного ім'я, а не на технічну доступність безпосередньо веб-ресурсу.

Веб-ресурси, які виключаються з фільтра через анулювання або закінчення дії реєстрації доменного ім'я, вносяться до архівного списку, який також регулярно перевіряється на предмет повторної реєстрації доменного ім'я та активації зловмисних веб-ресурсів (у такому випадку ці ресурси знову додаються до фільтра).

## Джерела інформації

* Власна моніторингова команда
* Урядова команда реагування на комп'ютерні надзвичайні події України (CERT-UA): [https://cert.gov.ua](https://cert.gov.ua/)
* BlackList EMA [https://www.ema.com.ua/citizens/blacklist](https://www.ema.com.ua/citizens/blacklist/)

## Партнери проекту

* DNSlytics: [https://dnslytics.com](https://dnslytics.com)

## Wiki

[https://github.com/braveinnovators/url-blocklist/wiki](https://github.com/braveinnovators/url-blocklist/wiki)

## Ліцензія

На фільтр (список блокувань) Ukrainian Malicious URL Blocklist поширюються умови ліцензії [GNU General Public License v3.0](https://github.com/braveinnovators/url-blocklist/blob/main/LICENSE)
