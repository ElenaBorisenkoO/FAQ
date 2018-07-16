# 🤔 FAQ

---

> Заметка: FAQ — это аббревиатура от Frequently Asked Questions (часто задаваемые вопросы).

---

## 📜 Содержание

-   [🌏 Настройка окружения](#-Настройка-окружения)
-   [🏎 Запуск и остановка проекта](#-Запуск-и-остановка-проекта)
-   [🥊 npm и yarn](#-npm-и-yarn)
-   [🤔 FAQ](#-faq)

<br>

### 🌏 Настройка окружения

#### ❓ Вопрос: как установить Node.js?
✅ Ответ: [скачать с официального сайта](https://nodejs.org/en/) и установить последнюю версию Node.js.

<br>

#### ❓ Вопрос: как установить или обновить Git?
✅ Ответ: [скачать с официального сайта](https://git-scm.com/download/) и установить последнюю версию Git.

<br>

#### ❓ Вопрос: как обновить Node.js?
✅ Ответ: возможно два варианта.
+ `Первый`: если вы установили Node.js установщиком с сайта, то обновить тоже нужно с помощью [установщика последней версии](https://nodejs.org/en/).
+ `Второй`: если вы установили Node.js [через `nvm`](https://github.com/creationix/nvm), то обновить тоже нужно с помощью команды `nvm install --lts --latest-npm`.

<br>

### 🏎 Запуск и остановка проекта

#### ❓ Вопрос: У меня не запускается проект. Что делать?
Ответ: есть несколько решений:

1. Посмотри консоль на наличие ошибок;
2. Прочитай текст ошибки. Чаще всего, текст ошибки сам по себе объясняет её причину.
    + Самая частая ошибка: `Error: listen EADDRINUSE 0.0.0.0:3000`. Давай разберёмся как её решить. Читаем:
        + Первое слово — `Error`, говорит о том, что это ошибка;
        + Второе слово — `listen`, говорит о том, что ошибка связана с процессом «прослушивания»;
        + Далее — `EADDRINUSE 0.0.0.0:3000`, первая часть (буквы) — это описание ошибки, вторая часть (цифры) — адрес в формате хост:порт;
        + `EADDRINUSE` — это аббревиатура. Пу сути её можно разгадать путем обычной логики:
            + `E` — означает Error, ошибка;
            + `ADDR` — сокращение от address, адрес;
            + `INUSE` — сокращение in use — в использовании.
        + Итого, можно составить заключение, что адрес `0.0.0.0:3000` чем-то используется. Webpack поднимает проект именно на этом адресе. Этот адрес уже занят каким-то процессом, поэтому — возникает ошибка;
        + **`Решение`**:
            + Найди, какие процессы твоего компьютера используют данный адрес, и выключи их;
            + Если не можешь найти эти процессией через терминал — перегрузи компьютер.

#### ❓ Вопрос: как остановить запущенный командой npm run start (или yarn start) проект?
Ответ: В терминале нажми сочетание клавиш `CTRL` + `C`.

<br>

### 🥊 npm и yarn

#### ❓ Вопрос: в чём разница между npm и yarn?
Ответ: это два разных менеджера npm-пакетов. Можно почитать об их отличиях [здесь](https://ua-blog.com/npm-vs-yarn-%D0%BA%D0%B0%D0%BA%D0%BE%D0%B9-%D0%BC%D0%B5%D0%BD%D0%B5%D0%B4%D0%B6%D0%B5%D1%80-%D0%BF%D0%B0%D0%BA%D0%B5%D1%82%D0%BE%D0%B2-%D1%81%D1%82%D0%BE%D0%B8%D1%82-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB/) и [здесь](https://blog.risingstack.com/yarn-vs-npm-node-js-package-managers/).


#### ❓ Вопрос: что лучше — npm или yarn?
Ответ: на этот, как и на многие другие вопросы типа «а что лучше...?», увы, ответа-серебрянной пули нет.
> У каждого пакета есть свои достоинства и недостатки. Мы используем [yarn](https://yarnpkg.com/en/docs), так как по нашему мнению он обладает более удобным и красивым интерфейсом.



#### ❓ Вопрос: почему весь мой код подсвечивает редактор?
Ответ: возможно два варианта.
> `Первый`: ваш редактор расценивает код как неправильный. Это может произойти, когда вы пишете разметку JSX React без поддержки вашим редактором такого синтаксиса. Чтобы включить поддержку — нужно скачать соответствующий плагин для редактора. [Вот пример](https://atom.io/packages/language-babel) такого плагина для редактора Atom.

> `Второй`: ваш код подсвечивает линтер, указывая на стилистические ошибки.


#### ❓ Вопрос: что такое линтер?
Ответ: линтер — это статический анализатор кода.
> Он сообщает разработчику о стилистических и функциональных ошибках в программном коде. Мы используем [ESLint для JavaScript](https://eslint.org/), и [stylelint для CSS](https://stylelint.io/) . Детально о том, как работает линтер на примере ESLint можно [узнать здесь](https://www.youtube.com/watch?v=hppJw2REb8g).


#### ❓ Вопрос: как включить поддержку синтаксиса `PostCSS` в `WebStorm`?
Ответ: возможно несколько вариантов:
+ `WebStorm`: [следуй этому гайду](https://plugins.jetbrains.com/plugin/8578-postcss-support).


#### ❓ Вопрос: что такое `Prettier`? 
Ответ: [`Prettier`](https://prettier.io/) — это интрумент для форматирования JavaScript.


#### ❓ Вопрос: как сделать, чтобы `Prettier` и `ESLint` работали вместе?
Ответ: всё не так просто:
+ У `ESLint` есть настройки, по которым он проводит анализ кода и говорит вам об ошибках.
+ Пакет [`prettier-eslint-cli`](https://github.com/prettier/prettier-eslint-cli) — это интеграция `Prettier` и `ESLint`, как мостик между двумя берегами.

```
Prettier 🏖 ← мостик prettier-eslint-cli → 🏖 ESLint
```

+ То есть, чтобы `Prettier` понимал, что форматировать код нужно именно по правилам `ESLint` — нужно обязательно [использовать интеграцию `prettier-eslint-cli`](https://github.com/prettier/prettier-eslint-cli#installation).

#### ❓ Вопрос: Как настроить `Prettier` с `ESlint`, чтобы можно было форматировать код по хотекю:
Ответ: возможно несколько вариантов:
+ [WebStorm](https://prettier.io/docs/en/webstorm.html#using-prettier-with-eslint)
