# UA: Malicious URL Blocklist

Список блокувань фішингових сайтів, які обманом виманюють в українців доступ до облікових записів банківських онлайн систем, реквізити платіжних карток, конфіденційну інформацію та гроші.

## Формати

### Domain-based blocklist

Цей формат списку блокувань сумісний практично з усіма браузерами, розширеннями та іншим програмним забезпеченням, що підтримує синтаксис AdBlock:

```
https://www.awwwwesome.org/url-blocklist/url-blocklist.txt
```

## Сумісність з браузерами та розширеннями

Нижче наведений перелік браузерів та сторонніх розширень з якими гарантована сумісність правил, які містяться у списку UA: Malicious URL Blocklist.

#### Браузери (з власними модулями фільтрації контенту)
* [Brave](https://brave.com/)

#### Розширення
* [uBlock Origin](https://ublockorigin.com/)
* [Adblock Plus](https://adblockplus.org/features)
* [AdBlock](https://getadblock.com/)
* [AdGuard Browser extension](https://adguard.com/)

## Як додати список

### Brave

- У меню Settings відкрити вкладку Shields й змінити налаштування Trackers & ads blocking на Aggressive
- У вкладці Shields відкрити розділ Content filtering і у розділі Add custom filter lists у поле вводу вставити скопійовану адресу списку:

```
https://www.awwwwesome.org/url-blocklist/url-blocklist.txt
```

<img src="doc/1676223121.gif" style="display: inline-block; margin: 20px 0; max-width: 800px">

### uBlock Origin

- Відкрити меню Preferences розширення uBlock Origin, клацнути мишею на вкладку Filter lists і прокрутити до розділу Custom
- Клацнути мишею на Import... і у поле вводу вставити скопійовану адресу списку:

```
https://www.awwwwesome.org/url-blocklist/url-blocklist.txt
```

Додаткова інструкція доступна за адресою: [https://github.com/gorhill/uBlock/wiki/Filter-lists-from-around-the-web](https://github.com/gorhill/uBlock/wiki/Filter-lists-from-around-the-web)

<img src="doc/1676223122.gif" style="display: inline-block; margin: 20px 0; max-width: 800px">

## Особливості формування та оновлення списку UA: Malicious URL Blocklist

- до списку у форматі domain-based blocklist вносяться лише домени, що дає можливість блокувати доступ до ресурсу без жорсткої прив'язки до субдоменів та (або) шляху/параметрів URL (виключення: посилання на соціальні мережі, блоги та інші ресурси які є легітимними, проте, які використовуються зловмисниками);

- кожен веб-ресурс перед додаванням до списку проходить перевірку на дійсність реєстрації доменного ім'я, при цьому, список регулярно перевіряється що, у підсумку, виключає наявність ресурсів з анульованою реєстрацією;

- неактивність веб-ресурсу за зазначеною у списку адресою не є підставою для його виключення зі списку, оскільки зловмисник може у будь-який момент відновити роботу сервера й тому ми орієнтуємося саме на дійсність реєстрації доменного ім'я, а не на технічну доступність безпосередньо веб-ресурсу;

- веб-ресурси, які виключаються зі списку через анулювання або закінчення дії реєстрації доменного ім'я, вносяться до архівного списку, який також регулярно перевіряється на предмет повторної реєстрації доменного ім'я та активації зловмисних веб-ресурсів (у такому випадку ці ресурси знову додаються до основного списку).

## Джерела інформації

* [CERT-UA (Урядова команда реагування на комп’ютерні надзвичайні події України)](https://cert.gov.ua/)
* [BlackList EMA](https://www.ema.com.ua/citizens/blacklist/)

## Ліцензія

На список UA: Malicious URL Blocklist поширюються умови ліцензії [GNU General Public License v3.0](https://github.com/S5Innovators/url-blocklist/blob/main/LICENSE)
