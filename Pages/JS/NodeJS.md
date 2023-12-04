<h1> NodeJS </h1>

[//]: # (NodeJS)
<details><summary><b>NodeJS</b></summary><p>

  - Node.js — это среда выполнения языка JavaScript. Просто другой способ выполнять код на вашем компьютере. Если вы хотите, чтобы платформа была HTTP-сервером, вам придётся написать HTTP-сервер (с помощью встроенных библиотек).
  - Для проверки успешной установки Node.js используйте команду `$ node -v`
  - Обновление под Windows - просто скачай и установи заново с сайта https://nodejs.org/en/
  - В Win 10x64 по-умолчанию ставится в C:\Program Files\nodejs\
  - Первая версия node.js представлена в 2009

  **Ссылки**
  - [Node.js - Official site](https://nodejs.org/en/)
  - [Node.js - Официальная документация на русском](https://nodejs.org/ru/docs/)
    - [Дока - Что такое Node.js](https://doka.guide/tools/nodejs/)
  - [Хабр - Руководство по Node.js (10 частей)](https://habr.com/ru/company/ruvds/blog/422893/)
  - [metanit.com - Руководство по Node.js](https://metanit.com/web/nodejs/)
  - [Manuel Kiessling - Node.js для начинающих (2013)](http://spmbt.github.io/NodeBeginnersBook-ru/)
  - [Кантор - Скринкаст по Node.JS (YouTube, 2021)](https://www.youtube.com/playlist?list=PLDyvV36pndZFWfEQpNixIHVvp191Hb3Gg)

<br></p>
</details>

[//]: # (NPM - Node Packet Manager)
<details><summary><b>NPM (Node Packet Manager)</b></summary><p>

  - Менеджер пакетов (инструмент Command Line Interface), входящий в состав Node.js + онлайн-репозиторий для публикации проектов Node.js с открытым исходным кодом.
  - Использует клиент командной строки и базу данных, состоящую из общедоступных и приватных пакетов, известной как npm registry. Пользователи могут получить доступ к базе через сайт или через консоль.
  - Автоматизация процесса установки, обновления и удаления сторонних модулей, управление зависимостями.
  - Позволяет разработчикам устанавливать пакеты как глобально, так и локально.
  - Для проверки успешной установки npm используйте команду `$ npm -v`
  - Сам по себе npm не запускает никаких пакетов. Если вы хотите запустить пакет, используя npm, вы должны указать этот пакет в своем файле `package.json`. НУ или ещё как-то извернуться

  **Ссылки**
  - [Official Site](https://www.npmjs.com)
  - [npm trends - Compare NPM package downloads](https://www.npmtrends.com)
  - [Cheat Sheet: npm vs Yarn Commands](https://www.digitalocean.com/community/tutorials/nodejs-npm-yarn-cheatsheet)

<br></p>
</details>

[//]: # (Yarn)
<details><summary><b>Yarn</b></summary><p>

  - менеджер пакетов, альтернатива npm. Разработан в Facebook чтобы избавится от недостатков npm.
  - технически Yarn не является заменой npm - берет информацию про модули из базы npm. Yarn это новый установщик который по-прежнему базируется на структуре заданной npm. В Yarn доступны все те же пакеты, что и в npm, поэтому, переезд с npm на Yarn не требует больших усилий.
  - Отличия от npm:
    - Наличие yarn.lock файла для хранения списка зависимостей
    - Работает быстрее
    - Безопаснее - не позволяет автоматически запускать код зависимостей и добавлять зависимости на лету.
  - Недостатки Yarn:
     - Одновременное использование npm и Yarn создает конфликты. 
     - Большая необходимость в дисковом пространстве, так как Yarn сохраняет зависимости локально.
    
    **Ссылки**
    - [npm vs Yarn — какой менеджер пакетов стоит использовать ?](https://ua-blog.com/npm-vs-yarn-%D0%BA%D0%B0%D0%BA%D0%BE%D0%B9-%D0%BC%D0%B5%D0%BD%D0%B5%D0%B4%D0%B6%D0%B5%D1%80-%D0%BF%D0%B0%D0%BA%D0%B5%D1%82%D0%BE%D0%B2-%D1%81%D1%82%D0%BE%D0%B8%D1%82-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB/)
- [Cheat Sheet: npm vs Yarn Commands](https://www.digitalocean.com/community/tutorials/nodejs-npm-yarn-cheatsheet)

<br></p>
</details>

[//]: # (NPX)
<details><summary><b>NPX</b></summary><p>

  - Инструмент Command Line Interface для упрощения установки и управления зависимостями, размещенными в реестре npm
  - Для проверки успешной установки npm используйте команду `$ npx -v`
  - Позволяет:
    - легко запускать локально установленный пакет из коммандной строки (не надо прописывать его в package.json и т.д.). Без необходимости указывать полный путь до исполняемого файла - npx сам найдёт где у тебя установлен данный пакет.
    - запускать пакет прямо с GitHub, без локальной установки (полезно для тестирования проекта)
    - запускать произвольных фрагментов кода, доступных по некоему адресу. Например из GitHub Gis / реопзиториев
    - запускать разные версии одних и тех же утилит, указывая нужную версию с помощью конструкции @version.
    - запускать JavaScript-код с использованием различных версий Node.js. Позволяет отказаться от NVM и его аналогов. Выглядит так: `npx node@6 что-то-там`

  **Ссылки**
  -[hexlet - JS: Настройка окружения. NPX](https://ru.hexlet.io/courses/js-setup-environment/lessons/npx/theory_unit)
  
<br></p>
</details>

[//]: # (NVM)
<details><summary><b>NVM (Node Version Manager)</b></summary><p>

  - Менеджер версий Node.js, управляет версиями node.js и npm
  - Позволяет удобно переключаться между различными версиями Node.js, с его помощью можно, например, установить и попробовать новую версию Node.js, после чего, при необходимости, вернуться на старую. 
  - Полезно когда нужно испытать какой-нибудь код на старой версии Node.js.
  - С появлением NPX уже не так актуален

<br></p>
</details>

[//]: # (ASDF)
<details><summary><b>ASDF</b></summary><p>

  - Универсальный менеджер версий чего угодно. Надстройка над всеми другими менеджерами - nvm, yarn, pyenv, rvm, rustup, gvm...
  - Работает под Linux / MacOS. Windows - только под Windows SL
  - Написан на bash 
  - Удобно, например, когда работаешь с разными языками. Не надо использовать отдельный пакетный менеджер для Phyton, отдельный для JS/Nodejs...
  - Кроме того, через asdf можно управлять версиями различных утилит и сервисов

**Ссылки**
- [ASDF - Official site](https://asdf-vm.com/)
- [Упарвление версиями чего угодно при помощи asdf](https://semakin.dev/2020/05/asdf/)
<br></p>
</details>


**Ссылки**
- [Дока - Что такое Node.js](https://doka.guide/tools/nodejs/)
- [Дока - Системы сборки](https://doka.guide/tools/bundlers/)
- [Дока - Что такое Webpack](https://doka.guide/tools/webpack/#otslezhivanie-izmeneniy-v-proekte)
- [Дока - Виды веб-приложений ](https://doka.guide/js/web-app-types/)
- [Дока - Версии языка, транспайлеры, бандлеры](https://doka.guide/js/language-versions/)


  <br> 
  <br> 

*[Legmo, 2019-2023](https://github.com/Legmo/notes/)*