<h1> Качество кода - линтеры и т.д. </h1>

[//]: # (Я использую)
<details><summary><b>Я использую</b></summary><p>

- Для работы с React JS в PhpStorm использую
    - [ESLint](https://eslint.org) - показывает ошибки, позволяет автоматически исправить некоторые из них
    - [Prettier](https://prettier.io/) / [Prettier miscellaneous](https://github.com/arijs/prettier-miscellaneous) - оформляет, форматирует код по образцу (пробелы, запятые и т.д.). Пока отказался - не смог нормально настроить [выравнивание значений в объектах друг-над-другом](https://github.com/prettier/prettier/issues/1622) - чтоб не было конфликта с правилом ESLint [KeySpacing align after column by value](https://github.com/prettier/prettier/issues/1622). Ну и в целом он мне пока не нужен - большую часть вопросов решает ESLint --fix + настройки по реформатированию кода в IDEPhpStorm
    - [Husky](https://github.com/typicode/husky) и [lint-staged](https://github.com/okonet/lint-staged) - позволяет запускать эти проверки перед отправкой коммита. Использует возможности [Git hooks](https://git-scm.com/book/ru/v2/%D0%9D%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-Git-%D0%A5%D1%83%D0%BA%D0%B8-%D0%B2-Git).
- Отказался
    - [JSHint](https://jshint.com/) - не разобрался как отключить некоторые ошибки. Например, не умеет воспринимать стрелочные функции в классовых компонентах React JS, даже в режиме ES6. Пишет "Class properties must be methods". Возможно сейчас ситуация улучшилась, но пока не актуально
    - [TSLint](https://palantir.github.io/tslint/) — поддержка прекращена в 2019. Переходите на ESLint

<br></p>
</details>

[//]: # (ESLint)
<details><summary><b>ESLint</b></summary><p>

- Линтер — это помощник по части «здоровья» кода. Вы определяете список правил и в дальнейшем, при настроенном плагине в вашем редакторе, он как Microsoft Word «проферка орфографии» проверяет все, что вы написали. Например, определили переменную, но нигде не используете? Сработает правило: no-unused-vars (долой неиспользуемые переменные) и переменная будет подчеркнута.
- Когда вы видите «подчеркивание», и после наведения видите в скобочках название правила — не нужно бежать гуглить. Нужно идти на сайт [eslint.org](https://eslint.org/docs/rules/) и там в «поиск» вставлять текст ошибки, будет быстрее.
- Суть линтинга с помощью ESLint заключается в парсерах, которые трансформируют код в AST (Abstract Syntax Tree) для дальнейшей программной обработки, и плагинах, которые содержат правила.
- Чтобы достичь большей консистентности кодовой базы, можно выбрать и добавить в конфиг ESLint правила одного из популярных стайл гайдов:
   - AirBnB: самый популярный и строгий из этих трёх, обязательные замыкающие запятые и точки с запятыми.
   - Google: похож на AirBnB в плане форматирования, но менее строгий, обязательные комментарии JSDoc.
   - StandartJS: запрещает использовать замыкающие запятые и точки с запятыми.
- Выбирайте реализацию стайл гайда на TypeScript, потому что правила для JavaScript могут неправильно отрабатывать на TypeScript.
- Поиск ошибок производится следующим образом:
  - автоматически в процессе написания кода (нужно настроить инспектор синтаксиса в PhpStorm)- ошибки подсвечиваются, выдаётся всплывающее сообщение с комментарием
  - при совершении опр. действий, например при сохранении файла (нужно настроить плагин линтера в PhpStorm)
  - при запуске в консоли команды, например `lint` (нужно настроить скрипты в файле `package.json`) - в консоли будет выведена подробная информация - в каком файле на какой строке какая ошибка. Можно не писать команду в консоли, а вызывать из выпадающего меню `Run` в PhpStorm
  - если настроить скрипт в файле `package.json` - можно также вызывать команду исправления ошибок (через консоль или из выпадающего меню `Run`). Исправляет не все, но многие. 
- При конфликте между стандартным `Reformat code` от PhpStorm (`Ctrl + Alt + L`) и ESLint. Например в правиле о выравнивании ключей/значений в объектах при помощи пробелов ([key-spacing](https://eslint.org/docs/latest/rules/key-spacing)) 
  - По идее надо настраивать в `File | Settings | Editor | Code Style | JavaScript`, вкладка `Wrapping & Braces`, раздел `Objects`
  - Если не помогло: иду в `File | Settings | Keymap`, удаляю клавиатурное сокращение `Ctrl + Alt + L` у `Reformat code` и навешиsваю его на `Fix ESLint Problems`
  - Также обратить внимание на `File | Settings | Tools | Actions on Save`
<br>
<br>

**Установка / Настройка**
- поддержка JSHint включена в PhpStrom по-умолчанию, никаких доп. плагинов к самому PhpStrom ставить не надо
- устанавливаю ESLint локально в проекте 
  - Ставить только если НЕ использую `Create React APP`
  - В `Create React APP` включен по-умолчанию
  - `yarn add eslint eslint-plugin-react eslint-plugin-jsx-a11y --dev`
- рекомендуют поставить эти плагины
  - `yarn add eslint-plugin-prettier eslint-config-prettier babel-eslint --dev`
- закидываю в корень свой конфигурационный файл `.eslintrc.json`
- если я использую дополнительные плагины, например `React` и `JSX A11y` - их надо включить в секции `extends`
    - пример
      ```
      "extends": [
        "eslint:recommended",
        "plugin:react/recommended",
        "plugin:jsx-a11y/recommended"
      ],
- в настройках PhpStorm
  - включаю режим `React JSX` - `Settings\Languages & Frameworks\JavaScript`
    - Если варианта `React JSX` нет - можно выбрать `ECMAScript 6+`
  - включаю `ESLint` в настройках PhpStorm
      - `Settings\Languages & Frameworks\JavaScript\Code Quality Tool`
  - настраиваю `Settings\Languages & Frameworks\JavaScript\Code Quality Tool\ES Lint`
    - включаю `manual ES Lint configuration`
    - указываю путь к папке `ESLint package`
      - например `D:\Work\_Localsites\legmo_hotquotes\node_modules\eslint`
      - т.е. указываю путь не к глобальному модулю, а к модулю из Create React App, внутри проекта
    - указываю папку `Working directories`
      - например `D:\Work\_Localsites\legmo_hotquotes\src`
    - указываю путь к файлу конфигурации `Configuration file`
      - например D:\Work\_Localsites\legmo_hotquotes\.eslintrc.json
      - Его пришлось убрать и перевести в режим `Automatic search`. Плюс убрать все конфиг файлы ESLint из папок верхних уровней (`D:\Work\_Localsites`, `D:\Work\` и т.д.). После этого PhpStorm "увидел" конфиг файл в проекте
  - чтобы получать предупреждения об ошибках в синтаксисе JSX - открыть раздел настроек `Editor | Inspections`
    - включаю инспектор синтаксиса `React JSX` в `JavaScript and TypeScript | General node`.
- проверяю что ESLint работает
  - берём какое-то правило, например `quotes` и нарушаем его в коде
  - у меня в файле конфигурации ESLint (`.eslintrc.json`) стоит настройка: кавычки должны быть одинарными, и это помечается как Warning
  - ставлю в коде двойные - появляется сообщение инспектора, warning
  - теперь проверим, что это срабатывает правило именно из моего файла конфигурации ESLint (`.eslintrc.json`) — для правила "quotes" меняю в нём "warn" на "error"
  - если всё ок, то у меня в коде сообщение инспектора для двойных кавычек должно измениться с warning на error
- в файле `package.json` (корень проекта) дописываю команды в секцию "scripts"
  - например:
  ```
  "scripts": {
    <что там было>
    "lint": "eslint --debug src/",
    "lint-fix": "eslint --debug src/ --fix"
  },
  ```
- Настраиваю файл `.eslintignore` - чтобы исключить из проверки директории/файлы указываем их в виде списка
  - За основу можно взять .gitignore
  <br>
  <br>

**Плагины**
- Eslint-plugin-react
  - [GitHub](https://github.com/jsx-eslint/eslint-plugin-react)
  - Обратите внимание, что поддержка синтаксиса JSX — это не то же самое, что поддержка React.
  - React применяет к синтаксису JSX особую семантику, которую ESLint не распознает.
  - Мы рекомендуем использовать `eslint-plugin-react`, если вы используете React и хотите использовать семантику React.
- Eslint-plugin-jsx-a11y
  - [GitHub](https://github.com/jsx-eslint/eslint-plugin-jsx-a11y)
  - предоставляет правила, касающиеся доступности JSX-элементов для людей с ограниченными возможностями.
- Eslint-plugin-prettier
  - [GitHub](https://github.com/prettier/eslint-plugin-prettier)
  - помогает совместной работе ESLint и Prettier. Выглядит это следующим образом: когда Prettier форматирует код, он делает это с учётом правил ESLint.
<br>
<br>

**Автоматическая правка некоторых ошибок ESLint**
- Настрой PhpStorm - ёSettings\Languages & Frameworks\JavaScript\Code Quality Tool\ES Lint` - внизу галочка `Run eslint --fix on save`
- [Официальная документация (eng)](https://eslint.org/docs/user-guide/command-line-interface#fixing-problems)
<br>
<br>

**Файл конфигурации**
- Имеет следующую структуру:
    ```
    module.exports = { 
       env:{}, 
       extends: {}, 
       plugin: {}, 
       parser: {}, 
       parserOptions: {}, 
       rules: {},
    };
- **env** — позволяет задавать список сред, код для которых планируется проверять. В нашем случае тут имеются свойства es6, browser и node, установленные в true. 
  - es6 - включает возможности ES6 за исключением модулей (эта возможность автоматически устанавливает, в блоке parserOptions, параметр ecmaVersion в значение 6). 
  - browser - подключает глобальные переменные браузера, такие, как Windows. 
  - node - добавляет глобальные переменные среды Node.js и области видимости, например — global. 
- **extends** — представляет собой массив строк с конфигурациями, при этом каждая дополнительная конфигурация расширяет предыдущую. Здесь используются правила линтинга airbnb, которые расширены до jest и затем расширены до jest-enzyme.
- **plugins** — тут представлены правила линтинга, которые мы хотим использовать. У нас применяются правила babel, import, jsx-a11y, react, prettier, о которых мы уже говорили.
- **parser** — по умолчанию ESLint использует синтаксический анализатор Espree, но, если мы работаем с Babel, нам надо пользоваться Babel-ESLint.
- **parserOptions** — так как мы изменили стандартный синтаксический анализатор на babel-eslint, нам необходимо задать и свойства в этом блоке. Свойство ecmaVersion, установленное в значение 6, указывает ESLint на то, что проверяться будет ES6-код. Так как код мы пишем в EcmaScript-модулях, свойство sourceType установлено в значение module. И, наконец, так как мы используем React, что означает применение JSX, то в свойство ecmaFeatures записывается объект с ключом jsx, установленным в true.
- **rules** — позволяет настраивать правила ESLint. Все правила, которые мы расширили или добавили с помощью плагинов, можно менять или переопределять, и делается это именно в блоке rules.
<br>
<br>

**Пример файла конфигурации для ESLint (`.eslintrc.json`)**
```
    {
        "env": {
            "es6": true,
            "browser": true,
            "node": true
        },
        "parserOptions": {
            "ecmaVersion": "latest",
            "sourceType": "module",
            "ecmaFeatures": {
                "jsx": true
            }
        },
    "extends": [
        //  https://eslint.org/docs/rules/
        "eslint:recommended",
        "plugin:react/recommended",
        "plugin:jsx-a11y/recommended"
    ],
    "plugins": [
        "react"
    ],
    "rules": {
        //  https://eslint.org/docs/rules/semi
        //  "semi": 0, //Disable semicolon error
        "semi": "error",
        // https://eslint.org/docs/rules/no-multi-spaces
        "no-multi-spaces": [
            "warn",
            {
                "exceptions": {
                    "VariableDeclarator": true
                }
            }
        ],
        //  https://eslint.org/docs/rules/key-spacing
        "key-spacing": [
            "error",
            {
                "align": {
                    //          "beforeColon": true,
                    //          "afterColon": true,
                    "on": "value"
                }
            }
        ],
        "react/jsx-equals-spacing": "warn", // https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/jsx-equals-spacing.md
        "react/prop-types": "warn", // https://github.com/yannickcr/eslint-plugin-react/blob/master/docs/rules/prop-types.md
        "jsx-a11y/label-has-for": "warn", // https://github.com/evcohen/eslint-plugin-jsx-a11y/blob/master/docs/rules/label-has-for.md
        "linebreak-style": "off" // Does not work correctly on Windows.
        }
    }
```
<br>
<br>

**Заметки**
- любое правило можно отключить для куска кода
  - `// eslint-disable-line no-unused-vars`
  - `/* eslint react/jsx-one-expression-per-line: "off" */`
  - https://eslint.org/docs/user-guide/configuring.html#configuring-rules
  - https://eslint.org/docs/user-guide/configuring.html#disabling-rules-with-inline-comments
- любое правило можно "отключить" вообще - `"semi": "off"`
- любому правилу можно перевести в другой статус:
    - сделать предупреждением - `"semi": "warn"`
    - сделать ошибкой - `"semi": "error"`
- Не работают правила линтера или форматирование отличается от ожидаемого.
  - Возможно, это следствие наличия в проекте других конфигурационных файлов. Они имеют разный приоритет исполнения. Например, файл `.editorconfig `имеет высший приоритет, чем `.eslintrc`, поэтому линтер будет выставлять настройки с его помощью.
<br>
<br>

**Ссылки**
- [ESLint official site](https://eslint.org)
- [ESLint official site - rules list](https://eslint.org/docs/rules/)
- [Hexlet - Руководство Eslint + Prettier](https://ru.hexlet.io/blog/posts/rukovodstvo-eslint-prettier)
- [Хабр - Prettier, ESLint, Husky, Lint-Staged и EditorConfig: инструменты для написания аккуратного кода (2018)](https://habr.com/ru/company/ruvds/blog/428173/)
- [Хабр - Переносим Angular проект на ESLint, с Prettier, Husky и lint-staged (2020)](https://habr.com/ru/post/501830/)
- [Настройка ESLint, Prettier, pre-commit hook (create-react-app, visual studio code)](https://maxpfrontend.ru/vebinary/nastroyka-eslint-prettier-pre-commit-hook-create-react-app-visual-studio-code/)

<br></p>
</details>

[//]: # (TSLint)
<details><summary><b>TypeScript Linting</b></summary><p>

Раньше был линтер [TSLint](https://palantir.github.io/tslint/) — поддержка прекращена в 2019. Переходите на ESLint.

Есть [TypeScript ESLint](https://typescript-eslint.io/) — надо разбираться

**Инструкция**
- Как использовать ESLint для проверки TypeScript
- Не уверен, что это правильный ход, но я делаю так
- ставлю плагин `@typescript-eslint`
- прописываю его в файле настроек ESLint (`.eslintrc.json`), секция `"plugins"`
- в файле настроек ESLint (`.eslintrc.json`), в секции `"rules": {}` завожу секцию `@typescript-eslint/ИМЯ_ПРАВИЛА:[ настройки]`
  - ==ПРИМЕР С ОТСТУПОМ НЕ СТОИТ ИСПОЛЬЗОВАТЬ!== — он ведёт к ошибкам. См. https://github.com/typescript-eslint/typescript-eslint/issues/1824. Использую для таких случаев Prettier либо настройки IDE
  - например: `"@typescript-eslint/indent": ["warn","tab"]`
  - пример описания для этого правила https://typescript-eslint.io/rules/indent


**Ссылки**
- [TypeScript ESLint](https://typescript-eslint.io/)
- [eslint.org - Configuration Files](https://eslint.org/docs/latest/user-guide/configuring/configuration-files)
- [Medium - Настройка ESLint в проекте React Typescript](https://andrebnassis.medium.com/setting-eslint-on-a-react-typescript-project-2021-1190a43ffba)
- [TSLint](https://palantir.github.io/tslint/) — поддержка прекращена в 2019. Переходите на ESLint

<br></p>
</details>

[//]: # (Prettier / Prettier miscellaneous)
<details><summary><b>Prettier / Prettier miscellaneous</b></summary><p>

- это помощник по части оформления кода. Можно писать с пробелами перед именем свойства, кавычками, запятыми в последней строке и т.д. — Prettier, настроенный на сохранение или на пре-коммит хук «перетрясет» ваши файлы и оформит их в соответствии с настройками, которых у него минимум. Это сделано специально, ибо чем меньше настроек, тем меньше конфигураций.
- Зачем использовать Prettier, если ESLint тоже умеет форматировать код? Ответ — Prettier форматирует код намного лучше: убирает всё форматирование и полностью переписывает код в едином стиле. Это позволяет разработчикам забыть о форматировании кода и не тратить время на обсуждение стиля кода на ревью. ESLint не всегда может всё исправить, часто он просто показывает "здесь ошибка", и править её требуется в ручном режиме.
- [Prettier miscellaneous](https://github.com/arijs/prettier-miscellaneous) - форк (альтернативная версия) Prettier. Ставлю его. Добавляет поддержку некоторых дополнительных правил. Например, поддерживает [выравнивание значений в объектах друг-над-другом](https://github.com/prettier/prettier/issues/1622) - чтоб не было конфликта с правилом ESLint [KeySpacing align after column by value](https://github.com/prettier/prettier/issues/1622). 
<br>
<br>

**Установка / Настройка**
- Устанавливаю Prettier локально в проект (даже если использую Create React APP)
  - `yarn add --dev --exact prettier`
- Также рекомендуют поставить эти плагины
  - `yarn add eslint-plugin-prettier eslint-config-prettier babel-eslint --dev`
- В настройках `PhpStorm / Plugins` включаю плагин `Prettier`
- В настройках `PhpStorm / Languages & Frameworks / Javascript / Prettier`
  - указываю путь к `Prettier package`, например `D:\Work\_Localsites\legmo_hotquotes\node_modules\prettier`
  - или `D:\Work\_Localsites\legmo_hotquotes\node_modules\prettier-miscellaneous`
  - включаю настройку `Run on Reformat code action`
  - включаю настройку `Run on save`
- Копирую в корень проекта файл конфигурации `.prettierrc.json`
- Создаю файл `.prettierignore` чтобы `Prettier CLI` и редакторы знали, какие файлы не следует форматировать.
  - команда создания файла через терминал: `echo {}> .prettierignore`
  - пример файла:
    ```
    # Ignore artifacts:
      build
      coverage
    ```
  - Основывайте свой `.prettierignore` на `.gitignore` и `.eslintignore` (если он у вас есть).
  - Если ваш проект еще не готов к форматированию, скажем, файлов HTML, добавьте в исключения *.html.
- В документации указан еще один способ конфигурации. Помимо конфигурационных файлов можно опубликовать свой конфиг как NPM-пакет, хотя бы даже только на GitHub. После этого вы сможете устанавливать свой собственный пакет во все свои проекты. Таким образом любой человек, который тоже захочет поработать над вашими проектами (контрибьютор на GitHub) будет использовать тот же конфиг-файл.
 <br>
 <br>

**Ссылки**
- [Prettier official site](https://prettier.io/)
- [Prettier official site - format options](https://prettier.io/docs/en/options.html)
- [Prettier official site - installation](https://prettier.io/docs/en/install.html)
- [Prettier official site - configuration](https://prettier.io/docs/en/configuration.html)
- [Начните использовать Prettier правильно](https://techrocks.ru/2021/02/19/prettier-configuration/)
- [Hexlet - Руководство Eslint + Prettier](https://ru.hexlet.io/blog/posts/rukovodstvo-eslint-prettier)
- [Хабр - Prettier, ESLint, Husky, Lint-Staged и EditorConfig: инструменты для написания аккуратного кода (2018)](https://habr.com/ru/company/ruvds/blog/428173/)
- [Хабр - Переносим Angular проект на ESLint, с Prettier, Husky и lint-staged (2020)](https://habr.com/ru/post/501830/)
- [Настройка ESLint, Prettier, pre-commit hook (create-react-app, visual studio code)](https://maxpfrontend.ru/vebinary/nastroyka-eslint-prettier-pre-commit-hook-create-react-app-visual-studio-code/)

<br></p>
</details>

[//]: # (Husky, lint-staged и Git хуки)
<details><summary><b>Husky, lint-staged и Git хуки</b></summary><p>

- [Git хуки](https://git-scm.com/book/ru/v2/%D0%9D%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-Git-%D0%A5%D1%83%D0%BA%D0%B8-%D0%B2-Git) — это скрипты, которые Git вызывает при определённых событиях: commit, push, recieve. С помощью них, мы можем запускать линтинг кода при создании коммита, чтобы в пул реквесты попадало меньше ошибок. 
- Для более удобной работы с Git хуками установим [Husky](https://github.com/typicode/husky)
- Чтобы проверять только тот код, который добавлен в коммит [lint-staged](https://github.com/okonet/lint-staged). Это полезно в больших проектах, где линтинг занимает много времени. Пакет Lint-staged позволяет проверять с помощью линтера индексированные файлы, что помогает предотвратить отправку в репозиторий кода с ошибками.


**Установка / Настройка**
- Важно! В версии husky 6 и выше нужно использовать файлы настроек в .husky (вместо packge.json)
- Устанавливаю Husky и lint-staged локально в проект (даже если использую Create React APP)
  - `yarn add --dev husky` или `npm install husky --save-dev`
  - Включаю Git hooks
    - `npx husky install` 
  - В `packge.json` добавляю секцию
      ```
    "scripts": {
       ...
      "prepare": "husky install"
    }
      ```
  - В папке `.husky` создаём файл `pre-commit` (прямо в этой папке, и прямо так - без расширения).
    - содержимое файла:
    - ```
      #!/usr/bin/env sh
      . "$(dirname -- "$0")/_/husky.sh"
      ```
  - В `.husky/pre-commit` дописываю внизу файла команды, которые должны выполняться перед коммитом:
    ```
    eslint --fix
    prettier -u -w .
    npm run build
    git add
    ```
- получается, перед каждым коммитом будет 
  - вызываться `ESLint` в режиме `--fix`
  - отрабатывать `prettier` в режиме `--write` (перезапишет файлы, т.е. исправит в них ошибки по правилам указанным в файле конфигурации `.prettierrc.json`) и `--ignore-unknown` (будет игнорировать неизвестные файлы)
  - выполняться `npm run build`
  - и только потом совершаться `git add`

**Ссылки**
- [Husky official GitHub](https://github.com/typicode/husky)
- [lint-staged official GitHub](https://github.com/okonet/lint-staged)
- [Хуки в Git](https://git-scm.com/book/ru/v2/%D0%9D%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B9%D0%BA%D0%B0-Git-%D0%A5%D1%83%D0%BA%D0%B8-%D0%B2-Git)
- [Хабр - Prettier, ESLint, Husky, Lint-Staged и EditorConfig: инструменты для написания аккуратного кода (2018)](https://habr.com/ru/company/ruvds/blog/428173/)
- [Хабр - Переносим Angular проект на ESLint, с Prettier, Husky и lint-staged (2020)](https://habr.com/ru/post/501830/)
- [Настройка ESLint, Prettier, pre-commit hook (create-react-app, visual studio code)](https://maxpfrontend.ru/vebinary/nastroyka-eslint-prettier-pre-commit-hook-create-react-app-visual-studio-code/)

<br></p>
</details>

[//]: # (JSHint)
<details><summary><b>JSHint</b></summary><p>

**Установка / Настройка**
- поддержка JSHint включена в PhpStrom по-умолчанию, никаких доп. плагинов к самому PhpStrom ставить не надо
- включаю режим `React JSX` в настройках PhpStrom `Settings\Languages & Frameworks\JavaScript`
    - Если варианта `React JSX` нет - можно выбрать `ECMAScript 6+`
- включаю JSHint в настройках PHP Strom `Settings\Languages & Frameworks\JavaScript\Code Quality Tool`
- указываю путь к Custom configuration file в настройках PHP Strom `Settings\Languages & Frameworks\JavaScript\Code Quality Tool`
<br>
<br>

**Пример фала конфигурации для JSHint (файл `.jshintrc`)**
```
{
    "bitwise":    true,
    "curly":      true,
    "eqeqeq":     true,
    "esversion":    9,
    "forin":      true,
    "funcscope":    true,
    "futurehostile":  true,
    "indent":     2,
    "latedef":    true,
    "maxdepth":   5,
    "maxerr":     100,
    "maxparams":    5,
    "noarg":      true,
    "noempty":    true,
    "nonew":      true,
    "quotmark":   "double",
    "strict":     true,
    "undef":      true,
    "unused":     true,
    "browser":    true
}
```

<br></p>
</details>

[//]: # (Конфигурационные файлы, .editorconfig)
<details><summary><b>Конфигурационные файлы, .editorconfig</b></summary><p>

- Разные члены вашей команды могут использовать разные редакторы. Принуждать их использовать какой-то один редактор ни к чему. Однако для того, чтобы все пользовались едиными настройками, касающимися, например, отступов или символов перевода строки, мы и применяем файл .editorconfig. Он помогает поддерживать единый набор правил в неоднородных командах.
- Конфигурационные файлы имеют разный приоритет исполнения. Например, файл .editorconfig имеет высший приоритет, чем .eslintrc., поэтому линтер будет выставлять настройки с его помощью.

**Ссылки**
- [Хабр - Prettier, ESLint, Husky, Lint-Staged и EditorConfig: инструменты для написания аккуратного кода (2018)](https://habr.com/ru/company/ruvds/blog/428173/)

<br></p>
</details>

[//]: # (Прочие ссылки)
<details><summary><b>Прочие ссылки</b></summary><p>
- [Hexlet - Руководство Eslint + Prettier](https://ru.hexlet.io/blog/posts/rukovodstvo-eslint-prettier)
- [Хабр - Prettier, ESLint, Husky, Lint-Staged и EditorConfig: инструменты для написания аккуратного кода (2018)](https://habr.com/ru/company/ruvds/blog/428173/)
- [Хабр - Переносим Angular проект на ESLint, с Prettier, Husky и lint-staged (2020)](https://habr.com/ru/post/501830/)
- [Настройка ESLint, Prettier, pre-commit hook (create-react-app, visual studio code)](https://maxpfrontend.ru/vebinary/nastroyka-eslint-prettier-pre-commit-hook-create-react-app-visual-studio-code/)

<br></p>
</details>

<br>
<br>

*[Legmo, 2019-2022](https://github.com/Legmo/notes/)*
