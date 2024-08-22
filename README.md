# Ukrainian Security Filter

**Ukrainian Security Filter (Український безпековий фільтр)** — це фільтр шкідливих веб-ресурсів (фішинг, онлайн-шахрайство, дропшопінг, шкідливе програмне забезпечення тощо), що орієнтовані на громадян України.

Цей проєкт є частиною ініціативи [Ukrainian Filters](https://github.com/ukrainianfilters/lists) (Українські фільтри)

## Правила фільтрації

Щодня зловмисники активують нові шкідливі веб-ресурси за допомогою яких обманом виманюють в українців доступ до облікових записів банківських онлайн систем, реквізити платіжних карток, конфіденційну інформацію та гроші. Щодня реєструються десятки нових доменних імен, які згодом будуть використані у нових фішингових кампаніях та онлайн-шахрайстві. За таких обставин блокування шкідливих веб-ресурсів лише за назвою доменних імен не є ефективним. Саме тому Український безпековий фільтр містить три групи правил фільтрації:

1. **Стандартні правила** (domain-based blocklist) — це список блокувань за назвою доменного ім'я.

2. **Індивідуальні правила** (page-specific filtering rules) дозволяють блокувати сторінки у соціальних мережах, посилання на групи або чат-боти у месенджерах тощо, тобто цільові веб-адреси (URL-адреси) ресурсів які є легітимними, проте, які використовуються зловмисниками.

3. **Універсальні правила** (pattern-based filtering rules) дозволяють блокувати шкідливі веб-ресурси, навіть, якщо інформація про доменні імена таких ресурсів відсутня у фільтрі, адже блокування відбувається на основі [паттернів](https://mastodon.online/@braveinnovators/111364189029417720).

## Формати

### Adblock-style syntax

Цей формат фільтра сумісний з усіма браузерами, розширеннями та іншим програмним забезпеченням, що підтримує синтаксис AdBlock.

```
https://raw.githubusercontent.com/braveinnovators/ukrainian-security-filter/main/lists/adblock.txt
```

### Domain-based blocklist

Усі веб-адреси (URL-адреси) відображені у такому форматі: `example.com`

```
https://raw.githubusercontent.com/braveinnovators/ukrainian-security-filter/main/lists/domains.txt
```

### Hosts-based blocklist

Усі веб-адреси (URL-адреси) відображені у такому форматі: `0.0.0.0 example.com`

```
https://raw.githubusercontent.com/braveinnovators/ukrainian-security-filter/main/lists/hosts.txt
```

### dnsmasq

Усі веб-адреси (URL-адреси) відображені у такому форматі: `address=/example.com/`

```
https://raw.githubusercontent.com/braveinnovators/ukrainian-security-filter/main/lists/dnsmasq.txt
```

## Сумісність з браузерами та розширеннями

Незважаючи на те, що правила, які містяться у фільтрі, сумісні як з браузерами з вбудованими модулями фільтрації контенту, так і з популярними сторонніми розширеннями, користувачам персональних комп'ютерів та мобільних пристроїв на базі ОС Android ми рекомендуємо використовувати розширення [uBlock Origin](https://ublockorigin.com/) разом з браузером [Firefox](https://www.mozilla.org/firefox/) (або ж будь-який інший браузер разом із розширенням uBlock Origin).

Якщо ви використовуєте браузер Google Chrome, майте на увазі, що, починаючи з червня 2024 року, цей браузер почне поступово деактивувати розширення, які не підтримують [Manifest V3](https://blog.chromium.org/2024/05/manifest-v2-phase-out-begins.html). Це означає, що жодне розширення-блокувальник реклами більше [не зможе повноцінно працювати](https://www.theverge.com/2024/5/30/24168057/google-chrome-extension-change-manifest-v3-ad-blockers) з цим браузером. Альтернативою може стати або Firefox, або браузери на основі [Chromium](https://uk.wikipedia.org/wiki/Chromium), які продовжать підтримувати Manifest V2 та сторонні блокувальники реклами, включно з uBlock Origin.

> [!WARNING]
> Починаючи з версії 0.5, розробники розширення **Adblock** [вирішили прибрати](https://web.archive.org/web/20111206122411/http://adblockplus.org/en/faq_features#siteblock) функцію блокування веб-сторінок (strict blocking). Це означає, що ані **Adblock**, ані **Adblock Plus** не можуть блокувати доступ до шкідливих веб-ресурсів на рівні доменного ім'я. Розширення **AdGuard** так само має проблеми з обробкою правил фільтрації ([Issue #2760](https://github.com/AdguardTeam/AdguardBrowserExtension/issues/2760)), навіть тих, що прописані в документації цього розширення. Відповідно, ці розширення не є сумісними з нашим фільтром.

## Як імпортувати фільтр

### uBlock Origin

[uBlock Origin](https://ublockorigin.com/) (uBO) — платформонезалежне розширення фільтрації контенту для Firefox та інших браузерів, що засновані на [Chromium](https://uk.wikipedia.org/wiki/Chromium) (зокрема, Google Chrome, Opera, Microsoft Edge, Brave). Переваги цього розширення: вільне програмне забезпечення з відкритим кодом, ефективне використання процесора та пам'яті, об'єктивно найкращий вибір з точки зору функціональних можливостей та гнучкості налаштувань.

<details>
<summary>Windows, macOS, Linux та Android</summary>

1. Відкрити меню `Preferences` розширення uBlock Origin, клацнути мишею на вкладку `Filter lists` і прокрутити до розділу `Custom`
2. Клацнути мишею на `Import...` і у поле вводу вставити скопійовану адресу фільтра, зберігши зміни:

```
https://raw.githubusercontent.com/braveinnovators/ukrainian-security-filter/main/lists/adblock.txt
```

Додаткова інструкція доступна за адресою: [https://github.com/gorhill/uBlock/wiki/Filter-lists-from-around-the-web](https://github.com/gorhill/uBlock/wiki/Filter-lists-from-around-the-web)
</details>

### Brave

Браузер [Brave](https://brave.com/) заснований на [Chromium](https://uk.wikipedia.org/wiki/Chromium), має власний модуль фільтрації контенту з підтримкою [синтаксису фільтрації](https://support.brave.com/hc/en-us/articles/6449369961741-How-do-I-manage-Ad-Block-filters-in-Brave) розширення uBlock Origin. Цей браузер [продовжить підтримувати Manifest V2](https://brave.com/blog/brave-shields-manifest-v3/) та сторонні розширення-блокувальники реклами, включно з uBlock Origin.

<details>
<summary>Windows, macOS та Linux</summary>

1. У меню `Settings` відкрити вкладку `Shields` й змінити налаштування `Trackers & ads blocking` на `Aggressive`
2. У вкладці `Shields` відкрити розділ `Content filtering` і у розділі `Add custom filter lists` у поле вводу вставити скопійовану адресу фільтра:

```
https://raw.githubusercontent.com/braveinnovators/ukrainian-security-filter/main/lists/adblock.txt
```
</details>

<details>
<summary>Android та iOS</summary>

1. У меню `Settings` відкрити розділ меню `Brave Shields & privacy` й змінити налаштування `Block trackers & ads` на `Aggressive`
2. У розділі меню `Brave Shields & privacy` відкрити `Content filtering`, далі `Add custom filter list` і у поле вводу вставити скопійовану адресу фільтра, зберігши зміни шляхом натискання на кнопку `Add`:

```
https://raw.githubusercontent.com/braveinnovators/ukrainian-security-filter/main/lists/adblock.txt
```
</details>

> [!NOTE]
> Якщо програмне забезпечення фільтрації контенту підтримує функцію автооновлення імпортованих списків, список фільтрів у форматі adblock-style syntax буде оновлюватися автоматично. У разі необхідності цей список також можна оновлювати вручну.

## Джерела інформації

* Власна моніторингова команда
* Урядова команда реагування на комп'ютерні надзвичайні події України (CERT-UA)
* Комісія з регулювання азартних ігор та лотерей (КРАІЛ)
* BlackList EMA

## Повідомлення про шкідливі веб-ресурси

Повідомити про шкідливі веб-ресурси можна, заповнивши відповідний [шаблон звернення](https://github.com/braveinnovators/ukrainian-security-filter/issues/new?assignees=serhiyguryev&labels=malicious+website&projects=&template=report_malicious_websites.md&title=).

## Співпраця

Якщо ви створили правила фільтрації та бажаєте, щоб вони були додані до фільтра, вам необхідно:

1. Створити [fork](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/about-forks) проєкту та додати правила до файлів (списків) з відповідними фільтрами: `adblock.txt`, `dnsmasq.txt`, `domains.txt`, `hosts.txt`, що містяться в окремій директорії під назвою `sandbox`
2. Створити [pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests) (після проходження тестування, ваші правила будуть додані безпосередньо мейнтейнерами проєкту із зазначенням авторства)

## Ліцензія

На Ukrainian Security Filter (Український безпековий фільтр) поширюються умови ліцензії [GNU General Public License v3.0](https://github.com/braveinnovators/ukrainian-security-filter/blob/main/LICENSE)
