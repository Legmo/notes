<h1>Подборки вопросов-ответов для собеседования разработчика</h1>

[//]: # (Повторять)
<details><summary><b>Повторять</b></summary><p>

- JS
  - [Повторное введение в JS](https://developer.mozilla.org/ru/docs/Web/JavaScript/A_re-introduction_to_JavaScript)
  - [Замыкания](https://learn.javascript.ru/closure)
  - [Стрелочные функции](https://learn.javascript.ru/arrow-functions-basics)
    и [ещё они же](https://learn.javascript.ru/arrow-functions)
  - [Promise](https://learn.javascript.ru/async)
  - [Ver, Let, Const](https://learn.javascript.ru/var)
  - [Рекурсия](https://learn.javascript.ru/recursion)
    и [ещё](https://code.tutsplus.com/ru/tutorials/understanding-recursion-with-javascript--cms-30346)
  - [Прототипы](https://learn.javascript.ru/prototypes)
  - [Декораторы в JS](https://learn.javascript.ru/call-apply-decorators)
- React
  - [Side-эффекты](/Pages/Programming/Programming.md)
  - [HOC](/Pages/JS/React.md)
  - [Reselect](https://youtu.be/_jyrQh0ZdTA) - библиотека для создания мемоизированных селекторов
- [REST API](/Pages/WebDeveloping/REST.md)
  - методы - out, post, get, delete...
  - Что можно отправлять
  - типа параметров и т.д.
  - Диапазоны http-кодов
- [GraphQL](/Pages/WebDeveloping/GraphQL.md)
- TypeScript
- Jest и тестирование
- [Чистые функции](/Pages/Programming/Programming.md)
- [Термины](/Pages/Programming/Programming.md)
  - инкапсуляция
  - **идемпотентность** - сколько раз не вызовем операцию, всегда получаем тот же результат
  - **детерминированность** - результат однозначно определяется исходными данными.
  - иммутабельность,
  - декоратор,
  - дебаунс,
  - тротлинг,
  - мемоизация - reselect. Используется селектор с мемоизацией. Выполняем вычисления только если в соотв. части
    дерева state произошли изменения.
- [WebSocket](https://learn.javascript.ru/websocket) и [ещё](/Pages/WebDeveloping/Ajax.md) - протокол связи поверх
  TCP. Для обмена данными между браузером и сервером через постоянное соединение.
- [Микросервисная архитектура](/Pages/WebDeveloping/Microservices.md)
- [MVC](/Pages/Programming/Programming.md)
  - Общее
  - Приложение к веб
  - Приложение к React
- [ООП - Основные понятия](/Pages/Programming/Programming.md)
  - Класс
  - Объект
  - Свойства
  - Методы
  - Геттеры/сеттеры
- [ООП - Базовые принципы](/Pages/Programming/Programming.md)
  - **Наследование** - механизм описания новых классов на основе родительского.
  - Абстракция
  - Инкапсуляция - ограничение доступа к данным и возможностям их изменения. Св-во системы, позволяет объединить в
    классе данные и методы для работы с ними.
  - Полиморфизм - возможность работать с несколькими типами так, будто это один и тот же тип. Cв-во системы,
    позволяет использовать объекты с одинаковым интерфейсом, не зная о типе и внутр. стр-ре объекта.
- [ООП - Паттерны. 23 шаблона](/Pages/Programming/Pattern.md)
- [Принципы SOLID](/Pages/Programming/Programming.md)
  - `Single Responsibility Principle` — Принцип единой ответственности
  - `Open-Closed Principle` — Принцип открытости-закрытости
  - `Liskov Substitution Principle` — Принцип подстановки Барбары Лисков
  - `Interface Segregation Principle` — Принцип разделения интерфейса
  - `Dependency Inversion Principle` — Принцип инверсии зависимостей
- [Акронимы принципов программирования](/Pages/Programming/Programming.md)
  - `DRY`,
  - `KISS`,
  - `YAGNI`,
  - `SOLID`
- [GIT](/Pages/_Other/GIT.md)
  - Rebase
  - Squash
  - GIT flow
- [Советы по оптимизации рендеринга web-страниц](/Pages/Programming/Programming.md) (ДОРАБОТАТЬ)
  - JS.
    - не блокировать пользовательский интерфейс
    - эффективно использовать память
    - избегать использования setTimeout() и setInterval() для обновления внешнего вида элементов страниц.
    - переносить длительные вычисления в [`веб-воркеры`](/Pages/WebDeveloping/Browser.md).
    - для изменений в DOM использовать микро-задачи, разбитые на N кадров.
  - Прочее
    - уменьшить сложность CSS селекторов.
    - Уменьшите число элементов, для которых вычисляем стили. Лучше менять стиль N элементов, а не всю стр.
    - Стараться не менять этих свойств: ширина, высота, позиция элемента (геометр. характеристики) — они требуют
      изменения макета.
    - Использовать flexbox вместо старых моделей создания макетов - работает быстрее, дает сильный прирост
      производительности.
    - Избегайте периодического изменение параметров элементов и их последующего считывания. Т.е. меняю стиль элемента (
      например, динамически добавляю CSS-класс), а потом считываю его параметры (вроде offsetHeight или offsetWidth) из
      предыдущего кадра => браузеру надо применить изменения стиля, создать макет и возвратить нужные данные.
  - Избегать анимации свойств элементов, которые вызывают изменение макета страницы (например width и height)


- JS
  - [ ] Event loop, микро и макро tasks
    - [ ] https://learn.javascript.ru/event-loop
    - [ ] https://learn.javascript.ru/microtask-queue
  - [ ] Асинхронность
    - [ ] https://habr.com/ru/post/439620/
    - [ ] https://developer.mozilla.org/ru/docs/Learn/JavaScript/Asynchronous/Introducing
    - [ ] https://github.com/Legmo/notes/blob/master/Pages/JS/JS.md
  - [ ] Асинхронная итерация, цикл for-await-of
    - [ ] https://learn.javascript.ru/async-iterators-generators
    - [ ] https://learn.javascript.ru/async-await
  - [ ] Bind, контекст, this
    - [ ] https://habr.com/ru/company/ruvds/blog/455527/
    - [ ] https://learn.javascript.ru/bind
    - [ ] https://learn.javascript.ru/object-methods
    - [ ] https://learn.javascript.ru/call-apply
    - [ ] https://habr.com/ru/company/ruvds/blog/419371/
  - [ ] [Fetch](https://learn.javascript.ru/network) - метод реализации асинхронных запросов в нативном JS.
    Предоставляетс Fetch API
  - [ ] [Деструктурирующее присваивание](https://learn.javascript.ru/destructuring-assignment)
  - [ ] [Публичные поля классов JS](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Classes/Public_class_fields#публичные_поля_экземпляра)
  - [ ] Веб-воркеры
- React
  - [WebDev - #9 Фрагменты и стили (Fragments & CSS)](https://youtu.be/Z0S4wcyzLZc)[](http://savefrom.net/?url=https%3A%2F%2Fyoutu.be%2FZ0S4wcyzLZc&utm_source=ff&utm_medium=extensions&utm_campaign=link_modifier "Получи прямую ссылку")
  - [IT-Kamasutra - 100](https://youtu.be/0AohM_oOjBc)
  - [ ] Хуки
    - [WebDev - #2 React Hooks A Complete Introduction (Полное введение в Хуки)](https://youtu.be/X6j7Y7tp3_c)[](http://savefrom.net/?url=https%3A%2F%2Fyoutu.be%2FX6j7Y7tp3_c&utm_source=ff&utm_medium=extensions&utm_campaign=link_modifier "Получи прямую ссылку")
    - [WebDev - #3 React 16.8 Hooks RELEASE! (Реакт Хуки. Официальный релиз)](https://youtu.be/19EmLE2mZ1Q)[](http://savefrom.net/?url=https%3A%2F%2Fyoutu.be%2F19EmLE2mZ1Q&utm_source=ff&utm_medium=extensions&utm_campaign=link_modifier "
      Получи прямую ссылку"
    - https://ru.reactjs.org/docs/hooks-state.html
    - https://ru.reactjs.org/docs/hooks-effect.html
    - [Должен ли я использовать connect или хуки для react redux и который имеет лучшую производительность?](https://translated.turbopages.org/proxy_u/en-ru.ru.b0899dbb-62fa5bee-806cf6a7-74722d776562/https/stackoverflow.com/questions/66527982/should-i-use-connect-or-hooks-for-react-redux-and-which-has-better-performance)
    - [От Редакса к хукам?](https://bespoyasov.ru/blog/you-might-not-need-redux-now/)
    - [Стоит ли использовать Redux с React Hooks](https://amorgunov.com/posts/2020-04-12-use-redux-with-react-hooks/)
    - [Смогут ли React-хуки заменить Redux](https://css-live.ru/articles/smogut-li-react-xuki-zamenit-redux.html)
    - [useEffect(fn, []) это не новый componentDidMount()](https://stasonmars.ru/javascript/useeffect-eto-ne-novyi-componentdidmount/)
  - [ ] Методы жизненного цикла
    - [WebDev - #11 Методы жизненного цикла (Lifecycle methods)](https://youtu.be/O8f6aXqpGHw)
    - componentShouldUpdate
  - [ ] Оптимизация React
  - [ ] Современные практики - 2020, 2021, 2022
  - [ ] Классовые компоненты
  - [ ] Ref
  - [ ] [HOC](https://github.com/Legmo/notes/blob/master/Pages/JS/React.md)
  - [ ] Child
  - [ ] Connect и то как он прокидывает props
  - [ ] Render props
  - Читать документацию React (прочесть трижды)
  - [«Запашки» кода React-компонентов ](https://css-live.ru/javascript/zapashki-koda-react-komponentov.html#jsx-returns)
  - https://it-shpora.pp.ua
- TS
  - смотреть видео про TS - https://www.youtube.com/playlist?list=PLNkWIWHIRwMEm1FgiLjHqSky27x5rXvQa
  - прочитать и законспектировать базовые понятия
  - [ ] типы (type)
  - [ ] интерфейсы (interface)
  - [ ] дженерики (generic)
  - [ ] транспиляция
  - [ ] наследование
  - [ ] Основные отличия TS и JS

  +

  - [ ] в JS нет дженериков - что такое генерификация, как она работает
  - [ ] как дженерики транспилируются в JS
  - [ ] как реализовано наследование
  - [ ] как реализована деструктуризация
  - [ ] как реализован event loop
  - [ ] как работает сборщик мусора
  - [ ] 
- JEST
  - https://youtu.be/Kyc_Z_2b2Hc
  - https://youtu.be/Kyc_Z_2b2Hc?t=1653 - как протестить APP
  - https://habr.com/ru/company/timeweb/blog/670480/
  - https://ru.hexlet.io/courses/js-react/lessons/tests/theory_unit
  - https://code.tutsplus.com/ru/articles/testing-components-in-react-using-jest-the-basics--cms-28934
- Парадигмы программирования
  - https://doka.guide/js/programming-paradigms/
  - https://pikabu.ru/story/paradigmyi_programmirovaniya_7584307
  - https://habr.com/ru/post/554474/
- Вёрстка
  - CSS для React - модули
  - CSS для React - CSS in JS
  - CSS для React - прочее
  - [Sass - какие для вас главные преимущества](/Pages/WebDeveloping/HtmlCssQuestions.md)
  - BEM

<br></p>
</details> 

[//]: # (Из личного опыта)
<details><summary><b>Из личного опыта</b></summary><p>

- Замыкания
- Работа JS-движка - Event Loop, стэк, очередь задач, микро/макро задачи, web API... SetInterval/Promises
- Асинхронность и однопоточность JS - что это значит и чем обусловлено.
- **Как JS распределяет память, как парсится и выполняется код.**
- Promises, Async/Await, атрибуты async и defer у тега script
- Передача "по значению" и "по ссылке"
- **Лексическое всплытие**
- **Алгоритмическая сложность**
  - **Теория нормализации данных** (применительно к проектированию Redux state)
  - Работа DOM браузера: "дорогие" операции. Relayout / repaint
  - Работа DOM браузера: "дорогие" операции чтения (get.computer.style и т.д.)
  - Отслеживание изменений в фреймворке — центральный вопрос для современных фреймворков. Как фреймворк понимает, что
    что-то изменилось и необходимо применить новые изменения к DOM?
  - Методы жизненного цикла компонента React - не просто заучить, а понимать с какой целью они были добавлены.
  - Основные понятия React.
  - Устройство Redux (store, createStore, state, reducer, actions, action creators, dispatch, provider, connect,
    middleware, mapDispatchToProps, mapStateToProps)

<br></p>
</details> 

[//]: # (Популярные задачки)
<details><summary><b>Популярные задачки</b></summary><p>

- Замыкания - например использование var/let в for()
- Promise & setTimeout/setInterval - что раньше выполнится? Куча разных console.log, в каком порядке будут выводиться
- Написать свою реализацию функции debounce
- Предложить разные методы организации кэша для вычисления Фибоначчи (кэш ограничен 20 значениями, а поступить может
  хоть 10000 - как оптимизировать? часть кэша выделяем под хранение предыдущиз вычисленных значений. Рекурсия - самый
  дорогой вариант)
- Теория нормализации данных. Применение для проектирования стэйта. Например: в качестве ответа сервера получаем очень
  большой неупорядоченный массив - как с ним работать? Решение: дробление по принципу связи. Точно не помню, надо
  повторять, но вроде идея такая - создаём отдельный массив для одних сущностей (задачи, например) и отдельный для
  других (пользователи) и устанавливаем между ними связи.

<br></p>
</details> 

---

[//]: # (React.js)
<details><summary><b>React.js</b></summary><p>

[Вопросы на собеседовании React.js](https://github.com/likezninjaz/react-ru-interview-questions)

**JavaScript**

- Какие типы данных существуют в JavaScript?
- Что такое цикл событий (event loop) и как он работает?
- Что такое замыкание?
- Что такое прототип объекта в JavaScript?
- Как работает ключевое слово this?
- Как работают методы apply(), call() и bind()?
- Что такое Promise (Промис)?

**React**

- Какие методы жизненного цикла компонента существуют в React?
- Что такое Context в React и для чего он используется?
- Что такое Виртуальная DOM?
- Для чего нужен атрибут key при рендере списков?
- В чем разница между управляемыми (controlled) и не управляемыми (uncontrolled) компонентами?
- Что такое PureComponent?
- Что такое Компонент высшего порядка (Higher-Order Component, HOC)?
- Что такое хуки в React?
- Что такое порталы в React?

<br></p>
</details> 

[//]: # (Козлова О - React.js + Redux)
<details><summary><b>Козлова О - React.js + Redux</b></summary><p>

[Козлова О - React.js + Redux — interview questions](https://medium.com/@olgakozlova/react-js-redux-interview-questions-1-e6d2f12f2d79)

- Зачем вообще нужен реакт?
- Что такое виртуальный DOM?
- Жизненный цикл React компонента?
- Что такое JSX?
- Stateless vs Stateful React компоненты?
- Functional vs Class React компоненты?
- Smart vs Dumb React компоненты?
- Отличия props и state?
- Архитектура Redux

<br></p>
</details> 

[//]: # (Козлова О - JS Массивы)
<details><summary><b>Козлова О - JS. Массивы</b></summary><p>

[Козлова О - JS. Массивы](https://medium.com/@olgakozlova/javascript-interview-questions-part-i-arrays-e996f6433089)

- Какие способы создать массив вы знаете?
- Какие особенности существуют у массивов в JavaScript по сравнению с массивами в других языках программирования — C,
  C#?
- Как можно узнать длину массива?
- Можно ли перезаписать length массива?
- Как можно перебрать все элементы массива?
- Какие методы для работы с массивом как со стеком Вы знаете?
- Что будет в переменной result после исполнения этого кода? (Array.prototype.push.apply(arr, [3, 4]))
- Какие методы для работы с массивом как с очередью Вы знаете?
- Какие методы изменения порядка элементов массива Вы знаете?
- Что будет в переменной result после исполнения этого кода? (array.sort())
- Каким условиям должна удовлетворять функция-comparator передаваемая методу Array.prototype.sort()?
- Как преобразовать массив в строку?
- Метод объединения массивов?
- Метод создания подмассива из массива?
- Метод заполнения элементов массива
- Методы перебора элементов массива
- Методы поиска элементов в массиве
- Методы редукции массивов
- Как проверить, является ли элемент массивом?
- Какой typeof у массива?
- Почему не рекомендуется работать с разнотипными и разреженными массивами?
- Преобразование массивов в другие типы данных

<br></p>
</details> 

[//]: # (Козлова О - JS. Функции])
<details><summary><b>Козлова О - JS. Функции</b></summary><p>

[Козлова О - JS. Функции](https://medium.com/@olgakozlova/javascript-interview-questions-part-ii-functions-5bd513054382)

- Какие способы создать функцию Вы знаете?
- Какие способы вызвать функцию Вы знаете?
- Какую функцию можно вызвать как конструктор?
- Что происходит при вызове функции как конструктора?
- Что будет в каждой переменной?
- Что такое самоопределяемая функция? Приведите пример.
- Как работает bind?
- Что такое немедленно вызываемые функции? Примеры? Применение?
- Что такое стрелочные фунцкии? Каковы их особенности?
- Что такое вложенность функций?
- Как можно работать с функцией как с объектом?
- Как передаются аргументы в функцию? По ссылке или по значению?
- Как получить все аргументы функции, если точное их количество не известно?
- Каковы особенности работы с объектом arguments?
- Что такое замыкания?
- Как можно применять замыкания?
- Какие проблемы могут вызвать замыкания?

<br></p>
</details> 

[//]: # (Вопросы и ответы на собеседовании по React.js)
<details><summary><b>Вопросы и ответы на собеседовании по React.js</b></summary><p>

[Вопросы и ответы на собеседовании по React.js](https://www.interviewhelper.org/ru/question/voprosy-i-otvety-na-sobesedovanii-po-react-js)

- Как заставить компонент React перерендерится?
- Назовите методы жизненного цикла компонента?
- Какие методы компонента могут быть вызваны после некоторых изменений состояния?
- Почему важно использовать key для отображения элементов списка ?
- Как обрабатывать событие нажатия кнопки в React.js ?
- Как передать параметр обработчику события или в callback?
- Что произойдет, если передать функцию в метод setState ?
- Что такое поднятие состояния вверх по иерархии в React (Lifting State Up)?
- Как получить значение input?
- Что такое строгий режим в React.js
- Что такое порталы(Portals)?
- В каком методе жизненного цикла нужно сделать HTTP-запрос ?
- Что такое чистый компонент и когда он должен использоваться ?
- Как сделать условный рендер в React.js?
- Как собрать React приложение в production режиме?
- Где инициализировать состояние компонента?
- Что представляют собой компоненты высшего порядка в React.js (HOC)?
- Кода нужно использовать метод getDerivedStateFromProps(props, state)?
- Что такое PropTypes и как их использовать?
- Что такое stateless компоненты?

<br></p>
</details> 

[//]: # (Вопросы про React на собеседовании)
<details><summary><b>Вопросы про React на собеседовании</b></summary><p>

[Вопросы про React на собеседовании](https://www.kanby.ru/voprosyi-pro-react-na-sobesedovanii.html)

- Что происходит, когда вы вызываете setState?
- Какая разница между Элементом и Компонентом в React?
- Когда вам использовать Class Component вместо Functional Component?
- Что за refs в React и в чем их важность?
- Что за keys в React и чем их важность?
- Если вы создали в React элемент Twitter как в примере ниже, то как бы он выглядел?
- В чем разница между controlled и uncontrolled компонентами?
- В какой момент жизненного цикла вы применяется AJAX запросы и почему?
- Что делает и почему важен shouldComponentUpdate?
- Как вы скажете React строить в режиме Production и как это сделать?
- Опишите, как в React обрабатываются события?
- В чем разница между createElement и cloneElement?
- Какой второй аргумент можно передать опционально в setState и какова его цель?
- Что не так с этим кодом?

<br></p>
</details> 

[//]: # (Топ 15 вопросов о React.JS на собеседовании. Другой перевод)
<details><summary><b>Топ 15 вопросов о React.JS на собеседовании (другой перевод)</b></summary><p>

[Топ 15 вопросов о React.JS на собеседовании (другой перевод)](https://proglib.io/p/react-js-interview/)

- Что делает setState?
- В чем разница между элементом и компонентом React.JS?
- В каких случаях Class Component лучше, чем Functional Component?
- Что такое refs и с чем их едят?
- React key – это…
- Как бы выглядел приведенный ниже элемент Twitter в React?
- Разница между компонентами controlled и uncontrolled
- В каком моменте должны быть AJAX запросы и почему?
- Что за зверь, этот shouldComponentUpdate?
- Поговорим с React.JS: режим Production
- Почему React.Children.map(props.children, () => ), а не props.children.map(() => )?
- Опишите обработку событий в React.JS
- В чем разница между cloneElement и createElement?
- Какой второй аргумент может быть передан в setState?

<br></p>
</details> 

[//]: # (Вопросы на собеседование по React / Redux)
<details><summary><b>Вопросы на собеседование по React / Redux</b></summary><p>

[Вопросы на собеседование по React / Redux](https://webformyself.com/voprosy-na-sobesedovanie-po-react-redux/)

- Что такое React?
- Что такое Виртуальная DOM?
- В чем разница между состоянием и свойством?
- Какие существуют фазы жизненного цикла компонентов React?
- Как работает React?
- Что такое потомки?
- Что такое состояние в React?
- Что такое контролируемые компоненты?
- Что такое Flux?
- Что такое Redux?
- Как изменяется состояние в Redux?
- Что такое «хранилище» в Redux?
- Что такое чистая функция?
- Как бы вы отключили хранилище Redux, чтобы оно не принимало никаких изменений в состоянии?

<br></p>
</details> 

[//]: # (Пацианский М - Вопросы для собеседования JS разработчика)
<details><summary><b>Пацианский М - Вопросы для собеседования JS разработчика</b></summary><p>

[Пацианский М - Вопросы для собеседования javascript разработчика](https://maxpfrontend.ru/vebinary/voprosy-dlya-sobesedovaniya-javascript-razrabotchika/)

**Основы**

- прицнипы ООП (хороший эффект производит знание трех слов: инкапсуляция, наследование, полиморфизм)
- типы данных javascript
- что такое свойство объекта, а что метод
- написать функцию, add, чтобы вызов add(1)(2) вернул 3 (замыкания)
- армия функций
- кофеварка (один раз написать самому, подсматривая в учебник обязательно)
- знать, что объекты передаются по ссылке
- как сделать debounce функцию
- map, filter, reduce
- XMLHttpRequest и как его отменить, современный вариант fetch
- promise

**React**

- Какую проблему решает react?
- Мгновенно ли срабатывает setState? Если нет, то как выполнить код, который 100% выполнится после того, как новый state
  будет установлен
- Зачем многие постоянно пишут в constructor: this.FUNCTION_NAME = this.FUNCTION_NAME.bind(this) и отсюда вопрос
  вытекает чему равно this в разных местах вашего компонента…
- в каких методах жизненного цикла стоит выполнять xhr запросы? В каких стоит «обновлять state на основе props«?
- Что будет если вызвать this.setState в render методе компонента?
- Зачем нужен componenWIllUnmount, приведите пример
- Контролируемые, не контролируемые компоненты
- Как организовать роутинг в реакт приложении?
- Зачем нужны propTypes? Что происходит с ними в production сборке?
- Как можно удобно «отлаживать» чужой код приложения, написанного на react (намек в сторону React devtools)

**Redux**

- Какую проблему решает redux?
- Зачем многие создают типы действий NAME_REQUEST / NAME_SUCCESS ? А заодно, что такое «действие», а что такое
  «создатель действия»…
- Что такое редьюсер? Можете написать простой редьюсер без react/redux?
- Для чего нужен redux-thunk? Как он работает? Напишите (можно псевдокод) асинхронный создатель действия (либо, если
  надоело говорить «терминами» — асинхронный aciton)
- Как компоненты приложения получают «пропсы» из «стора»?
- Можно ли (и считается ли это нормальным) использовать state, если используется Redux?
- Почему в reducer’ax мы возвращаем новые объекты? Приведите пример, когда вы возвращаете новый объект, а когда тот же
  самый.
- Что возвращает функция connect (из react-redux)?

**Общие вопросы (что это и для чего?)**

- package.json
- Webpack, gulp, и т.д.
- node.js
- promise

<br></p>
</details> 

<h3>Ещё</h3>

- [Козлова О - Вопросы из Яндекса](https://medium.com/@olgakozlova/%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B-%D0%B8%D0%B7-%D1%8F%D0%BD%D0%B4%D0%B5%D0%BA%D1%81%D0%B0-895261c94e16)
- [Козлова О - Сети в вопросах и ответах. HTTP-протокол. AJAX. JSONP. CORS.COMET.](https://medium.com/@olgakozlova/%D1%81%D0%B5%D1%82%D0%B8-%D0%B2-%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D0%B0%D1%85-%D0%B8-%D0%BE%D1%82%D0%B2%D0%B5%D1%82%D0%B0%D1%85-http-%D0%BF%D1%80%D0%BE%D1%82%D0%BE%D0%BA%D0%BE%D0%BB-ajax-jsonp-cors-comet-53c60319a5a7)
- [CSSSR - «И так сойдёт!» или главные ошибки кандидатов](http://blog.csssr.ru/2018/08/16/candidates-mistakes)
- [Кожанова М («Нетология») - Что спрашивают у начинающего разработчика JavaScript на собеседованиях и в тестовых заданиях](https://habr.com/ru/company/netologyru/blog/667520/)
- [github.com/learning-zone — React Interview Questions (en)](https://github.com/learning-zone/react-interview-questions)
- [Агапов Е - Вопросы по React для подготовки к собеседованию. Old. Версия 1 (322 вопроса, 2021 год)](https://github.com/harryheman/my-js/blob/master/docs/other/js-questions.md)
- [Агапов Е - Вопросы по React для подготовки к собеседованию. Old. Версия 2 (180 вопросов, 2021 год)](https://github.com/harryheman/my-js/blob/master/docs/other/js-questions2.md)
- [Агапов Е - Вопросы по React для подготовки к собеседованию. New. Версия 1](https://github.com/harryheman/my-js/blob/master/docs/other/js-questions.md)
- [Агапов Е - Вопросы по React для подготовки к собеседованию. New. Версия 2](https://github.com/harryheman/my-js/blob/master/docs/other/js-questions2.md)


<br>
<br>

*[Legmo, 2019-2022](https://github.com/Legmo/notes/)*