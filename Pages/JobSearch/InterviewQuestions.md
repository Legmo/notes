<h1>Подборки вопросов-ответов для собеседования разработчика</h1>

[//]: # (Повторять)
<details><summary><b>Повторять</b></summary><p>

***

[//]: # (JS)
<details><summary><b>JS</b></summary><p>

- [Повторное введение в JS](https://developer.mozilla.org/ru/docs/Web/JavaScript/A_re-introduction_to_JavaScript)
- [Legmo - JS](../JS/JS.md)
-
- [Что нового в последних 3 версиях JS](../JS/JS.md)
- [Работа JS-движка](../JS/JS.md)
  - Event Loop,
  - стэк,
  - очередь задач,
  - микро/макро задачи,
  - веб-воркеры,
  - SetInterval
  - Promises,
  - web API...
  - Асинхронность и однопоточность JS - что это значит и чем обусловлено.
  - В каком порядке будут выводиться console.log, Promise
- [Сборщик мусора](https://learn.javascript.ru/garbage-collection)
-
- [Use strict](https://learn.javascript.ru/strict-mode)
- [Атрибуты async и defer у тега script](https://learn.javascript.ru/script-async-defer)
- [Function Declaration / Function Expression](https://learn.javascript.ru/function-expressions) (`function sayHi(){}`
  / `let sayHi = function(){}`)
- [Замыкания](https://learn.javascript.ru/closure)
- [Стрелочные функции](https://learn.javascript.ru/arrow-functions-basics)
  и [ещё они же](https://learn.javascript.ru/arrow-functions)
- Ключевое слово this
  - https://learn.javascript.ru/object-methods
  - https://learn.javascript.ru/arrow-functions
  - [Habr - Что записано в this? Закулисье JavaScript-объектов](https://habr.com/ru/company/ruvds/blog/455527/)
  - [Habr - Ключевое слово this в JavaScript для начинающих](https://habr.com/ru/company/ruvds/blog/419371/)
- [Метод bind()](https://learn.javascript.ru/bind)
- [Методы apply() и call()](https://learn.javascript.ru/call-apply-decorators)
- [Лексическое всплытие](https://learn.javascript.ru/bubbling-and-capturing)
- Контекст выполнения
  - [Habr - Контекст выполнения и стек вызовов в JavaScript](https://habr.com/ru/company/ruvds/blog/422089/)
- [Рекурсия](https://learn.javascript.ru/recursion)
  и [ещё](https://code.tutsplus.com/ru/tutorials/understanding-recursion-with-javascript--cms-30346)
- [Promise, Async/Await](https://learn.javascript.ru/async)
- [Fetch](https://learn.javascript.ru/network) - метод реализации асинхронных запросов в нативном JS. Предоставляется
  Fetch API
- [XMLHttpRequest](https://learn.javascript.ru/xmlhttprequest) (Его современный аналог — fetch)
- Стуркутры [Map и Set](https://learn.javascript.ru/map-set)
  , [WeakMap и WeakSet](https://learn.javascript.ru/weakmap-weakset)
-
- [Ver, Let, Const](https://learn.javascript.ru/var)
- Типы в JS (string, number, object...)
- [Приведение типов](https://doka.guide/js/typecasting/#preobrazovanie-tipov)
- Что является объектом в JS?
- Различия Undefined и Null
- Передача по значению / по ссылке
- Методы примитивов
  - [Общие вопросы](https://learn.javascript.ru/primitives-methods)
  - [String](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/String#methods)
  - [Number](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Number#methods)
  - [BigInt](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/BigInt#%D1%81%D1%82%D0%B0%D1%82%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%B8%D0%B5_%D0%BC%D0%B5%D1%82%D0%BE%D0%B4%D1%8B)
  - [Boolean](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Boolean#methods)
  - [Symbol](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Symbol)
- Методы объектов
  - keys() - возвращает ключи объекта.
  - values() - возвращает значения объекта.
  - create() - создать новый объект из существующего.
  - freeze() - «замораживает» объект. Предотваращает изменения свойств и т.д.
  - seal() - предотвращает добавление новых свойств, но позволяет изменять существующие.
  - assign() - копирование свойств объекта в другой объект.
  - entries() - создает вложенный массив пар «ключ-значение» объекта
  - getPrototypeOf() - получения внутреннего скрытого [[Prototype]] объекта, также доступного через свойство __proto__
    .
  - ... там ещё много. Изучать
  - что-то добавили в последние несколько лет
  -
  - [Некоторые методы объектов](https://techrocks.ru/2021/10/27/40-javascript-methods-you-should-know/#object)
  - [Habr - Работа с объектами в JavaScript: теория и практика](https://habr.com/ru/post/48542/)
- Методы массивов
  - push(...items) – добавляет элементы в конец,
  - pop() – извлекает элемент из конца,
  - shift() – извлекает элемент из начала,
  - unshift(...items) – добавляет элементы в начало.
  - [splice](https://learn.javascript.ru/array-methods#splice) - добавлять, удалять и заменять элементы.
  - [slice](https://learn.javascript.ru/array-methods#slice) - создаёт новый массив и копирует в него нужные эл-ты
  - [concat](https://learn.javascript.ru/array-methods#concat) - создаёт новый массив и копирует в него данные из
    старых
  - [forEach](https://learn.javascript.ru/array-methods#perebor-foreach) - перебор
  - [indexOf/lastIndexOf и includes](https://learn.javascript.ru/array-methods#indexof-lastindexof-i-includes) - поиск
    в массиве
  - [find и findIndex](https://learn.javascript.ru/array-methods#find-i-findindex) - поиск
  - [filter](https://learn.javascript.ru/array-methods#filter) - поиск
  - [map](https://learn.javascript.ru/array-methods#map) - преобразование
  - [sort(fn)](https://learn.javascript.ru/array-methods#sort-fn) - сортировка «на месте»
  - [reverse](https://learn.javascript.ru/array-methods#reverse) - смена порядка элементов на обратный
  - [split и join](https://learn.javascript.ru/array-methods#split-i-join) - разбивка/объединение
  - [reduce/reduceRight]()
  - [Array.isArray](https://learn.javascript.ru/array-methods#array-isarray) - отличить массив от объекта
  -
  - НОВЫЕ
  - `findLast()` и `findLastIndex()` — поиск в массивах «с конца
  - `at()` — обращаться к массивам с конца. И строкам тоже
  - `flat()` и `flatMap()` — рекурсивно сгладить массивы до заданной глубины и вернуть новый массив. Т.е. многомерный
    массив сделать одномерным.
  -
  - [ШПАРГАЛКА](https://learn.javascript.ru/array-methods#itogo)
  - [Habr - 15 методов работы с массивами в JavaScript, которые необходимо знать в 2020 году](https://habr.com/ru/company/plarium/blog/483958/)
  -
  - Чаще всего спрашивают
    - Метод [map](https://learn.javascript.ru/array-methods#map) - преобразование
    - Метод [filter](https://learn.javascript.ru/array-methods#filter)
    - Метод [reduce](https://learn.javascript.ru/array-methods#reduce-reduceright)
- Мутирующие / не мутирующие методы (особенной у массивов)
-
- [Асинхронная итерация](https://learn.javascript.ru/async-iterators-generators)
- [Оператор нулевого слияния (??)](https://learn.javascript.ru/nullish-coalescing-operator)
- [Логические операторы присваивания(`&&=`, `||=`, `??=`)]()
- [Опциональная цепочка `?.`](https://learn.javascript.ru/optional-chaining)
- [Деструктурирующее присваивание](https://learn.javascript.ru/destructuring-assignment)
- [Остаточные параметры и оператор расширения / spread (...)](https://learn.javascript.ru/rest-parameters-spread-operator)
- [Параметры функции по умолчанию](https://tproger.ru/translations/javascript-cheatsheet/#fnctdefparam)
- [Шаблонные строки (шаблонные литералы). Теговые шаблоны](https://tproger.ru/translations/javascript-cheatsheet/#tmpltltrls)
- [Цикл for-await-of](https://learn.javascript.ru/async-await)
- [Декораторы](https://learn.javascript.ru/call-apply-decorators)
- [Прототипы](https://learn.javascript.ru/prototypes)
- Классы
  - [Базовые вопросы](https://learn.javascript.ru/classes)
  - [Ключевые слова extends и super](https://tproger.ru/translations/javascript-cheatsheet/#extendsuperkwrds)
  - [Публичные поля классов](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Classes/Public_class_fields#публичные_поля_экземпляра)
  - ...
- Как профилировать и отлаживать js (кроме console.log)
- Нативный JS: как обратиться к элементам DOM-страницы? А к конкретному? А по тегам?
-

<br></p>
</details> 

[//]: # (React)
<details><summary><b>React</b></summary><p>

- [Legmo - React](/Pages/JS/React.md)
-
- Как работает React
  - [Habr - Как работает React: подробное руководство](https://habr.com/ru/company/timeweb/blog/586972/)
  - [Habr - Как работает React: подробное руководство](https://habr.com/ru/company/timeweb/blog/586972/)
  - [habr - Объясняем современный JavaScript динозавру](https://habr.com/ru/company/mailru/blog/340922/)
  - [csssr - Основы производительности React-приложений](https://blog.csssr.ru/2016/12/07/react-perfomance)
- Как в React обрабатываются события?
- Virtual DOM
  - [Medium - Как работает Virtual DOM ?](https://medium.com/@abraztsov/how-virtual-dom-work-567128ed77e9)
  - [Habr - Немного о том, как работает виртуальный DOM в React](https://habr.com/ru/company/macloud/blog/558682/)
  - [Оф. документация - Виртуальный DOM и детали его реализации в React](https://ru.reactjs.org/docs/faq-internals.html)
  - [Как работает Virtual DOM ?](https://medium.com/@abraztsov/how-virtual-dom-work-567128ed77e9)
  - [csssr - Основы производительности React-приложений](https://blog.csssr.ru/2016/12/07/react-perfomance)
  - [React и SEO: преимущества изоморфности React для одностраничных приложений](https://xbsoftware.ru/blog/react-seo-izomorphnost-react-odnostrannoe-prilozhenie/)
  - [learnjavascript - про обычный DOM](https://learn.javascript.ru/browser-environment)
  - [Medium - Как работает Virtual DOM?](https://medium.com/@abraztsov/how-virtual-dom-work-567128ed77e9)
  - [Habr - Немного о том, как работает виртуальный DOM в React](https://habr.com/ru/company/macloud/blog/558682/)
  - [IT-Kamasutra #86 - Virtual DOM](https://youtu.be/rsW9_UtF4jk)
- Классовые и функциональные компоненты.
- Компоненты с состоянием и stateless
- Контролируемы и не контролируемые компоненты (controlled/uncontrolled)
- Context
- Хуки
  - [Legmo - Хуки](/Pages/JS/React.md)
  - Хук useState - [reactjs.org](https://ru.reactjs.org/docs/hooks-state.html)
  - Хук useEffect - [reactjs.org](https://ru.reactjs.org/docs/hooks-effect.html)
  - [Habr - React hooks, как не выстрелить себе в ноги. Часть 1: useState](https://habr.com/ru/company/otus/blog/667706/)
  - [Habr - React hooks, как не выстрелить себе в ноги. Часть 2: useEffect и useLayoutEffect](https://habr.com/ru/company/otus/blog/668700/)
  - [Habr - React hooks, как не выстрелить себе в ноги. Часть 3.1: useMemo](https://habr.com/ru/company/otus/blog/669962/)
- [Side-эффекты](/Pages/Programming/Programming.md)
- [HOC](/Pages/JS/React.md)
- [Reselect (YouTube)](https://youtu.be/_jyrQh0ZdTA) - библиотека для создания мемоизированных селекторов
- [WebDev - #9 Фрагменты и стили (Fragments & CSS) (YouTube)](https://youtu.be/Z0S4wcyzLZc)[](http://savefrom.net/?url=https%3A%2F%2Fyoutu.be%2FZ0S4wcyzLZc&utm_source=ff&utm_medium=extensions&utm_campaign=link_modifier "Получи прямую ссылку")
- [IT-Kamasutra - 100 (YouTube)](https://youtu.be/0AohM_oOjBc)
- Методы жизненного цикла
  - какие есть, зачем добавлены, как работают
  - componentShouldUpdate
  - [WebDev - #11 Методы жизненного цикла (Lifecycle methods) (YouTube)](https://youtu.be/O8f6aXqpGHw)
- Ref - [Legmo notes](https://github.com/Legmo/notes/blob/master/Pages/JS/React.md)
- HOC - [Legmo notes](https://github.com/Legmo/notes/blob/master/Pages/JS/React.md)
- Connect и то как он прокидывает props
- Порталы в React - [Оф. документация](https://ru.reactjs.org/docs/portals.html)
- Строгий режим в React.js - [Оф. документация](https://ru.reactjs.org/docs/strict-mode.html)
- Как сделать условный рендер в React.js
  - [7 способов реализации условного рендеринга в React](https://russianblogs.com/article/8615661123/)
  - [Оф. документация](https://ru.react.js.org/docs/conditional-rendering.html)
- Метод getDerivedStateFromProps(props, state)
  - [Оф. документация](https://ru.react.js.org/docs/react-component.html?#static-getderivedstatefromprops).
  - Срабатывает перед каждым рендером/ререндером. Для редких случаев когда состояние зависит от изменений в свойствах со
    временем.
- Разница между createElement и cloneElement
  - [Оф. документация - createElement](https://ru.reactjs.org/docs/react-api.html#createelement)
  - [Оф. документация - cloneElement](https://ru.reactjs.org/docs/react-api.html#cloneelement)
  - [stackoverflow.com - React createElement vs cloneElement](https://stackoverflow.com/questions/35616029/react-createelement-vs-cloneelement)
- [WebDev - #9 Фрагменты и стили (Fragments & CSS)](https://youtu.be/Z0S4wcyzLZc)
- [WebDev - #11 Методы жизненного цикла (Lifecycle methods)](https://youtu.be/O8f6aXqpGHw)
- HOC - [Legmo notes]](https://github.com/Legmo/notes/blob/master/Pages/JS/React.md)
- Child
  - Что такое потомки?
  - [Погружаемся в работу с children на React (2020)](https://stasonmars.ru/javascript/pogruzhaemsya-v-raboty-s-children-na-react/)
  - [Оф. документация](https://ru.reactjs.org/docs/react-api.html#reactchildrenmap)
- Render props
  - [Оф. документация](https://ru.reactjs.org/docs/render-props.html)
  - [Разбираемся с Render Props на примере](https://habr.com/ru/post/418863/)
- React DevTools - [статья на Habr (2021)](https://habr.com/ru/post/595607/)
- React Reconciliation - [Статья](https://kramarenko.com.ua/post/what_is_reconciliation)
- Современные практики - 2020, 2021, 2022
  - Статья про [лучшие практики React 2021](https://habr.com/ru/company/otus/blog/546534/)
- Оптимизация React
  - Как уменьшить количество ререндера компонентов?
  - [«Запашки» кода React-компонентов ](https://css-live.ru/javascript/zapashki-koda-react-komponentov.html#jsx-returns)
  - [csssr - Основы производительности React-приложений](https://blog.csssr.ru/2016/12/07/react-perfomance)
- Вёрстка для React
  - CSS модули
  - CSS in JS
  - Styled components
  - BEM
  - [Sass - какие для вас главные преимущества](/Pages/WebDeveloping/HtmlCssQuestions.md)
- Источники
  - [Оф. документация React](https://ru.reactjs.org/docs/hello-world.html) (прочесть трижды)
  - [Legmo - React](/Pages/JS/React.md)
  - https://it-shpora.pp.ua

<br></p>
</details> 

[//]: # (Redux)
<details><summary><b>Redux</b></summary><p>

- [Legmo - Redux](/Pages/JS/Redux.md)
- Что такое Redux?
- Зачем нужен?
- Flux-архитектура
- Нормализация данных применительно к проектированию Redux state
- `State` (состояние) — объект хранящий актуальное состояние системы.
- `Store` (хранилище) — объект, хранящий `state` и методы для работы с ним.
- `Dispatch` (отправка) — один из методов `store`. Объединяет все методы для правки `state`.
- `Actions` — объекты которые мы из UI (React) передаем в метод `dispatch()`.
- `Type` и `Payload` — параметры объекта `action`
- `ActionCreators()` — функции, создают объект `Action`. Принимают данные-payload нужные для правки `state`, и
  возвращают объект `action` (с нужным type и payload).
- `Reducers()` — функции внутри `dispatch()`. Отвечают за правку опр. части `state`. Принимают `action` и `state`,
  возвращают новый `state`
- `Thunk()` — функция, делает какой-то асинхронный код и умеет  `dispatch(actions)` . Нужна для асинхронных запросов.
- `ThunkCreator()` — функция-обёртка `thunk()`. Нужна чтоб передать в `thunk()` данные-payload для правки `state` .
- `Saga()` — альтернатива `thunk`. Тоже библиотека. Сложнее, более продвинутая
- `Middleware()` — функция-обёртка `dispatch()`. Нужна чтоб выполнить асинхронный код между отправкой из UI
  и `dispatch()`
- `Selectors` - Функция, принимает весь стэйт целиком, достаёт и обрабатывает какие-то данные и передаёт их
  в `mapStateToPros` (и дальше в UI). Архитектурный слой, занимается получением, комбинированием и преобразованием
  данных.
- `Reselect` - библиотека для оптимизации работы селекторов
- `React-Redux` - что это, зачем?
- `Redux Toolkit` - что это, зачем?
- `Connect` - API react-redux, для создания компонентов-контейнеров, которые подключены к хранилищу Redux.
- `mapStateToProps`
- `mapDispatchToProps`
- `Provider` - компонент из react-redux, оборачивается вокруг корневой компоненты (<App>). Позволяет передавать store
  всем потомкам - теперь у connect() есть доступ к store
- `Compose` - функция, предоставляется Redux. Объединить несколько последовательных вызовов функций. Полезно в ситуации
  конвейера.
- `Быстродействие и оптимизация Redux`
- `AJAX и асинхронные операции`  - варианты реализации
  - Запрос внутри actionCreator
  - Middlewares
  - Redux-thunk
  - Redux saga
  - Хуки
-
- ReactRedux
- ReactRedux Toolkit - возможности
- Connect и то как он прокидывает props
- Как бы вы отключили хранилище Redux, чтобы оно не принимало никаких изменений в состоянии?

<br></p>
</details> 

[//]: # (TypeScript)
<details><summary><b>TypeScript</b></summary><p>

- [Legmo - TypeScript](/Pages/JS/TypeScript.md) (ДОРАБОТАТЬ)
- Основные отличия TS и JS
- Транспиляция
- Утиная типизация
- Типы
- Объекты
- Массивы
- Кортежи
- Enum
- Классы
- Наследование (реализовано на классах)
- Пространства имён, модули, barrel-файлы
- Интерфейсы
- ! Дженерики. **Что такое генерификация? Как она работает? Как дженерики транспилируются в JS?**
- ! Декораторы - классов, свойств, методов, аксессоров (геттеров/сеттеров). Фабрика декораторов
- Типизация функций
- Утилиты (Utility Types)
- ! Деструктуризация - как реализована
- ! Event loop - как реализован
- ! Сборщик мусора - как

<br></p>
</details> 

[//]: # (ООП)
<details><summary><b>ООП</b></summary><p>

- [ООП - Основные понятия](/Pages/Programming/Programming.md)
  - Класс
  - Объект
  - Свойства
  - Методы
  - Геттеры/сеттеры
- [ООП - Базовые принципы](/Pages/Programming/Programming.md)
  - хороший эффект производит знание трех слов: инкапсуляция, наследование, полиморфизм
  - **Наследование** - механизм описания новых классов на основе родительского.
  - Абстракция
  - Инкапсуляция - ограничение доступа к данным и возможностям их изменения. Св-во системы, позволяет объединить в
    классе данные и методы для работы с ними.
  - Полиморфизм - возможность работать с несколькими типами так, будто это один и тот же тип. Cв-во системы,
    позволяет использовать объекты с одинаковым интерфейсом, не зная о типе и внутр. стр-ре объекта.
- [ООП - Паттерны. 23 шаблона](/Pages/Programming/Pattern.md)
- [ООП - Принципы SOLID](/Pages/Programming/Programming.md)
  - `Single Responsibility Principle` — Принцип единой ответственности
  - `Open-Closed Principle` — Принцип открытости-закрытости
  - `Liskov Substitution Principle` — Принцип подстановки Барбары Лисков
  - `Interface Segregation Principle` — Принцип разделения интерфейса
  - `Dependency Inversion Principle` — Принцип инверсии зависимостей

<br></p>
</details> 

[//]: # (Тестирование)
<details><summary><b>Тестирование</b></summary><p>

- [Legmo - Тестирование](/Pages/Programming/Testing.md)
- Зачем вообще тестировать?
- TDD / BDD
- Jest - среда запуска тестов JavaScript, фреймворк
- React Testing Library - библиотека для тестирования React.
- Enzime - библиотека для тестирования React.
- Unit-тестирование
- Snapshot тестирование
- Компонентное/Модульное тестирование
- Тест на «запах дыма»
- Интеграционный тест
- Функциональный тест
- Сквозное тестирование
- Приемочный тест
- Тест производительности
-

<br></p>
</details> 

[//]: # (Оптимизации web-страниц)
<details><summary><b>Оптимизации web-страниц</b></summary><p>

- [Legmo - Оптимизации web-страниц](/Pages/Programming/Programming.md) (ДОРАБОТАТЬ)
- JS - эффективно использовать память
- JS - избегать использования setTimeout() и setInterval() для обновления внешнего вида элементов страниц.
- JS - переносить длительные вычисления в [`веб-воркеры`](/Pages/WebDeveloping/Browser.md).
- JS - для изменений в DOM использовать микро-задачи, разбитые на N кадров.
- CSS - уменьшить сложность CSS селекторов.
- CSS - Уменьшите число элементов, для которых вычисляем стили. Лучше менять стиль N элементов, а не всю стр.
- Стараться не менять этих свойств: ширина, высота, позиция элемента (геометр. характеристики) — они требуют
  изменения макета.
- Использовать flexbox - эта модель создания макета работает быстрее
- Избегайте периодического изменение параметров элементов и их последующего считывания. Т.е. меняю стиль элемента (
  например, динамически добавляю CSS-класс), а потом считываю его параметры (вроде offsetHeight или offsetWidth) из
  предыдущего кадра => браузеру надо применить изменения стиля, создать макет и возвратить нужные данные.
- Избегать анимации свойств элементов, которые вменяют макета страницы (например width и height)

+

- в первую очередь загружать критические запросы (html,css, шрифты...). Т.е. управлять приоритетом загрузки
  статического контента. Например через `<link rel="preload">`
- Использование CSS-спрайтов
- Уменьшите количество HTTP-запросов. Используйте поддомены для параллельного скачивания
- Оптимизация изображений - формат, размер, вектор, CSS-графика...
- Оптимизировать количество шрифтов
- JS - избегать лишних зависимостей
- Используйте CDN для загрузки популярных JavaScript библиотек
- минимизация CSS & JS
- Разделение кода (code splitting) - ленивая загрузка, динамический импорт... Подгружать не самые важные вещи только
  когда они понадобятся
- кэширование - на стороне сервера, на стороне клиента ( HTTP-заголовок Expires )

<br></p>
</details> 

[//]: # (Оптимизация работы браузера)
<details><summary><b>Оптимизация работы браузера</b></summary><p>

- [Legmo - Browser. Оптимизация работы браузера](../WebDeveloping/Browser.md)
- "Дорогие" операции работы с DOM. `Relayout` / `Repaint`
- "Дорогие" операции чтения (getComputedStyle() и т.д.)
- Схема работы:
  - Получение ресурсов (`Fetching`)
  - Парсинг (`Parsing`)
  - Построение `DOM` (Document Object Model)
  - Построение `CSSOM` (CSS Object Model). Блокирует выполнение JS
  - Встретились блокирующие элементы (скрипты и т.д.) - приостановка обработки до их загрузки.
  - `Render Tree` - объединяет DOM и CSSOM в общее дерево рендеринга. Туда попадают только видимые элементы.
  - `Layout` - вычисление позиции и размеров элементов. Последующие повторные операции можно называть `Reflow`.
    - в основном потоке браузера — там же где исполняется JS. Тяжелый JS-код блокирует Reflow => нет интерактивности
      страницы.
    - `Глобальный Layout` — просчёт всего дерева
    - `Инкрементальный Layout` — просчёт только части дерева.
  - `Paint` - отрисовка. Последующие повторные операции - `Repaint` .
  - Композитинг (`Compositing`) — разделение содержимого стр. на «слои», которые браузер будет перерисовывать.
    - Происходит в отдельном потоке — вычисления в JS никак не влияют на него
  - `Reflow` (`Relayout`, `Layout`) и `Repaint` - перестановка и перерисовка

**Рекомендации по оптимизации**

- Обращаться к DOM как можно реже.
  - Если обратился — сохрани элемент в переменной, чтоб не искать повторно
- Минимизируйте перерисовку (`Repaint`) и перестановку (`Reflow`).
  - Изменения компоновки и геометрии, требуют Reflow и Repaint:
    - Добавляются или удаляются визуальные элементы DOM
    - Элемент меняет положение
    - Элементы меняют размер (из-за полей, отступов, толщины границы, ширины, высоты и т. Д.)
    - Изменения содержимого, например, изменения текста или изображения заменены на другой размер
    - Отрисовка начальной страницы
    - Размер окна браузера изменен
  - Объединить несколько изменений DOM и изменений стиля в один пакет и применить их все сразу.
- Минимизировать количество запросов информации о макете:
  - `offset`: offsetTop, offsetLeft, offsetWidth, offsetHeight
  - `scroll`: scrollTop, scrollLeft, scrollWidth, scrollHeight
  - `client`: clientTop, clientLeft, clientWidth, clientHeight
  - `getComputedStyle()`
  - В процессе смены стиля лучше не использовать ни один из вышеперечисленных атрибутов.
  - Если запросил — назначь ее локальной переменной, и потом бери оттуда.
  - Иначе нарушается внутренняя оптимизация — очередь `Reflow`
- Уменьшить количество `агентов событий`
  - Когда на странице много элементов, и каждый из них привязан к одному или нескольким событиям (например, `onclick`)

<br></p>
</details> 

[//]: # (Работа браузера и смежные вопросы)
<details><summary><b>Работа браузера и смежные вопросы</b></summary><p>

- [Legmo - Browser](../WebDeveloping/Browser.md)
- WebAssembly
- Web Worker API, веб воркеры - отдельные потоки браузера, для вычислений JS без блокировки event loop
- Service Worker API
- Веб push-уведомления (Push API и Notifications API)
- MutationObserver API - отслеживание изменений в DOM
- WebSocket
- SSE API (Server-Sent events)
- WebRTC и механизмы P2P-коммуникаций
- Shadow DOM
- Web-компоненты, пользовательские элементы (Custom Elements)
- Системы хранения данных (LocalStorage, SessionStorage, Cookie...)

<br></p>
</details> 

[//]: # (Интернет-технологии - AJAX, JSON, CORS и т.д.)
<details><summary><b>Интернет-технологии - AJAX, JSON, CORS и т.д.</b></summary><p>

- [Legmo - Browser](../WebDeveloping/Technologies.md)
- Порт
- TCP/IP
- HTTP
- HTTP/2
- HTTPS
- JSON (Javascript Object Notation)
- AJAX (Asynchronous JavaScript and XML)
- DHTML (Dynamic HTML)
- JSONP (JSON with Padding - JSON с набивкой)
- JSONPP (Parameterized JSON with padding — параметризованный JSONP)
- CORS
- COMET
- WebSocket - [learnjs](https://learn.javascript.ru/websocket) - протокол связи поверх TCP. Обмен данными браузер-сервер
  через постоянное соединение.
- SSE API (Server-Sent events)
- Server Push
- XMLHttpRequest (XHR)
- Fetch
- Документация API при помощи RAML

<br></p>
</details> 

**Прочие вопросы**

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
- [GIT](/Pages/_Other/GIT.md)
  - Rebase
  - Squash
  - GIT flow
- [REST API](/Pages/WebDeveloping/REST.md)
  - методы - out, post, get, delete...
  - Что можно отправлять
  - типа параметров и т.д.
  - Диапазоны http-кодов
- [GraphQL](/Pages/WebDeveloping/GraphQL.md)
- [MVC](/Pages/Programming/Programming.md)
  - Общее
  - Приложение к веб
  - Приложение к React
- [Акронимы принципов программирования](/Pages/Programming/Programming.md)
  - `DRY`,
  - `KISS`,
  - `YAGNI`,
  - `SOLID`
- [Парадигмы программирования](/Pages/Programming/Programming.md)
- Алгоритмы
  - читать в целом
  - [Алгоритмическая сложность](https://tproger.ru/translations/algorithms-and-data-structures)
  - [Сортировки. Пузырьковая сортировка/фильтрация](https://tproger.ru/translations/sorting-for-beginners)
  - [Бинарное дерево](https://tproger.ru/translations/binary-search-tree-for-beginners)
- [Микросервисная архитектура](/Pages/WebDeveloping/Microservices.md)
- [СI/CD - Continuous Integration, Continuous Delivery, Continuous Deployment](/Pages/Programming/CI-CD.md)
- Отслеживание изменений в фреймворке - как он понимает, что нечто изменилось и надо применить изменения к DOM?
  - [Medium - Как создать реактивный фреймворк на JavaScript](https://medium.com/@monochromer/%D0%BA%D0%B0%D0%BA-%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D1%82%D1%8C-%D1%80%D0%B5%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%BD%D1%8B%D0%B9-%D1%84%D1%80%D0%B5%D0%B9%D0%BC%D0%B2%D0%BE%D1%80%D0%BA-%D0%BD%D0%B0-javascript-cfa34c63fd52)
  - [MutationObserver](../WebDeveloping/Browser.md) и [ещё](https://learn.javascript.ru/mutation-observer) - API
    браузера. Спец. объект, наблюдает за DOM-элементом, запускает колбэк в случае изменений.
- Что такое CORS - [Habr](https://habr.com/ru/company/macloud/blog/553826/)
- Css селекторы - [MDN](https://developer.mozilla.org/ru/docs/Web/CSS/CSS_Selectors)

<br></p>
</details> 

[//]: # (Из личного опыта)
<details><summary><b>Из личного опыта</b></summary><p>

- Замыкания
- Работа JS-движка - Event Loop, стэк, очередь задач, микро/макро задачи, веб-воркеры, SetInterval/Promises, web API...
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

- **ГК «Самолёт», React-frontend middle+** (август 2022)
  - Общее
    - что такое прогрессивный рендеринг, гидратация
    - как искать ошибки (console.log, debugger, точки останова)
    - какие JS/React библиотеки использую
  - CSS
    - методы позиционирования
    - семантическая вёрстка
  - JS
    - загрузка скриптов — обычная, async и defer
    - замыкания
    - event loop, микро-макро таск
    - Отличия Cookie, LocalStorage, sessionStorage — https://learn.javascript.ru/localstorage
  - React
    - что это такое
    - различия функциональных/классовых компонент
    - хуки
      - какие есть
      - как имитировать методы жизненного цикла
      - useState
      - useEffect, что даёт return
      - useMemo / useCallback (что вернёт)
    - отличия ReactRouter и ReactRouterDOM
  - Задачки
    - в каком порядке выведутся `console.log`
      - обычный 1, setInterval, промис, then. обычный 2 => `1, 2, Promise, then, setInterval`
      - [Legmo - JS. Разделы «Работа движка JS», «Асинхронность»]
    - числа Фибоначчи
      - решение через рекурсию
      - решение через цикл for
      - [learn.javascript.ru - Задачка «Числа Фибоначчи» с решением](https://learn.javascript.ru/task/fibonacci-numbers)

- **«CryptoRocks», React-frontend middle** (сентябрь 2022)
  - Что такое VirtualDOM
  - Какие есть методы жизненного цикла
  - Какие стэйт-менеджменты использовал
  - Есть два react-компонента на разном уровне вложенности (меню в шапке и форма в боковой колонке). В форме что-то
    поменялось, надо прокинуть в шапку - какие есть варианты
    - Flux (Redux)
    - подъем пропсов до общего родителя
    - отслеживать изменения в DOM (совсем плохой вариант)
    - есть ещё какие-то варианты. Что-то про observer, библиотека RxJS
  - TypeScript
  - Задачки
    - есть линейный график из множества точек, предложить алгоритм его построения. На локальных максимумах цвет меняется
      на более темный
    - сортировка - отсортировать исходный массив положительных и отрицательных чисел по их квадратам. Использовать
      алгоритм не требующий много памяти

<br></p>
</details> 

[//]: # (Популярные задачки)
<details><summary><b>Популярные задачки</b></summary><p>

- Замыкания - например использование var/let в for()
- Замыкания - написать функцию, add, чтобы вызов add(1)(2) вернул 3
  - ```js
    //Стерлочная
    const add = x => y => {
      const z = x + y;
      console.log(x + '+' + y + '=' + z);
      return z;
    };
    const res = add(3)(6); // вернёт 9 и выведет в консоль 3+6=9
    console.log(res);
    ```
  - ```js
    //Обычная
    function fA() {
      var currentCount = 1;
      function fB() { 
        return currentCount++;
      };
      return fB;
    }
    var counter1 = fA();     
    console.log(counter1()); // 1
    console.log(counter1()); // 2
    console.log(counter1()); // 3

    // создаём другой счётчик, он будет независим от первого
    var counter2 = fA();
    console.log(counter2()); // 1
    ```
- Замыкания, this - написать декратор для кэширования
  - [learn.javascript.ru - Декораторы и переадресация вызова, call/apply](https://learn.javascript.ru/call-apply-decorators)
  - ```js
    let worker = {
      //Вариант 1 -  без func.call(this, x) 
      // здесь может быть страшно тяжёлая задача для процессора
      // alert(`Called with ${x}`);
      // return x;
    
      //Вариант с использование метода объекта - для демонатрации func.call(this, x) 
      someMethod() {
        return 1;
      },
      slow(x) {
        // здесь может быть страшно тяжёлая задача для процессора
        alert("Called with " + x);
        return x * this.someMethod();
      }
    };
  
    function cachingDecorator(func) {
      let cache = new Map();
      return function(x) {
        if (cache.has(x)) { // если кеш содержит такой x,
          return cache.get(x); // читаем из него результат
        }

        // иначе, вызываем функцию
        //Вариант 1 - без привязки this
        // let result = func(x); // вариант 
      
        //Вариант 2 - с привязкой this
        let result = func.call(this, x); // .call() позволяет вызывать функцию, явно устанавливая this.
        cache.set(x, result); //кешируем (запоминаем) результат
        return result;
      };
    }
  
    worker.slow = cachingDecorator(worker.slow); // добавляем к функции обёртку-декоратор, делаем её кеширующей
  
    alert( worker.slow(2) ); // работает
    alert( worker.slow(2) ); // работает, не вызывая первоначальную функцию (кешируется)
    ```
- Работа движка, ассинхронность — в аком порядке выведутся console.log()?
  - дано несколько разных console.log - обычные, promise + .then(), setTimeout/setInterval
- Армия функций
  - https://learn.javascript.ru/task/make-army
  - https://learn.javascript.ru/let-const
  - https://qna.habr.com/q/365769
- Рекурсия - числа Фибоначи. Напишите функцию fib(n) которая возвращает n-е число Фибоначчи.
  - https://learn.javascript.ru/task/fibonacci-numbers
  - Вариант 1 - через рекурсию
  - Вариант 2 - через рекурсию + мемомизацию (чтоб по несколько раз не высчитывать одно и то же значение)
  - Вариант 3 - через цикл for (любая рекурсия может быть сведена к циклу)
    - начнёт с 1 и 2, затем из них получит fib(3) как их сумму, затем fib(4)как сумму предыдущих значений, затем fib(5)
      и так далее, до финального результата. На каждом шаге нам нужно помнить только значения двух предыдущих чисел
      последовательности.
- Рекурсия - возведение в степень.
  - ```js
    //через рекурсию
    function test(x, n) {
      if (n == 1) {
        return x;
      } else {
        return x * test(x, n - 1);
      }
    }
    alert( test
  - ```js
    //итеартивно, цикл for
    function pow(x, n) {
      let result = 1;
      for (let i = 0; i < n; i++) {
        result *= x; // умножаем result на x n раз в цикле
      }
      return result;
    }
    alert( pow(2, 3) ); // 8
    ```
- Рекурсия - факториал.
  - Число, умноженное на "себя минус один", затем на "себя минус два", и так далее до 1
  - [learn.javascript.ru - Рекурсия](https://learn.javascript.ru/recursion#dva-sposoba-myshleniya]
  - ```js
    function fact(n) {
      if(n == 1) {
        return 1
      }
      else {
        return n * fact(n - 1);
      }
    }
    alert( fact(4) ); // 24
    ```
- Рекурсия - вывод односвязного списка
  - [learn.javascript.ru - Вывод односвязного списка. Ркурсия, цикл](https://learn.javascript.ru/task/output-single-linked-list)
- Кофеварка
  - один раз написать самому (подсматривая в учебник)
  - https://learn.javascript.ru/private-protected-properties-methods
  - https://learn.javascript.ru/task/add-method-property-coffeemachine
  - https://learn.javascript.ru/task/add-public-coffeemachine
  - https://learn.javascript.ru/functional-inheritance
  - https://learn.javascript.ru/getters-setters
- Сделать debounce функцию
  - [learn.javascript.ru - Сделать Debounce](https://learn.javascript.ru/task/debounce)
  - [doka - Сделать Debounce на примере формы поиска](https://doka.guide/js/debounce/)
  - [Habr - Debouncing с помощью React Hooks](https://habr.com/ru/post/492248/)
  - [Habr - Debouncing с помощью React Hooks: хук для функций](https://habr.com/ru/company/domclick/blog/510616/)
  - [Habr - Микропаттерны оптимизации в Javascript: декораторы функций debouncing и throttling](https://habr.com/ru/post/60957/)
- Сделать throttling функцию
  - [Habr - Микропаттерны оптимизации в Javascript: декораторы функций debouncing и throttling](https://habr.com/ru/post/60957/)
- Предложить разные методы организации кэша для вычисления Фибоначчи
  - кэш ограничен 20 значениями, а поступить может хоть 10000 - как оптимизировать?
  - часть кэша выделяем под хранение предыдущих вычисленных значений (мемоизация).
  - Рекурсия - самый дорогой вариант вычисления Фибоначчи
- Нормализация данных для проектирования стэйта.
  - Например: в качестве ответа сервера получаем очень большой неупорядоченный массив - как с ним работать?
  - Решение: дробление по принципу связи. Точно не помню, надо повторять, но вроде идея такая - создаём отдельный массив
    для одних сущностей (задачи, например) и отдельный для других (пользователи) и устанавливаем между ними связи.

<br></p>
</details> 

[//]: # (Алгоритм подготовки к собеседованию)
<details><summary><b>Алгоритм подготовки к собеседованию</b></summary><p>

- Изучить описание вакансии. Выписать технологии, повторить
- Просмотреть заметки [Lebmo notes](https://github.com/Legmo/notes). Знать что в каком файле лежит.
- Повторить темы
  из [Подборки вопросов-ответов для собеседования разработчика](https://github.com/Legmo/notes/blob/master/Pages/JobSearch/InterviewQuestions.md)
  . Особенно разделы:
  - «Повторять»
  - «Из личного опыта»
  - «Популярные задачки»
  - остальные можно «просканировать»
  - акцентировать внимание на общих вопросах - как работает JS-движок, как устроен Redux и т.д.
- Перечитать свои резюме (hh.ru, linkedin, doc-файлы...)
- Почитать переписку с рекуртёром, посмотреть свои заметки по вакансии
- Полистать свои публичные проекты на GitHub — чтоб ответить на вопросы по своему коду
- Подготовить открытые вкладки — подглядывать на собеседовании (Legmo notes, learnjs, mdm, reactjs.org, свои резюме,
  вакансия)
- Открыть редактор с JS кодом — набирать-проверять код. Например [plnkr.co](https://plnkr.co/edit/jXj1QgBx0iPp8IAh)
- Подготовить свои достижения/неудачи
- Можно поискать в сети — как проходит собеседование в жут компании. Что спрашивают. Какие задачки задают.
- Если дали тестовое задание — поискать его на GitHub, вероятно кто-то уже делал и выкладывал код своего решения.
- Полистать код тестовых заданий, которые делал для других компаний
- Пересмотреть [IT-Kamasutra #100 - Теория ReactJS + Redux за 90 минут](https://youtu.be/0AohM_oOjBc)

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

[//]: # (Вопросы для собеседования по хукам React)
<details><summary><b>Вопросы для собеседования по хукам React</b></summary><p>

[Вопросы для собеседования по хукам React](https://temofeev.ru/info/articles/voprosy-dlya-sobesedovaniya-po-khukam-react/)

- Что такое хуки в React?
- Будут ли хуки React работать внутри классовых компонентов?
- Зачем были введены хуки в React?
- Как работает хук useState? Какие аргументы принимает этот хук и что он возвращает?
- Задача на использование useState
- Задача на использование useState 2 — callback
- Задача на использование useState 3 — слияние объектов в setSteat()

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

![](/Assets/Img/humor_js-interview-1.png)

<br>
<br>

*[Legmo, 2019-2022](https://github.com/Legmo/notes/)*