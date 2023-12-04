<h1>Подборки вопросов-ответов для собеседования разработчика</h1>

[//]: # (Общий список вопросов)
<details><summary><b>Общий список вопросов</b></summary><p>

[//]: # (JS — вопросы с собеседований)
- <details><summary><b>JS — вопросы с собеседований</b></summary><p>

  - Асинхронность
    - Как работает движок JS «под капотом» (event loop и т.д.)?
    - Что такое окружение?
    - «Куча» и «стэк» в event loop
    - Работа сборщика мусора
    - Что такое таски и микротаски?
  - Промисы
    - Что это такое?
    - Promise API — promise.all и т.д.
    - Можно ли реализовать аналог callback-hell с использованием промисов (внутри промиса?)
    - Как из SetTimeout сделать Promise? (не очень понял вопрос, видимо имелось ввиду - как вызвать промис из setTimeout)
  - Замыкания
  - This, bind, call. Контекст
  - Стрелочные функции 
    - Отличие стрелочных функций от обычных
    - Можно ли сделать .bind стрелочной функции
      - ОТВЕТ: Нет. У стрелочных функций нет `this`, он всегда будет определяться как контекст, в котором был определен. Если требуется привязка this — надо использовать обычную функцию. Ошибки не будет, просто не сработает (скорее всего)
  - Типы данных
    - Какие есть типы данных в JS?
    - Что даёт typeof
    - Чему равен typeof null
      - ОТВЕТ: Object. Официальная ошибка языка
    - Приведение `0` и `'0'` к boolean
  - Прототипы
    - Наследование, прототипы
    - Как сделать свой метод сортировки который будет доступен любому объекту? 
    - Хорошо ли расширять / менять глобальны прототип?
    - Когда допустимо расширение прототипов? - полифилы для старых браузеров
    - Как идёт поиск по цепочке прототипов?
    - `__proto__` и `[[Prototype]]`
    - Что находится в конце цепочки прототипов?
      - ОТВЕТ: Object.prototype. Все объекты наследуют свойства и методы Object. Любая попытка поиска за пределами цепочки приводит к null.
    - Можно ли как-то поменять прототип
  - Делегирование и всплытие событий
  - Отличия `cookie`, `localStorage`, `sessionStorage` 
    - ОТВЕТ: https://learn.javascript.ru/localstorage
  - Объекты
    - Массивы — это объекты?
    - Как скопировать объект в JS?
    - Как сделать полную копию объекта со свойствами типа 'number' и 'string'.
      - ОТВЕТ: 
      1. создать новый объект и воспроизвести структуру существующего, перебрав его свойства и скопировав их на примитивном уровне. Например циклом `for..in`
      2. использовать метод `Object.assign.` (`Object.assign(целевой_объект, [исходный_объект1, исходный_объект2, ...])`)
      3. при глубоком копировании - использовать рекурсию или что-то вроде cloneDeep из библиотеки lodash
    - Как удалить поле из объекта без копирования самого объекта?
      - ОТВЕТ: метод `delete`. Но не использовать это в массивах! В массивах - `.splice`, `slice`, `pop`, `.length - 1`... Если нужен новый объект со всеми ключами оригинала, кроме некоторых — деструктурирование.
    - Создание объекта через функции-конструкторы
  - Способы загрузки скриптов — обычная, `async` и `defer`
  - Какие есть способы объявить переменную? Чем они отличаются?
  - Что такое «область видимости»?
  - Что такое «блок кода»?
  - Метод массива `.map()`
  - Зачем нужна конструкция `??` 
    - ОТВЕТ: оператор «логического или»
  - В чём разница `.preventDefault()` и `.stopPropagation()`?
    - ОТВЕТ: `.preventDefault()` — метод для отмены действия браузера
    - ОТВЕТ: `.stopPropagation()` — остановка всплытия события. По умолчанию событие будет всплывать до элемента <html>, а затем до объекта document, а иногда даже до window, вызывая все обработчики на своём пути. Любой промежуточный обработчик может решить, что событие полностью обработано, и остановить всплытие. Не использовать без явной нужды, очевидной и архитектурно прозрачной. Иногда вместо этого мы можем использовать event.defaultPrevented, чтобы просигналить другим обработчикам, что событие обработано.
  - Циклы
    - Какие есть циклы в JS?
    - Как работает цикл `for`, что у него под капотом? (Под капотом у него `while`, а у того — генератор)
  - ООП
    - Классы, объекты, ООП
    - Как работает класс в JS  
  - Что такое `WebWorkers API`?
    - ОТВЕТ: API для параллельного выполнения сложных вычислительных задач. Потоки, принадлежащие браузеру, которые можно использовать для выполнения JS-кода без блокировки цикла событий.
  - Что такое `Service Worker API`?
    - ОТВЕТ: разновидность WebWorkers. Скрипт, выполняется браузером в фоне, отдельно от веб-страницы. Не имеет доступа к DOM. Может выполнять функции для которых не требуется взаимодействие со страницей или пользователем. Продолжает работать, даже когда вкладка с сайтом закрыта. Например: кешированть файлы из онлайн веб-приложения на локальное устройство пользователя и затем работать полностью в оффлайне.

  <br></p>
  </details> 

  [//]: # (JS)
- <details><summary><b>JS</b></summary><p>

  - Типы данных
    - Какие есть типы данных
    - Приведение типов
    - Оператор “+” с типами данных,
  - Движок JS 
    - Event Loop, стэк, очередь задач, микро/макро задачи, веб-воркеры, SetInterval/Promises...
    - Асинхронность и однопоточность JS - что это значит и чем обусловлено.
    - Интерпретатор
  - Сборщик мусора
  - Промисы
    - Promises
    - Promises API
    - Async/Await
    - then
      - что возвращает по умолчанию
      - это промис или просто обработчик, в котором я могу использовать промис?
    - как await ставит код на паузу
      - блокируется весь скрипт? Только данный блок?
    - циклы, for-await-of
    - 
    - [Хабр — Визуализация промисов и Async/Await](https://habr.com/ru/articles/501702)
    - [Хабр — Задачи, микрозадачи, очереди и планы](https://habr.com/ru/articles/264993/)
    - [Хабр — Оптимизация производительности фронтенда. Часть 2. Event loop, layout, paint, composite](https://habr.com/ru/articles/517594/)
  - Способы выполнения HTTP-запросов
    - Feetch
    - XMLHttpRequest - [Learnjs](https://learn.javascript.ru/xmlhttprequest) (его современный вариант — fetch)
  - Прототипы
    - Прототипное наследование
  - Замыкания
  - Передача "по значению" и "по ссылке"
  - Различие стрелочных функций и обычных
  - This, bind, call
  - Контекст выполнения
    - [Контекст выполнения](https://github.com/Legmo/notes/blob/master/Pages/JS/JS.md#this)
    - [Habr - Контекст выполнения и стек вызовов в JavaScript](https://habr.com/ru/company/ruvds/blog/422089/)
  - Атрибуты async и defer у тега script
  - Лексическое всплытие
  - Методы базовых типов
  - Переменные
  - Лексическое окружение
  - [Use strict](https://github.com/Legmo/notes/blob/master/Pages/JS/JS.md#useStrict)
  - [Атрибуты async и defer у тега script](https://github.com/Legmo/notes/blob/master/Pages/JS/JS.md#asyncDefer)
  - Функции, IIFE
    - Синтаксис "new Function"
    - Immediately Invoked Function Expression, IIFE — это функция, которая выполняется сразу же после того, как была определена.
    - [Function Declaration / Function Expression](https://github.com/Legmo/notes/blob/master/Pages/JS/JS.md#funcDeclaration) — `function sayHi(){}` / `let sayHi = function(){}`
    - Функции высшего порядка
    - [Анонимные функции, функциональные выражения](https://learn.javascript.ru/function-expressions)
    - Продвинутая работа с функциями (learnjs)
    - Callback
  - Модули
  - Объекты
    - [Habr - Работа с объектами в JavaScript: теория и практика](https://habr.com/ru/post/48542/)
    - Флаги и дескрипторы  
    - Аттрибуты свойств. Флаги, дескрипторы, методы доступа
  - Методы массивов и объектов
  - Создать копию массива = [...arraynme]
  - Как обращаться к свойствам объекта через object .['key']
  - API
  - Поднятие/погружение
  - Лексическое всплытие
  - Поднятие переменных (hoisting)
    - механизм, при котором переменные и объявления функций, передвигаются вверх своей области видимости перед тем, как код будет выполнен.
  - Оператор объединения с null - `??`
      - возвращает первый аргумент, если он не null/undefined , иначе второй.
      -  [Оператор нулевого слияния (learnjs)](https://learn.javascript.ru/nullish-coalescing-operator)
  - Список сокращённых лог. операторов
  - Логические операторы присваивания `&&=`, `||=`, `??=` — «присвоить если...»
    - `user &&= 'A'` — если user === true  
    - *user && (user = 'A')*
    - `user ||= 'A'` — если user === false  
    - if(!user)(user = 'A')
    - `user ??= 'A'` — если user === null или undefined  
    - *if(user === null || user === undefined)( user = 'A')*
  - Опциональная цепочка `?.`*
  - Побитовые операции
  - BigInt
  - Symbol
  - Коллекции Set, Map, WeakSet и WeakMap
  - Перебор структур данных. Методы `keys`, `values`, `entries`
  - ООП
    - Классы
    - [ООП в прототипном стиле](https://learn.javascript.ru/prototypes)
    - [ООП в классовом стиле](https://learn.javascript.ru/classes)
    - паттерны
    - SOLID
    - Архитектурные паттерны и стили MVC, MVVM, MVP, RESTful и пр.
    - Свойства геттеры и сеттеры
  - Каррирование
  - Декораторы и переадресация вызова
  - Proxy и Reflect
  - Proxy-объекты
  - Перебираемые объекты
  - [Итераторы, генераторы](https://learn.javascript.ru/generators-iterators)
  - Асинхронные итераторы и генераторы 
    - https://learn.javascript.ru/async-iterators-generators
    - https://learn.javascript.ru/async-await
  - Цикл for-await-of  - [Learnjs](https://learn.javascript.ru/async-await)  
  - [MDN - раздел про JS-фрэймворки (частично на русском)](https://developer.mozilla.org/ru/docs/Learn/Tools_and_testing/Client-side_JavaScript_frameworks)
  - Как профилировать и отлаживать js (кроме console.log)
  - [Прокси](https://learn.javascript.ru/proxy)
  - DOM
    - [DOM](https://learn.javascript.ru/ui)
    - Нативный JS: как обратиться к элементам DOM-страницы? А к конкретному? А по тегам?
  - Eval
  - Интернационализация
  - Switch
  - Ошибки, обработка ошибок
  - Отладка в браузере
    - debugger
    - выполнение кода в консоли
    - Разобраться как использовать debugger в коде и в расширении браузера
  - Если в компоненте поставил addEventListener - обязательно ставить removeEventListener https://youtu.be/BhwoKN1E3C8?t=2553
  - .
  - .
  - 
  - [Что нового в последних 3 версиях JS](../JS/JS.md#new)
  - [Работа JS-движка](../JS/JS.md#engine)
    - event loop, среда, web API, стэк, очередь задач, микро/макро задачи, setInterval/setTimeout, promises, обработчики
      промисов (then, catch, finally), async/await, веб-воркеры,
    - асинхронность и однопоточность JS - что это значит и чем обусловлено
    - В каком порядке будут выводиться console.log, Promise
  - [Сборщик мусора](../JS/JS.md#garbageCollection)
  - 
  - [Use strict](../JS/JS.md#useStrict)
  - [Атрибуты async и defer у тега script](../JS/JS.md#asyncDefer)
  - [Function Declaration / Function Expression](../JS/JS.md#funcDeclaration) — `function sayHi(){}`
    / `let sayHi = function(){}`
  - [Замыкания](../JS/JS.md#closures)
  - [Стрелочные функции](../JS/JS.md#arrowFunc)
  - [Контекст выполнения](../JS/JS.md#this)
  - [Ключевое слово this](../JS/JS.md#this)
  - [Метод bind()](../JS/JS.md#bind)
  - [Методы apply() и call()](../JS/JS.md#callApply)
  - 
  - [Promise](../JS/JS.md#promise)
  - [Async/Await](../JS/JS.md#promiseAsync)
  - [Асинхронная итерация](../JS/JS.md#asyncIteratorsGenerators)
  - [Цикл for-await-of](../JS/JS.md#cycleForAwaitOf)
  - [Fetch](../JS/JS.md#fetch) - метод реализации асинхронных запросов в нативном JS. Предоставляется Fetch API
  - [XMLHttpRequest](../JS/JS.md#xmlHttpRequest) - его современный аналог — fetch
  - 
  - [Что является объектом в JS?](../JS/JS.mdwhatIsObject#)
  - [Передача по значению / по ссылке](../JS/JS.md#bjectReference)
  - [Методы объектов](../JS/JS.md#objectMethods)
  - [Методы массивов](../JS/JS.md#arrayMethods)
    - [learn.javascript.ru - Шпаргалка](https://learn.javascript.ru/array-methods#itogo)
  - [Мутирующие методы массивов](../JS/JS.md#arrayMethods) - sort, reverse, splice
  - [Копирование объектов](../JS/JS.md#objectCopy) - обычное, глубокое
  - 
  - [Типы в JS (string, number, object...)](../JS/JS.md#types)
  - [Приведение типов](../JS/JS.md#typesTransformation)
  - [Различия Undefined и Null](../JS/JS.md#types)
  - [Методы примитивов](../JS/JS.md#primitiveMethods)
  - [Ver, Let, Const](../JS/JS.md#variables)
  - [Оператор нулевого слияния (`??`)](../JS/JS.md#nullishСoalescing)
  - [Логические операторы присваивания(`&&=`, `||=`, `??=`)](../JS/JS.md#logicalAssignment)
  - [Опциональная цепочка `?.`](../JS/JS.md#optionalChaining)
  - [Деструктурирующее присваивание](../JS/JS.md#destruct)
  - [Остаточные параметры и оператор расширения / spread (...)](../JS/JS.md#spread)
  - [Шаблонные строки (шаблонные литералы). Теговые шаблоны](../JS/JS.md#tmpLiterals)
  - [Параметры функции по умолчанию](../JS/JS.md#funcDefParam)
  - 
  - [Лексическое всплытие](../JS/JS.md#eventHoisting)
  - [Рекурсия](../Programming/Programming.md#recursion)
  - [Коллекции Map и Set, WeakMap и WeakSet](../JS/JS.md#collections)
  - [Декораторы](../JS/JS.md#decorators)
  - [Декоратор Debounce](../JS/JS.md#debounce)
  - [Декоратор Throttling](../JS/JS.md#throttling)
  - [Прототипы](../JS/JS.md#prototype)
  - [Классы](../JS/JS.md#classes)
    - [Базовые вопросы (learn.javascript.ru)](https://learn.javascript.ru/classes)
    - [Ключевые слова extends и super (tproger)](https://tproger.ru/translations/javascript-cheatsheet/#extendsuperkwrds)
    - [Публичные поля классов (MDN)](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Classes/Public_class_fields#публичные_поля_экземпляра)
    - ...
  - [Аттрибуты свойств (Флаги, дескрипторы, методы доступа)](../JS/JS.md#propertiesAttributes)
  - Как профилировать и отлаживать js (кроме console.log)
  - Нативный JS: как обратиться к элементам DOM-страницы? А к конкретному? А по тегам?
  - 
  - [Циклы](../JS/JS.md#cycles)
  - [Перебор структур данных. Методы «keys», «values», «entries»](../JS/JS.md#keysValuesEntries)
  - [Перебираемые/итерируемые объекты](../JS/JS.md#iterable)
  - [Преобразование объектов в примитивы](../JS/JS.md#objectToPrimitive)
  - [Symbol](../JS/JS.md#symbol)
  - [Callback](../JS/JS.md#callback)
  - [Cамовыполняющиеся функции. Модули](../JS/JS.md#modules)
  - [Обработчики событий, events handlers](../JS/JS.md#eventsHandlers)
  - [Web-workers](../JS/JS.md#webWorkers)
  - [Proxy-объекты](../JS/JS.md#proxyObjects)
  - [Функции-генераторы](../JS/JS.md#funcGenerators)
  - [Итераторы](../JS/JS.md#iterators)
  - [Хранение данных в браузере: Cookie, socalStorage, sessionStorage](../JS/JS.md#dataStorage)
  - [Утечки памяти в JS](../JS/JS.md#memoryLeak)
  - [Объект Error](../JS/JS.md#errorsObject)
  - [Чистота кода](../JS/JS.md#codeCleaning)
  - [Языки поверх JavaScript](../JS/JS.md#metaLanguages)
  - .
  - .
  - **ТЕМЫ ИЗ LEARN.JAVASCRIPT.RU**
  - Браузер - документ, события, интерфейсы
    - Документ
      - Браузерное окружение, спецификации
      - DOM-дерево
      - Навигация по DOM-элементам
      - Поиск: getElement*, querySelector*
      - Свойства узлов: тип, тег и содержимое
      - Атрибуты и свойства
      - Изменение документа
      - Стили и классы
      - Размеры и прокрутка элементов
      - Размеры и прокрутка окна
      - Координаты
    - Введение в события
      - Введение в браузерные события
      - Всплытие и погружение
      - Делегирование событий
      - Действия браузера по умолчанию
      - Генерация пользовательских событий
      - Интерфейсные события
      - Основы событий мыши
      - Движение мыши: mouseover/out, mouseenter/leave
      - Drag'n'Drop с событиями мыши
      - Клавиатура: keydown и keyup
      - События указателя
      - Прокрутка
      - Формы, элементы управления
      - Свойства и методы формы
      - Фокусировка: focus/blur
      - События: change, input, cut, copy, paste
      - Отправка формы: событие и метод submit
    - Загрузка документа и ресурсов
      - Страница: DOMContentLoaded, load, beforeunload, unload
      - Скрипты: async, defer
      - Загрузка ресурсов: onload и onerror
    - Разное
      - MutationObserver: наблюдатель за изменениями
      - Selection и Range
      - Событийный цикл: микрозадачи и макрозадачи
  - Фреймы и окна
    - Открытие окон и методы window
    - Общение между окнами
    - Атака типа clickjacking
  - Бинарные данные и файлы
    - ArrayBuffer, бинарные массивы
    - TextDecoder и TextEncoder
    - Blob
    - File и FileReader
  - Сетевые запросы
    - Fetch
    - FormData
    - Fetch: ход загрузки
    - Fetch: прерывание запроса
    - Fetch: запросы на другие сайты
    - Fetch API
    - Объекты URL
    - XMLHttpRequest
    - Возобновляемая загрузка файлов
    - Длинные опросы
    - WebSocket
    - Server Sent Events
  - Хранение данных в браузере
    - Куки, document.cookie
    - LocalStorage, sessionStorage
    - IndexedDB
  - Анимация
    - Кривые Безье
    - CSS-анимации
    - JavaScript-анимации
  - Веб-компоненты
    - С орбитальной высоты
    - Пользовательские элементы (Custom Elements)
    - Shadow DOM
    - Элемент "template"
    - Слоты теневого DOM, композиция
    - Настройка стилей теневого DOM
    - Теневой DOM и события
  - Регулярные выражения

  <br></p>
  </details> 

[//]: # (React)
- <details><summary><b>React</b></summary><p>

  - [Legmo - React](/Pages/JS/React.md)
  - .
  - .
  - методы жизненного цикла
  - хуки
    - useEffect
    - useMemo & UseCallback
    - useState
    - useRef
  - Virtual DOM
  - React.memo
  - Key, почему нельзя в него писать индекс элемента
  - Порталы
  - Оптимизация React, ререндеры
  - Методы жизненного цикла компонента React - не просто заучить, а понимать с какой целью они были добавлены.
  - .
  - .
  - Хуки
    - основные хуки ( Use state, Use Effect)
    - useMemo
      -  - [Учим на примерах](https://webtricks-master.ru/react-hooks/uchim-usememo-na-primerah/)  
    - useCallback
    - useRef
      - [Hexlet](https://ru.hexlet.io/courses/js-react-hooks/lessons/use-ref/theory_unit)
    - useEffect
      -  [useEffect(fn, []) это не новый componentDidMount()](https://stasonmars.ru/javascript/useeffect-eto-ne-novyi-componentdidmount/)
    - useState
    - useContext
    - useReducer 
    - UseRef вместо useState и предотвращение ре-рендера
    - 
    - [Legmo - Хуки](https://github.com/Legmo/notes/blob/master/Pages/JS/React.md)
    - [Демистификация хуков React: useCallback, useMemo и все-все-все](https://proglib.io/p/demistifikaciya-hukov-react-usecallback-usememo-i-vse-vse-vse-2021-02-28)
    - [Habr - React hooks, как не выстрелить себе в ноги. Часть 1: работа с состоянием](https://habr.com/ru/company/otus/blog/667706/)    
    - [Habr - React hooks, как не выстрелить себе в ноги. Часть 2: useEffect и useLayoutEffect](https://habr.com/ru/company/otus/blog/668700/)
    - [Habr - React hooks, как не выстрелить себе в ноги. Часть 3.1: мемоизация, memo](https://habr.com/ru/company/otus/blog/669962/)  
    - [Вопросы для собеседования по хукам React - useState](https://temofeev.ru/info/articles/voprosy-dlya-sobesedovaniya-po-khukam-react/)  
    - [Habr - Debouncing с помощью React Hooks](https://habr.com/ru/post/492248/)  
    - [Habr - Debouncing с помощью React Hooks: хук для функций](https://habr.com/ru/company/domclick/blog/510616/)
    - [WebDev - #2 React Hooks A Complete Introduction (Полное введение в Хуки) (YouTube)](https://youtu.be/X6j7Y7tp3_c)  
    - [WebDev - #3 React 16.8 Hooks RELEASE! (Реакт Хуки. Официальный релиз) (YouTube)](https://youtu.be/19EmLE2mZ1Q)
    - Использование хуков `useDispatch` и `useSelector` ( Redux Toolkit)
      - [Habr - Готовим селекторы в Redux](https://habr.com/ru/post/564004/)
      - [Стоит ли использовать Redux с React Hooks](https://amorgunov.com/posts/2020-04-12-use-redux-with-react-hooks/)
    - Redux vs Хуки
      - [Должен ли я использовать connect или хуки для react redux и который имеет лучшую производительность?](https://translated.turbopages.org/proxy_u/en-ru.ru.b0899dbb-62fa5bee-806cf6a7-74722d776562/https/stackoverflow.com/questions/66527982/should-i-use-connect-or-hooks-for-react-redux-and-which-has-better-performance)
      - [От Редакса к хукам?](https://bespoyasov.ru/blog/you-might-not-need-redux-now/)
      - [Стоит ли использовать Redux с React Hooks](https://amorgunov.com/posts/2020-04-12-use-redux-with-react-hooks/)
      - [Смогут ли React-хуки заменить Redux](https://css-live.ru/articles/smogut-li-react-xuki-zamenit-redux.html)
      - 
    - Дэн Абрамов - [cтатья про хуки](https://habr.com/ru/company/ruvds/blog/445276/)
  - мемоизация
  - оптимизация 
  - React.memo
  - Error.Boundary
  - Компоненты
    - Функциональные / классовые
    - Жизненный цикл компонента
    - в каком случае классовые нельзя заменить функциональными, 
    - жизненные циклы
    - [WebDev - #11 Методы жизненного цикла (Lifecycle methods)](https://youtu.be/O8f6aXqpGHw)
  - Рендер
    - [Руководство по рендеренгу в React](https://www.bxnotes.ru/conspect/lib/react/react-notes/rendering/)
    - [Когда React выполняет повторный рендеринг компонентов?](https://webformyself.com/kogda-react-vypolnyaet-povtornyj-rendering-komponentov/)
    - [Визуальное руководство по состоянию в React](https://tuhub.ru/posts/vizualnoe-rukovodstvo-po-sostoyaniyu-v-react)
    - рендеринг с помощью массивов,
    - Как сделать условный рендер в React.js
      - [7 способов реализации условного рендеринга в React](https://russianblogs.com/article/8615661123/)
      - [Оф. документация](https://ru.react.js.org/docs/conditional-rendering.html)
  - Render props
    - [Оф. документация](https://ru.reactjs.org/docs/render-props.html)
    - [Разбираемся с Render Props на примере](https://habr.com/ru/post/418863/)
  - Key
    - зачем нужен
    - почему нельзя в него писать индекс элемента.
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
  - Reconciliation 
    - [Статья](https://kramarenko.com.ua/post/what_is_reconciliation)
  - Порталы 
    - [Оф. документация](https://ru.reactjs.org/docs/portals.html)
  - Строгий режим в React.js 
    - [Оф. документация](https://ru.reactjs.org/docs/strict-mode.html)
  - Метод `getDerivedStateFromProps(props, state)` 
    - [Оф. документация](https://ru.react.js.org/docs/react-component.html?#static-getderivedstatefromprops). 
    - Срабатывает перед каждым рендером/ререндером.  Для редких случаев когда состояние зависит от изменений в свойствах со временем.
  - Разница между createElement и cloneElement
    - [Оф. документация - createElement](https://ru.reactjs.org/docs/react-api.html#createelement)
    - [Оф. документация - cloneElement](https://ru.reactjs.org/docs/react-api.html#cloneelement)
    - [stackoverflow.com - React createElement vs cloneElement](https://stackoverflow.com/questions/35616029/react-createelement-vs-cloneelement)
  - Фрагменты
    - [WebDev - #9 Фрагменты и стили (Fragments & CSS)](https://youtu.be/Z0S4wcyzLZc)
  - Ref
    - [Legmo notes]](https://github.com/Legmo/notes/blob/master/Pages/JS/React.md)
  - HOC 
    - [Legmo notes]](https://github.com/Legmo/notes/blob/master/Pages/JS/React.md)
  - Child
    - Что такое потомки?
    - [Погружаемся в работу с children на React (2020)](https://stasonmars.ru/javascript/pogruzhaemsya-v-raboty-s-children-na-react/)
    - [Оф. документация](https://ru.reactjs.org/docs/react-api.html#reactchildrenmap)
  - Как работает React 
    - Статья про основы современного Redux — https://redux.js.org/tutorials/essentials/part-1-overview-concepts
    - [Habr - Как работает React: подробное руководство](https://habr.com/ru/company/timeweb/blog/586972/)
    - [Habr - Как работает React: подробное руководство](https://habr.com/ru/company/timeweb/blog/586972/)  
    - [habr - Объясняем современный JavaScript динозавру](https://habr.com/ru/company/mailru/blog/340922/)  
    - [csssr - Основы производительности React-приложений](https://blog.csssr.ru/2016/12/07/react-perfomance)
  - Оптимизация React  
    - Как уменьшить количество ререндера компонентов?
    - [«Запашки» кода React-компонентов ](https://css-live.ru/javascript/zapashki-koda-react-komponentov.html#jsx-returns)  
    - [csssr - Основы производительности React-приложений](https://blog.csssr.ru/2016/12/07/react-perfomance)
    - 
  - .
  - Современные практики - 2020, 2021, 2022  
    - Статья про [лучшие практики React 2021](https://habr.com/ru/company/otus/blog/546534/)
  - Работа с формами
  - Работа с таблицами
  - схема работы
  - библиотеки
  - React DevTools - [статья на Habr (2021)](https://habr.com/ru/post/595607/)
  - Статья [Как не надо писать React: неправильные шаблоны и проблемы в React](https://webformyself.com/kak-ne-nado-pisat-react-nepravilnye-shablony-i-problemy-v-react/)
  - Статья Дэна Абрамова - [cтатья про компоненты](https://habr.com/ru/company/ruvds/blog/444348/)
  - Context — отличия от Redux от , как оно работает.
  - .
  - Условная отрисовка
  - Композиция vs Наследование
  - Списки и ключи
  - [StyledComponents](https://styled-components.com/docs/basics#getting-started)
  - Pure Component 
    - Ребята используют только классовые компоненты, именно ради Pure Component.
    - Говорят что функциональные часто делают лишний re-render, и для оптимизации надо задействовать классовые.
    - Разобраться - можно ли вопрос ре-рендеринга как-то решить на функциональных компонентах.
  - .
  - [connect](https://habr.com/ru/company/ruvds/blog/423157/)
  - [props.children](https://stasonmars.ru/javascript/pogruzhaemsya-v-raboty-s-children-na-react/) 
  - [Redux form](https://redux-form.com) - Очень много возни. Валидация, сложные формы и т.д.
  - [Formik](https://formik.org/)
  - [React Final Form](https://final-form.org/react)
  - [Redux-modal](https://www.npmjs.com/package/redux-modal) - Постоянно приходится разбираться. Через этот плагин все модалки отрисовываются
  - PopUp
  - .
  - TS
  - Тестирование
  - .
  - Альтернативные стэйт-менеджеры
    - [MobX](https://mobx.js.org/README.html)
    - [Recoil - A state management library for React - Подкаст Пятиминутка React](https://5minreact.ru/posts/064-recoil/)
    - [Redux Toolkit](https://redux-toolkit.js.org/)
  - 
  - Задачки
    - Что произойдет, если передать функцию в метод setState ?
    - Как получить значение input?
  - [Оф. документация React](https://ru.reactjs.org/docs/hello-world.html) (прочесть трижды)  
  - .
  - Читать про duck
  - Освоить работу с приложениями отладки, прежде всего React и Redux
  - 
  - React — вёрстка 
    - Styled components
    - CSS in JS
    - [WebDev - #9 Фрагменты и стили (Fragments & CSS)](https://youtu.be/Z0S4wcyzLZc)
  - .
  - .
  - Как работает
  - Как происходит рендеринг + жизненый цикл компонента
  - Теневой DOM
  - Хуки
  - Контекст
  - Роутинг
  - Компоненты высшего порядка
  - Flux + Redux + async работа со стором
  - .
  - интерполяция
  - Оптимизация React
  - Что нового в React и JS
  -  React Server Components, Стримы и Server Actions https://youtu.be/yC_q38uRxCw
  - .
  - .
  - Как работает React
    - [Habr - Как работает React: подробное руководство](https://habr.com/ru/company/timeweb/blog/586972/)
    - [Habr - Как работает React: подробное руководство](https://habr.com/ru/company/timeweb/blog/586972/)
    - [Habr - Объясняем современный JavaScript динозавру](https://habr.com/ru/company/mailru/blog/340922/)
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
    - [Sass - какие для вас главные преимущества](/Pages/JobSearch/HtmlCssQuestions.md)
  - Источники
    - [Оф. документация React](https://ru.reactjs.org/docs/hello-world.html) (прочесть трижды)
    - [Legmo - React](/Pages/JS/React.md)
    - https://it-shpora.pp.ua

  <br></p>
  </details> 

[//]: # (Redux)
- <details><summary><b>Redux</b></summary><p>

  - [Legmo - Redux](/Pages/JS/Redux.md)
  - .
  - .
  - Недостатки Redux
  - Устройство Redux (store, createStore, state, reducer, actions, action creators, dispatch, provider, connect,
    middleware, mapDispatchToProps, mapStateToProps)
  - Redux Toolkit
  - .
  - ReduxToolkit
  - RTK Query
  - ReactRedux
  - Connect и то как он прокидывает props
  - Как бы вы отключили хранилище Redux, чтобы оно не принимало никаких изменений в состоянии?
  - .
  - .
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
  - Какие ещё есть wrapper кроме thunk
  - Есть Redux Toolkit - почему тогда использую connect? Какие альтернативы предлагает React Toolkit?
  - Нужно ли в редьюсере в swithc...case делать default и возвращать в нём state?
  - Что такое useSelector.
    - [Habr - Готовим селекторы в Redux](https://habr.com/ru/post/564004/)
    - [Стоит ли использовать Redux с React Hooks](https://amorgunov.com/posts/2020-04-12-use-redux-with-react-hooks/)

  <br></p>
  </details> 

[//]: # (TypeScript)
- <details><summary><b>TypeScript</b></summary><p>

  - [Legmo - TypeScript](/Pages/JS/TypeScript.md) (ДОРАБОТАТЬ)
  - .
  - Очень любят спрашивать
    - какие типы есть
    - дженерики
  - .
  - .
  - Дженерики  
  - Интерфейсы, отличия от типов  
  - Кортежи, отличие от Массивов
  - Утилиты - Partial, Omit, Exclude, Extract
  - Перегрузка
    - ветвление логики?
    - описание функции, когда для одной функции несколько вариантов входных данных => будет несколько вариантов выхода  
  - .
  - .
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
  - Дженерики. **Что такое генерификация? Как она работает? Как дженерики транспилируются в JS?**
  - Декораторы - классов, свойств, методов, аксессоров (геттеров/сеттеров). Фабрика декораторов
  - Типизация функций
  - Утилиты (Utility Types)
  - Деструктуризация - как реализована
  - Event loop - как реализован
  - Сборщик мусора - как реализован

  <br></p>
  </details> 

[//]: # (GIT)
- <details><summary><b>GIT</b></summary><p>

  - squash
  - head
  - rebase
  - merge
  - restore
  - конфликты
  - .
  - Для себя
    - Исключение файлов
      - как исключить из GIT файл docker\\docker-compose.yml
      - как исключать файл после git add
      - [Hexlet - Игнорирование файлов в Git](https://ru.hexlet.io/courses/git_base/lessons/git_gitignore/theory_unit)  
    - возможности PHPStorm
    - работа с историей коммитов
    - работа с графическими оболочками
  - checkout
  - ветвление — у нас, по сути, Issue Branch Workflow 
    - Ветки создаются из заданий в проектном трекере. Ветки могут иметь одинаковые названия id заданий
    + модификация Git Flow — есть стабильный master, есть развивающийся develop. В мастер пушим через releas_s
  - позиция head
  - merge
  - rebase
  - squash
  - cherry pick

  <br></p>
  </details> 

[//]: # (Сеть)
- <details><summary><b>Сеть</b></summary><p>

  - [Legmo - Browser](../Network/Network.md)
  - .
  - .
  - HTTP, HTTP2, HTTPS
  - Методы HTTP
  - CORS
  - WebSocket
  - Cookies
  - .
  - REST,  RESTFul, 
  - CORS
  - HTTP, HTTP2, HTTPS  
  - Методы HTTP
  - GraphQL 
    - какие методы для него используются (POST или GET?) — Get
  - Cookies  
  - WebSocket
  - .
  - TCP/IP, DNS, HTTP + secure
  - .
  - .
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

[//]: # (Браузер)
- <details><summary><b>Браузер</b></summary><p>

  - [Legmo - Browser. Оптимизация работы браузера](../Network/Browser#optimization.md)
  - [Legmo - Browser](../Network/Browser.md)
  - .
  - .
  - Как работает: от запроса в адресную строку до закрытия вкладки (вкл. рендеринг, перерендеринг)
  - DOM, 
  - Render, Relayout, Repaint, 
  - "дорогие" операции...
  - Работа с памятью
  - Выполнение JS 
  - .
  - .
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
  - .
  - .
  - Critical rendering path
  - "Дорогие" операции работы с DOM. `Relayout` / `Repaint`
  - "Дорогие" операции чтения (getComputedStyle() и т.д.)
  - .
  - Схема работы браузера:
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

  - **Рекомендации по оптимизации**
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

[//]: # (Оптимизация web-страниц)
- <details><summary><b>Оптимизация web-страниц</b></summary><p>

  - [Legmo - Browser. Оптимизация работы браузера](../Network/Browser#optimization.md)
  - JS - эффективно использовать память
  - JS - избегать использования setTimeout() и setInterval() для обновления внешнего вида элементов страниц.
  - JS - переносить длительные вычисления в [`веб-воркеры`](/Pages/Network/Browser.md).
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
  - .
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

[//]: # (Webpack)
- <details><summary><b>Webpack</b></summary><p>

  - Как с помощью webpack'а оптимизировать бандл. 
  - **Webpack** - сборщик проекта, бандлер
      - собирает из проекта 1-N файлов для браузера
      - превращение исходников в конечный продукт
      - альтернатива менеджерам задач — Gulp, Grunt

  <br></p>
  </details> 

[//]: # (CSS)
- <details><summary><b>CSS</b></summary><p>

  - [@container](https://webdevblog.ru/css-sledujushhego-pokoleniya-container) — стилизовать компоненты в завсимости от размера родительского контйнера
  - Critical render path
  - Flexbox
  - CSS-grid
  - BEM
  - Canvas
  - анимация
  - понятие «потока»
  - как работает «float»
  - разные виды «position»

  <br></p>
  </details> 

[//]: # (ООП)
- <details><summary><b>ООП</b></summary><p>

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

[//]: # (Алгоритмы)
- <details><summary><b>Алгоритмы</b></summary><p>

  - [Legmo - Тестирование](/Pages/Programming/Algorithms.md)

  - сложность алгоритма, алгоритмическая сложность
  - оптимизация
  - big O notation

  <br></p>
  </details> 

[//]: # (Тестирование)
- <details><summary><b>Тестирование</b></summary><p>

  - [Legmo - Тестирование](/Pages/Programming/Testing.md)
  - .
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

  <br></p>
  </details> 

[//]: # (Soft-skills)
- <details><summary><b>Soft-skills</b></summary><p>

  - Самые большие ошибки
  - Самые большие достижения
  - Яркие, красивые примеры из своего рабочего опыта — какую выгоду получила ваша предыдущая компания от вашей деятельности, как вы помогли спасти ее от кризиса, как вы вывели ее в лидеры и т.д.

  <br></p>
  </details> 

[//]: # (Прочие)
- <details><summary><b>Прочие вопросы</b></summary><p>


  - **NodeJS** - среда выполнения JS
  - **NPM** - менеджер зависимостей
  - **Yarn**
  - **Nginx** 
  - **Bash**  - оболочка (shell). Интерпретатор командной строки. 
    - Программа, которая принимает ваши и обрабатывает, выполняя встроенные функции (например, cd) или вызывая внешние программы (например, ls или gcc). 
    - Обеспечивает взаимодействие пользователя и консоли (часть операционной системы для управления компьютером)
  - **Babel** — транспайлер, переводит JS  в другую версию. Или например JS в TypeScript и наоборот
  - .

  - Можно ли реализовать button который хранит свое значение в value, и меняет его через свой onChange 
  - .
  - [Чистые функции](/Pages/Programming/Programming.md)
  - [Термины](/Pages/Programming/Programming.md)
    - инкапсуляция
    - **идемпотентность** — сколько раз не вызовем операцию, всегда получаем тот же результат
    - **детерминированность** — результат однозначно определяется исходными данными.
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
  - [REST API](/Pages/Network/Network.md)
    - методы - out, post, get, delete...
    - Что можно отправлять
    - типа параметров и т.д.
    - Диапазоны http-кодов
  - [GraphQL](/Pages/Network/GraphQL.md)
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
  - [Алгоритмы](../Programming/Algorithms.md) - ИЗУЧАТЬ!
  - [Микросервисная архитектура](/Pages/Network/Microservices.md)
  - [СI/CD - Continuous Integration, Continuous Delivery, Continuous Deployment](/Pages/Programming/CI-CD.md)
  - Отслеживание изменений в фреймворке - как он понимает, что нечто изменилось и надо применить изменения к DOM?
    - [Medium - Как создать реактивный фреймворк на JavaScript](https://medium.com/@monochromer/%D0%BA%D0%B0%D0%BA-%D1%81%D0%BE%D0%B7%D0%B4%D0%B0%D1%82%D1%8C-%D1%80%D0%B5%D0%B0%D0%BA%D1%82%D0%B8%D0%B2%D0%BD%D1%8B%D0%B9-%D1%84%D1%80%D0%B5%D0%B9%D0%BC%D0%B2%D0%BE%D1%80%D0%BA-%D0%BD%D0%B0-javascript-cfa34c63fd52)
    - [MutationObserver](../Network/Browser.md) и [ещё](https://learn.javascript.ru/mutation-observer) - API
      браузера. Спец. объект, наблюдает за DOM-элементом, запускает колбэк в случае изменений.
  - [Что такое CORS](../Network/Network.md#CORS)
  - Css селекторы - [MDN](https://developer.mozilla.org/ru/docs/Web/CSS/CSS_Selectors)
  - [Domain Driven Design, DDD](/Pages/Programming/Programming.md)

  <br></p>
  </details> 

[//]: # (С собеседований)
- <details><summary><b>С собеседований</b></summary><p>

  - **JS**
    - Асинхронность
      - Как работает движок JS «под капотом» (event loop и т.д.)?
      - Асинхроннность. Что такое окружение. Куча и стэк в  в эвент лупе
      - Garbage collector (You don't know JS)
      - Event loop, микро-макро таск
      - Что такое таски и микротаски?
    - Промисы
      - Что это такое 
      - Promise API (promise.all и т.д.)
      - Можно ли реализовать аналог callback-hell с использованием промисов (внутри промиса?)
    - Типы данных
      - Какие есть типы данных в JS?
      - Что даёт typeof
      - Чему равен typeof null
        - Object. Официальная ошибка языка
      - Приведение `0` и `'0'` к boolean
    - Прототипы
      - Наследование, прототипы
      - Как сделать свой метод сортировки который будет доступен любому объекту? 
      - Хорошо ли расширять / менять глобальны прототип?
      - Когда допустимо расширение прототипов? - полифилы для старых браузеров
      - Как идёт поиск по цепочке прототипов?
      - `__proto__` и `[[Prototype]]`
      - Что находится в конце цепочки прототипов?
        - Object.prototype. Все объекты наследуют свойства и методы Object. Любая попытка поиска за пределами цепочки
          приводит к null.
      - Можно ли как-то поменять прототип
    - Замыкания
    - Делегирование, всплытие
    - This, bind, call
    - Стрелочные функции 
      - Отличие стрелочных функций от обычных
      - Можно ли сделать .bind стрелочной функции
        - нет. У стрелочных функций нет `this`, он всегда будет определяться как контекст, в котором был определен.
        - Если требуется привязка this — надо использовать обычную функцию.
        - Ошибки не будет, просто не сработает (скорее всего)
    - Отличия Cookie, LocalStorage, sessionStorage 
      - https://learn.javascript.ru/localstorage
    - Объекты
      - Массивы - это объекты?
      - Как сделать полную копию объекта со свойствами типа 'number' и 'string'.
        1. создать новый объект и воспроизвести структуру существующего, перебрав его свойства и скопировав их на
           примитивном уровне. Нпрмиер циклом `for..in`
        2. использовать метод `Object.assign.` (`Object.assign(целевой_объект, [исходный_объект1, исходный_объект2, ...])`)
        3. при глубоком копировании - использовать рекурсию или что-то вроде cloneDeep из библиотеки lodash
      - Как скопировать объект в JS?
      - Как удалить поле из объекта без копирования самого объекта?
        - метод `delete`. Но не использовать это в массивах! В массивах - `.splice`, `slice`, `pop`, `.length - 1`...
        - если нужен новый объект со всеми ключами оригинала, кроме некоторых — деструктурирование.
      - Создание объекта через функции-конструкторы
    - Загрузка скриптов — обычная, async и defer
    - Зачем нужна конструкция `??` 
      - оператор «логического или»
    - Что такое область видимости
    - Какие есть способы объявить переменную, чем они отличаются
    - Что такое блок кода
    - Метод массива .map()
    - В чём разница `.preventDefault()` и `.stopPropagation()`
      - `.preventDefault()` — метод для отмены действия браузера
      - `.stopPropagation()` — остановка всплытия события. По умолчанию событие будет всплывать до элемента <html>, а затем до объекта document, а иногда даже до window, вызывая все обработчики на своём пути. Любой промежуточный обработчик может решить, что событие полностью обработано, и остановить всплытие. Не использовать без явной нужды, очевидной и архитектурно прозрачной. Иногда вместо этого мы можем использовать event.defaultPrevented, чтобы просигналить другим обработчикам, что событие обработано.
    - Какие есть циклы в JS
    - Как работает цикл `for`, что у него под капотом? (Под капотом у него `while`, а у того — генератор)
    - Как из SetTimeout сделать Promise? (не очень понял вопрос, видимо имелось ввиду - как вызвать промис из setTimeout)
    - Что такое WebWorkers API?
    - Что такое Service Worker API?
    - ООП
      - Классы, объекты, ООП
      - Как работает класс в JS  
  - **React**
    - что такое React
    - различия функциональных/классовых компонент
    - какие JS/React библиотеки использую
    - что такое прогрессивный рендеринг, гидратация
    - хуки
      - какие есть
      - как имитировать методы жизненного цикла
      - useState
      - useEffect, что даёт return
      - useMemo / useCallback (что вернёт)
    - отличия ReactRouter и ReactRouterDOM
    - Что такое VirtualDOM
    - Какие есть методы жизненного цикла
    - Какие стэйт-менеджменты использовал
    - Есть два react-компонента на разном уровне вложенности (меню в шапке и форма в боковой колонке). В форме что-то
    поменялось, надо прокинуть в шапку - какие есть варианты
    - Flux (Redux)
    - подъем пропсов до общего родителя
    - отслеживать изменения в DOM (совсем плохой вариант)
    - есть ещё какие-то варианты. Что-то про observer, библиотека RxJS
    - Вопрос по моему проекту. Есть Redux Toolkit - почему тогда использую connect? Какие альтернативы предлагает Redux
      Toolkit
      - Redux Toolkit предоставляет хуки `useDispatch` и `useSelector`
    - Как получать данные из Redux?
    - Что такое useSelector (React-Redux).
      - [Habr - Готовим селекторы в Redux](https://habr.com/ru/post/564004/)
      - [Стоит ли использовать Redux с React Hooks](https://amorgunov.com/posts/2020-04-12-use-redux-with-react-hooks/)
    - Где хранить селекторы - в отдельной папке, в папке компонента, в файле компонента. Duck
    - Что такое и как работает store
    - Что такое и как работает action
    - Что такое и как работает thunk middleware,
    - Какие ещё middleware приходилось использовать
    - Приходилось ли писать свои middleware
    - Нужно ли в редьюсере в switch...case делать default и возвращать в нём state ?
      - Ответ — «да». Редьюсеров может быть много, каждый action раскидывается по всем редьюсерам. Какой-то один его
        обрабатывает, и может внести изменения (вернёт обновлённый кусок стэйта), остальные по дефолту вернут старый
        кусок стэйта. Из ответов всех редюсеров соберётся новый объект state.
    - Если в компоненте один коллбэк вызывает последовательно несколько actions один за другим - они выполнятся в том же
      порядке?
      - Ответ — «да». Redux store не возьмёт в работу второй action, пока не выполнится первый. Иначе бы Redux не мог
        нормально управлять state.
    - пара вопросов про работу React Router
    - Когда вызывается рендер в React?
      - когда меняются state или props
        - в частности, когда мы вызываем функцию setState
      - когда меняется родительский компонент
    - Когда вызывается рендер в React для функциональных и классовых компонентов?
      - Классовые:
        - this.setState()
        - this.forceUpdate()
      - Функциональные
        - useState
        - useReducer
      - Все
        - Рендер родителя вызовет рендер всех его дочерних элементов (возможна оптимизация)
        - повторный рендеринг будет вызван, если повторно запустить ReactDOM.render(<App />), что эквивалентно
          forceUpdate() на корневом компоненте.
    - Как оптимизировать рендер компонента?
      - shouldComponentUpdate — метод жизненного цикла классового компонента, если он вернет false то рендер не будет
        запущен
      - React.PureComponent — класс, реализующий типовой shouldComponentUpdate.
      - React.memo — HOC, который предотвращает повторный рендер, если входные props не изменились
      - useMemo() — чтобы в функциональном компоненте сохранить ссылки на объекты между рендерами
      - useCallback() — чтобы в функциональном компоненте сохранить ссылки на объекты между рендерами
      - аттрибуты key
      - Context /useContext() - Context API обеспечивает передачу переменных в дерево компонентов, без их непосредственной
        передачи в props данных компонентов.
      - оптимизация структуры компонет - помещать логику ближе к месту использования данных
    - Какие хуки использовать для оптимизации рендера?
      - useMemo() — чтобы в функциональном компоненте сохранить ссылки на объекты между рендерами
      - useCallback() — чтобы в функциональном компоненте сохранить ссылки на объекты между рендерами
      - useContext() - Context API обеспечивает передачу переменных в дерево компонентов, без их непосредственной передачи
        в props данных компонентов.
    - Как выполнить код на этапе между изменением state и render'ом?
    - Зачем нужен Virtual DOM?
    - Назови отличия useEffect от useLayoutEffect.
    - useEffect. Пустой массив зависимостей
    - useRef [
      - зачем используется 
        - работа с DOM-объектами
        - объект со свойством useRef вместо useState - не вызовет ре-рендер при изменении?]() 
    - «Порталы» — что это такое и зачем нужны. 
      - Пример использования - создание модальных окон. Передаём только id, рендерим в другом месте DOM 
    - ErrorBoundary
    - Мемоизация в React. useMemo, useCallback, React.memo
    - Как бороться с ререндерами в React
    - Key. Можно ли использовать случайные числа в качестве key
    - Из каких методов жизненного цикла делать запрос на сервер
    - Отличия хуков useMemo() и useCallback()
    - Для чего нужны файлы `.lock` в npm/yran
      - хранят зависимости зависимостей - т.е. полное дерево зависимостей
    - Стэйт-менеджменты кроме Redux (MobX и т.д.)
    - Возможности Redux Toolkit
    - Недостатки Redux
    - Как реализовать на React паттерн «singleton» (одиночка)
      - объект, существующий в единственном экземпляре на всё приложение
    - Что такое React
    - Основные хуки
    - Различия `udeCallback` и `useMemo`
    - Как работает Virtual DOM
    - Thunk, Middleware
    - Как оптимизировать рендер React-компонента?
    - Что такое React.Memo? Отличия от useMemo?
    - Какие ещё хуки используются для оптимизации работы React?
    - Как я реализовал бы сложную форму на React? Formik, или custom hooks + MobX.
  - **Redux**
    - Какие есть проблемы у Redux?
      - большая связность (?) - состояние всех компонент хранится в одном месте (глобальный store), сложно перенести модуль в другой проект, надо тянуть за собой структуру Redux. Концепции «изолированных модулей», «слои», реализация состояния хуками...
      - много «кода ради кода»
    - Что такое Redux
  - **TypeScript**
    - Что такое Interface
    - Отличие Interface от Type. Когда что использовать? Больше семантическое, пришло из ООП.
    - Utility Types - Partial
    - Tuples - отличия от Array 
    - Generic в TypeScript
    - Что такое перегрузка в TypeScript?
    - TypeScript — какими возможностями пользуюсь?
    - TypeScript — Различия между `any` и `unknow`
    - TypeScript — Настройки в проекте — включаю ли поддержку `any`?
    - TypeScript — Настройки в проекте — включаю ли `strict node check` — не позволяет присваивать значение `undefined`
    - TypeScript — Omit, Pick, Readonly
    - Что такое `useState<>()` в TypeScript
    - Модификаторы доступов классов - public, protected, private  в TS через декораторы/ ключевые слова
  - **GIT**
    - стратегии слияния merge
    - head
    - конфликты
    - git add
  - **Сеть**
    - Из чего состоит http запрос?
      - Стартовая строка, Заголовки, Тело
    - «Я знаю отличную шутку про UDP, но не факт, что она до вас дойдет». (шутка). UDP – это передача данных без
      установления соединения, не имеет подтверждения связи => нет гарантий доставки или порядка получения пакетов.
    - Что такое HTTP
    - Что такое HTTPS
    - Зачем нужны GET, POST и другие методы - почему не отправлять всё одним? Их различия
    - В чем различия если методом POST делать авторизацию (отправляем логин-пароль) или отправлять картинку?
    - Что за кракозябры появятся в адресной строке, если ввести туда что-то на русском - браузер использует кодировку
      ISO/IEC 8859-1, но там есть только латинские символы, так что любые другие приходится кодировать.
    - CORS
      - что это
      - JSONP, инъекции
      - простые и сложные
    - cookie
      - можно ли установить cookie из браузера?
      - любые ли cookie можно читать из кода?
    - Назови основные заголовки, отвечающие за кэширования веб-приложения.
    - HTTP, HTTP2, HTTPS
    - GrapQL
    - WebSocket
    - Что такое CORS?
  - **Браузер**
    - Как работает рендер браузера?
    - Что такое WebWorkers API?
    - Что такое Service Worker API?
  - **Оптимизация web-страниц**
    - Назови основные метрики производительности, на которые стоит обращать внимание, при разработке веб-приложения.
    - Назови основные заголовки, отвечающие за кэширования веб-приложения.
  - **Webpack**
    - Что такое Webpack и зачем он нужен
    - методы позиционирования
    - семантическая вёрстка
    - Что такое критичный CSS?
    - Что такое св-во gap в CSS?
    - Какой уровень вложенности блоков допустим в BEM?
      - любой
  - **ООП**
    - Как сделать метод иммутабельным?
      - Такой метод не должен менять входные данные. Возвращать копию объекта (т.к. объекты меняются «по ссылке»).
    - Что такое статический метод класса?
      - Метод самого класса. Может вызываться для классов, но не для отдельных объектов, созданных на его базе.
      - Не имеет доступа к состоянию (полям) объекта, то есть к переменной this.
      - Он не знает, какой именно объект его вызвал и, соответственно, у него нет доступа к полям объекта.
    - Инстансы (Экземпляры, instances)
      - Экземпляр — это объект, который содержит имена свойств и методы класса, но с уникальными значениями свойств (т. е. экземпляры класса имеют свои собственные уникальные идентификаторы). Грубо говоря, на основе класса «машина» сделал конкретный экземпляр — с опр. мощностью двигателя и т.д.
  - **CSS**
  - **Soft skills**
    - почему у вас два разных резюме (краткое под React и полное под Drupal)
    - почему сменили работу
    - какие результаты, достижения которыми гордишься? В жизни и в работе
    - что нравится / не нравится в работе
    - что предпочёл бы делать один, что предпочёл бы делать вместе, что предпочёл бы чтоб сделали вместо меня
    - сделал свои задачи, тим-лид отвечает долго, есть некий backlog задач на будущее (для всей команды, не факт что они
      пойдут мне) — что будешь делать? Отдыхать, ждать тим-лида, делать задачу из backlog (какую?)
    - что бы делал, если было бы неограниченное количество ресурсов (времени, сил, здоровья, денег)
  - **Прочие вопросы**
    - Принципы программирования
      - DRY
      - KISS
      - YAGNI
      - SOLID
    - Что такое архитектура во фронтенде?
    - Как организовать архитектуру приложения. Например, надо делить код между несколькими историями
    - GrapQL
    - Как сделать запрос на сервер из HTML, без использования JS?
      - использовать submit формы
    - Как искать ошибки
      - console.log, debugger, точки останова
    - В каких операционных системах работал
    - Не смущает ли необходимость зайти по SSH и исправить какой-то файл
    - «Как выйти из VIM» (шутка)
    - Безопасность - сталкивался ли с инъекциями и т.д.
    - Что такое Sourcemap - файл для связи между исходным кодом и скомпилированным кодом.
    - Есть компонент, выводит на экран кнопку. Но кнопке счётчик нажатий (менятеся при клике). Предложить как можно больше методов реализации - как хранить данные о состоянии счётчика нажатий. При этом, что они сохрнаялись при обновлении страницы. Хотели услышать про вариант записи в URL-адрес, как источник истины (после `?`)

  <br></p>
  </details> 

<br></p>
</details> 


<details><summary><b>Из личного опыта — по фирмам</b></summary><p>

- JS
  - Типы данных
  - Работа JS-движка - Event Loop, стэк, очередь задач, микро/макро задачи, веб-воркеры, SetInterval/Promises...
  - Асинхронность и однопоточность JS - что это значит и чем обусловлено.
  - Promises, Promises API, Async/Await
  - Прототипы
  - Замыкания
  - Передача "по значению" и "по ссылке"
  - Различие стрелочных функций и обычных
  - This, bind, call
  - Атрибуты async и defer у тега script
  - Лексическое всплытие
- TypeScript
  - Дженерики
  - Интерфейсы, отличия от типов
  - Кортежи, отличие от Массивов
  - Утилиты - Partial, Omit, Exclude, Extract
- Сеть
  - HTTP, HTTP2, HTTPS
  - Методы HTTP
  - CORS
  - WebSocket
  - Cookies
- React
  - методы жизненного цикла
  - хуки
    - useEffect
    - useMemo & UseCallback
    - useState
    - useRef
  - Virtual DOM
  - React.memo
  - Key, почему нельзя в него писать индекс элемента
  - Порталы
  - Оптимизация React, ререндеры
  - Методы жизненного цикла компонента React - не просто заучить, а понимать с какой целью они были добавлены.
- Redux
  - Недостатки Redux
  - Устройство Redux (store, createStore, state, reducer, actions, action creators, dispatch, provider, connect,
    middleware, mapDispatchToProps, mapStateToProps)
  - Redux Toolkit
- Работа браузера — DOM, Render, Relayout, Repaint, "дорогие" операции...
- Алгоритмическая сложность
<br>
<br>

[//]: # (Вопросы одного из рекуртёров на скриниге)
<details><summary><b>Вопросы одного из рекуртёров на скриниге (август 2022)</b></summary><p>
 
- Из чего состоит http запрос?
  - Стартовая строка, Заголовки, Тело
- Как сделать метод иммутабельным?
  - Такой метод не должен менять входные данные. Возвращать копию объекта (т.к. объекты меняются «по ссылке»).
- Что такое статический метод класса?
  - Метод самого класса. Может вызываться для классов, но не для отдельных объектов, созданных на его базе.
  - Не имеет доступа к состоянию (полям) объекта, то есть к переменной this.
  - Он не знает, какой именно объект его вызвал и, соответственно, у него нет доступа к полям объекта.

<br></p>
</details> 

[//]: # (ГК «Самолёт», React-frontend middle+)
<details><summary><b>ГК «Самолёт», React-frontend middle+ (август 2022)</b></summary><p>

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
    - Решение: [Legmo notes — Задачки для собеседования frontend](InterviewTasks.md#task-1)
    - [Legmo - JS. Работа движка JS](../JS/JS.md#engine)
    - [Legmo - JS. Асинхронность](../JS/JS.md#asynchrony)
  - числа Фибоначчи
    - Решение: [Legmo notes — Задачки для собеседования frontend](InterviewTasks.md#task-2)

<br></p>
</details> 

[//]: # («CryptoRocks», React-frontend middle)
<details><summary><b>«CryptoRocks», React-frontend middle (сентябрь 2022)</b></summary><p>

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
    - Подробнее: [Legmo notes — Задачки для собеседования frontend](InterviewTasks.md#task-13)
  - сортировка - отсортировать исходный массив положительных и отрицательных чисел по их квадратам. Использовать
    алгоритм не требующий много памяти
  - Решение: [Legmo notes — Задачки для собеседования frontend](InterviewTasks.md#task-6)

<br></p>
</details> 

[//]: # («РЖД» Цифровые сервисы, Frontend developer)
<details><summary><b>«РЖД» (Цифровые сервисы), Frontend developer (сентябрь 2022)</b></summary><p>

- Soft skills
  - почему у вас два разных резюме (краткое под React и полное под Drupal)
  - почему смнеили работу
  - какие результаты, достижения которыми гордишься? В жизни и в работе
  - что нравится / не нравится в работе
  - что предпочёл бы делать один, что предпочёл бы делать вместе, что предпочёл бы чтоб сделали вместо меня
  - сделал свои задачи, тим-лид отвечает долго, есть некий backlog задач на будущее (для всей команды, не факт что они
    пойдут мне) — что будешь делать? Отдыхать, ждать тим-лида, делать задачу из backlog (какую?)
  - что бы делал, если было бы неограниченное количество ресурсов (времени, сил, здоровья, денег)
- Hard skills. React, Redux
  - Вопрос по моему проекту. Есть Redux Toolkit - почему тогда использую connect? Какие альтернативы предлагает Redux
    Toolkit
    - Redux Toolkit предоставляет хуки `useDispatch` и `useSelector`
  - Как получать данные из Redux?
  - Что такое useSelector (React-Redux).
    - [Habr - Готовим селекторы в Redux](https://habr.com/ru/post/564004/)
    - [Стоит ли использовать Redux с React Hooks](https://amorgunov.com/posts/2020-04-12-use-redux-with-react-hooks/)
  - Где хранить селекторы - в отдельной папке, в папке компонента, в файле компонента. Duck
  - Что такое и как работает store
  - Что такое и как работает action
  - Что такое и как работает thunk middleware,
  - Какие ещё middleware приходилось использовать
  - Приходилось ли писать свои middleware
  - Нужно ли в редьюсере в switch...case делать default и возвращать в нём state ?
    - Ответ — «да». Редьюсеров может быть много, каждый action раскидывается по всем редьюсерам. Какой-то один его
      обрабатывает, и может внести изменения (вернёт обновлённый кусок стэйта), остальные по дефолту вернут старый
      кусок стэйта. Из ответов всех редюсеров соберётся новый объект state.
  - Если в компоненте один коллбэк вызывает последовательно несколько actions один за другим - они выполнятся в том же
    порядке?
    - Ответ — «да». Redux store не возьмёт в работу второй action, пока не выполнится первый. Иначе бы Redux не мог
      нормально управлять state.
  - пара вопросов про работу React Router
- Hard skills. JS
  - зачем нужна конструкция `??` - оператор «логического или»
  - приведение `0` и `'0'` к boolean
  - есть компонент, выводит на экран кнопку. Но кнопке счётчик нажатий (менятеся при клике). Предложить как можно
    больше методов реализации - как хранить данные о состоянии счётчика нажатий. При этом, что они сохрнаялись при
    обновлении страницы. Хотели услышать про вариант записи в URL-адрес, как источник истины (после `?`)

<br></p>
</details> 

[//]: # («InfoWatch», Frontend developer middle/senior)
<details><summary><b>«InfoWatch»** Frontend developer middle/senior (сентябрь 2022)</b></summary><p>

- Вопросов было много, это примерно 2/3
- В каких операционных системах работал
- Не смущает ли необходимость зайти по SSH и исправить какой-то файл
- «Как выйти из VIM» (шутка)
- «Я знаю отличную шутку про UDP, но не факт, что она до вас дойдет». (шутка). UDP – это передача данных без
  установления соединения, не имеет подтверждения связи => нет гарантий доставки или порядка получения пакетов.
- Что такое HTTP
- Что такое HTTPS
- Зачем нужны GET, POST и другие методы - почему не отправлять всё одним? Их различия
- В чем различия если методом POST делать авторизацию (отправляем логин-пароль) или отправлять картинку?
- Что за кракозябры появятся в адресной строке, если ввести туда что-то на русском - браузер использует кодировку
  ISO/IEC 8859-1, но там есть только латинские символы, так что любые другие приходится кодировать.
- Безопасность - сталкивался ли с инъекциями и т.д.
- Типы данных в JS, что даёт typeof
- Массивы - это объекты?
- Что такое область видимости
- Какие есть способы объявить переменную, чем они отличаются
- Что такое блок кода
- Наследование, прототипы
- Можно ли как-то поменять прототип
- Promises
- This, bind, call
- Отличие стрелочных функций от обычных
- Метод массива .map()
- Задачка — Найти все ошибки в компоненте React. Типизировать хук useState()
  - key ставить родительскому элементу внутри map(), а не вложенном элементу
  - почему в key лучше использовать id, а не index
  - onChange - использовать SetState() вместо прямого присваивания нового значения (state[index].status =
    e.target.checked)
  - вообще концептуально неправильно ориентироваться на e.target.checked — лучше оперировать pRevState
  - типизировать хук useState
  - Решение: [Legmo notes — Задачки для собеседования frontend](InterviewTasks.md#task-8)
  - 
  - Что такое `useState<>()` в TypeScript

<br></p>
</details> 

[//]: # («T.Hunter», Frontend developer)
<details><summary><b>«T.Hunter» Frontend developer (сентябрь 2022)</b></summary><p>

- экспресс-интервью под видео-запись (скрининг)
- Можно ли сделать .bind стрелочной функции
  - нет. У стрелочных функций нет `this`, он всегда будет определяться как контекст, в котором был определен.
  - Если требуется привязка this — надо использовать обычную функцию.
  - Ошибки не будет, просто не сработает (скорее всего)
- Чему равен typeof null
  - Object. Официальная ошибка языка
- В чём разница `.preventDefault()` и `.stopPropagation()`
  - `.preventDefault()` — метод для отмены действия браузера
  - `.stopPropagation()` — остановка всплытия события. По умолчанию событие будет всплывать до элемента <html>, а
    затем до объекта document, а иногда даже до window, вызывая все обработчики на своём пути. Любой промежуточный
    обработчик может решить, что событие полностью обработано, и остановить всплытие. Не использовать без явной нужды,
    очевидной и архитектурно прозрачной. Иногда вместо этого мы можем использовать event.defaultPrevented, чтобы
    просигналить другим обработчикам, что событие обработано.
- Что находится в конце цепочки прототипов?
  - Object.prototype. Все объекты наследуют свойства и методы Object. Любая попытка поиска за пределами цепочки
    приводит к null.
- Как сделать полную копию объекта со свойствами типа 'number' и 'string'.
  1. создать новый объект и воспроизвести структуру существующего, перебрав его свойства и скопировав их на
     примитивном уровне. Нпрмиер циклом `for..in`
  2. использовать метод `Object.assign.` (`Object.assign(целевой_объект, [исходный_объект1, исходный_объект2, ...])`)
  3. при глубоком копировании - использовать рекурсию или что-то вроде cloneDeep из библиотеки lodash
- Как удалить поле из объекта без копирования самого объекта?
  - метод `delete`. Но не использовать это в массивах! В массивах - `.splice`, `slice`, `pop`, `.length - 1`...
  - если нужен новый объект со всеми ключами оригинала, кроме некоторых — деструктурирование.
- Когда вызывается рендер в React?
  - когда меняются state или props
    - в частности, когда мы вызываем функцию setState
  - когда меняется родительский компонент
- Когда вызывается рендер в React для функциональных и классовых компонентов?
  - Классовые:
    - this.setState()
    - this.forceUpdate()
  - Функциональные
    - useState
    - useReducer
  - Все
    - Рендер родителя вызовет рендер всех его дочерних элементов (возможна оптимизация)
    - повторный рендеринг будет вызван, если повторно запустить ReactDOM.render(<App />), что эквивалентно
      forceUpdate() на корневом компоненте.
- Как оптимизировать рендер компонента?
  - shouldComponentUpdate — метод жизненного цикла классового компонента, если он вернет false то рендер не будет
    запущен
  - React.PureComponent — класс, реализующий типовой shouldComponentUpdate.
  - React.memo — HOC, который предотвращает повторный рендер, если входные props не изменились
  - useMemo() — чтобы в функциональном компоненте сохранить ссылки на объекты между рендерами
  - useCallback() — чтобы в функциональном компоненте сохранить ссылки на объекты между рендерами
  - аттрибуты key
  - Context /useContext() - Context API обеспечивает передачу переменных в дерево компонентов, без их непосредственной
    передачи в props данных компонентов.
  - оптимизация структуры компонет - помещать логику ближе к месту использования данных
- Какие хуки использовать для оптимизации рендера?
  - useMemo() — чтобы в функциональном компоненте сохранить ссылки на объекты между рендерами
  - useCallback() — чтобы в функциональном компоненте сохранить ссылки на объекты между рендерами
  - useContext() - Context API обеспечивает передачу переменных в дерево компонентов, без их непосредственной передачи
    в props данных компонентов.
- Как выполнить код на этапе между изменением state и render'ом?

<br></p>
</details> 

[//]: # («IT-One», Frontend developer)
<details><summary><b>«IT-One» Frontend developer (сентябрь 2022)</b></summary><p>

 - Задачка на JS — Генерация строки из массива объектов
  - есть массив однотипных объектов, у каждого есть свойства value, order, expired. 
  - надо написать функцию которая 
    - исключить объекты с expired=true, 
    - оставшиеся отсортировать по значению order (предполагалось использовать метод sort), 
    - потом взять значения свойства value, 
    - сделать каждому значению reverse, 
    - записать всё это в строку, 
    - при этом ни один символ в строке не должен повторяться дважды (предполагалось использовать коллекцию Set)
  - ```js
    // Написать функцию, либо последовательность операций, которая вернёт результат следующих условий:
    // результате есть строка из сконкатенированных value элементов коллекции, расположенных в обратном порядке
    // реузльтат не содержит одинаковых букв, если буква уже добавлена в строку, она более не добавляется
    // результат собирается только из непросроченных записей (т.е. из тех, у которых expired: false)
    // результат конкатенируется в порядке возрастания order
      
    const input = [
      {value: 'qweq', order: 4, expired: false},
      {value: 'asdq', order: 2, expired: true},
      {value: 'jkri', order: 1, expired: false},
      {value: 'oiod', order: 3, expired: false},
    ];
    ```  
  - Решение: [Legmo notes — Задачки для собеседования frontend](InterviewTasks.md#task-1)
- Задачка на JS — Порядок вывода console.log
  - в частности, в `Promise(resolve => {setTimeout(()=>{resolve()}}).then()` — resolve() прерывает очередь макрозадач, и отрабатывают все then. Как-то так
  - [Legmo notes — Задачки для собеседования frontend](InterviewTasks.md#task-1)
- TypeScript
  - что такое Utility Types
  - Utility Types Recod, Pick...
- Задачка на TypeScript - типизировать функцию 
  - Задачка
    ```js
    /* 
     Есть объект X (произвольный) и функция getProperty, которая на вход принимает произвольный объект 
     и строковое значение свойств
     необходимо при помощи TypeScript допилить функцию getProperty таким образомю чтобы на этапе написания кода 
     в строке getProperty(X, 'm') компилятор выдавал ошибку «Argument of type '"m"' is not assignable to parameter of type '"a"' | '"b"' | '"c"' | '"d"'»
    */
      
    const X = {a:1, b: 2, c: 3, d:4}
      
    let getProperty = function(obj, key){
      return obj[key]
    }
      
    //getProperty(X,a)
    //getProperty(X,m) 
      
    // Должно получиться что-то вроде: 
    // let getProperty:<V extends Record<string, >, T extends keyof V> = function(obj: V, data: T) => number;
    ```
    - должна была получиться конструкция типа `<V extends Record <string,>, T extends keyof V>(obj:V, data:T) => number`
    - Решение: [Legmo notes — Задачки для собеседования frontend](InterviewTasks.md#task-11)


<br></p>
</details> 

[//]: # («Orion», Frontend developer React middle)
<details><summary><b>«Orion», Frontend developer React middle (сентябрь 2022)</b></summary><p>

- Вопросы от рекуртёра на скрининге
  1. Назови основные метрики производительности, на которые стоит обращать внимание, при разработке веб-приложения.
  2. Назови основные заголовки, отвечающие за кэширования веб-приложения.
  3. Что такое таски и микротаски?
  4. Зачем нужен Virtual DOM?
  5. Назови отличия useEffect от useLayoutEffect.
- Задачка на собеседовании
  ```js
  // ВАРИАНТ 1
  // Написать функцию getData, которая запрашивает данные по url и
  // в случае неуспешного запроса, повторяет его еще 5 раз
  // в случае неудачи возвращает ошибку “Заданный URL недоступен”
  // Как делаем запрос (fetch или что-то ещё - не важно)

  function getData() { }
    
  getData('https://example.com')
  .then(console.log)
  .catch(console.error)
  ```
  Решение: [Legmo notes — Задачки для собеседования frontend](InterviewTasks.md#task-9)

  ```js
  // ВАРИАНТ 2 
  // Написать синхронную функцию
  // Внутри функции генерируем случайное число
  // Если число больше 0,5 - возвращаем его
  // Если число меньше 0,5 - вызываем снова. И так 5 раз 
  // Если 5 раз неудача - выводим console.log
  ```
  Решение: [Legmo notes — Задачки для собеседования frontend](InterviewTasks.md#task-10)

- **???**


<br></p>
</details> 

[//]: # («BTБ», Frontend developer React middle)
<details><summary><b>«ВТБ», Frontend developer React middle (октябрь 2022)</b></summary><p>

Задачка на React. Console.log внутри setTimeout внутри UseEffect
```jsx
//Что будет выведено в console.log если очень быстро нажать 3 раза подряд на кнопку?

import React, {useStae, useEffect} from "react";
import ReactDOM  from "react-dom"; 

function Exmple() {
  const [count, setCount] = useState(0);
  
  useEffect(() => {
    setTimeout(() => {
      console.log(`You clicked ${count} times`)
    }, 3000);
  });
  
  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count +1)}>
        Click me
      </button>
    </div>    
  )
}

const rootElement = document.getElementById("root");
ReactDOM.render(<Example />, rootElement);
```

- Решение: [Legmo notes — Задачки для собеседования frontend](InterviewTasks.md#task-12)

<br></p>
</details> 

[//]: # («Aston», Frontend developer React middle )
<details><summary><b>«Aston», Frontend developer React middle (октябрь 2022)</b></summary><p>

Собеседование более часа, под видео-запись.

Некоторые вопросы:
- JS
  - Асинхронность
  - Промисы
  - Promise API - promise.all и т.д.
  - Делегирование, всплытие
  - Прототипы. 
    - Как сделать свой метод сортировки который будет доступен любому объекту? 
    - Хорошо ли расширять / менять глобальны прототип?
    - Когда допустимо расширение прототипов? - полифилы для старых браузеров
    - Как идёт поиск по цепочке прототипов?
    - `__proto__` и `[[Prototype]]`
- TypeScript
  - Что такое Interface
  - Отличие Interface от Type. Когда что использовать? Больше семантическое, пришло из ООП.
  - Utility Types - Partial
  - Tuples - отличия от Array 
- React
  - useEffect. Пустой массив зависимостей
  - useRef [
    - зачем используется 
      - работа с DOM-объектами
      - объект со свойством useRef вместо useState - не вызовет ре-рендер при изменении?]() 
  - «Порталы» — что это такое и зачем нужны. 
    - Пример использования - создание модальных окон. Передаём только id, рендерим в другом месте DOM 
  - ErrorBoundary
- Network
  - CORS
    - что это
    - JSONP, инъекции
    - простые и сложные
  - cookie
    - можно ли установить cookie из браузера?
    - любые ли cookie можно читать из кода?
- Принципы программирования
  - DRY
  - KISS
  - YAGNI
  - SOLID
<br></p>
</details> 

[//]: # («Digital Nomands», Frontend developer React middle)
<details><summary><b>«Digital Nomands», Frontend developer React middle (октябрь 2022)</b></summary><p>

Вначале тестовое задание 
- есть виджет, который долго грузится
- есть набор строк, которые должны выводиться, пока виджет грузиться («подождите ещё чуть-чуть» и т.д.)
- есть объект с переводами этих строк, который пришёл с сервера
- делать компонент-обёртку, который будет ждать загрузки виджета, выводить переведённые строки через опр. промежуток времени, если виджет не загрузился за время Х - прерывать загрузку и выводить соответствующее сообщение. 
- Т.е. в обёртке совмещён инструмент перевода (i18n) + какой-то таймер-планировщик
- всё это со структурой папок, типизацией, линтером и т.д.

Вопросы
- Что такое архитектура во фронтенде?
- Как скопировать объект в JS?
- Как из SetTimeout сделать Promise? (не очень понял вопрос, видимо имелось ввиду - как вызвать промис из setTimeout)
- Generic в TypeScript
- Что такое перегрузка в TypeScript?
- Какие есть проблемы у Redux?
  - большая связность (?) - состояние всех компонент хранится в одном месте (глобальный store), сложно перенести модуль в другой проект, надо тянуть за собой структуру Redux. Концепции «изолированных модулей», «слои», реализация состояния хуками...
  - много «кода ради кода»
- Что такое критичный CSS?
- Что такое св-во gap в CSS?
- Какой уровень вложенности блоков допустим в BEM?
  - любой
- Как сделать запрос на сервер из HTML, без использования JS?
  - использовать submit формы
- Отличия хуков useMemo() и useCallback()
- Для чего нужны файлы `.lock` в npm/yran
  - хранят зависимости зависимостей - т.е. полное дерево зависимостей

<br></p>
</details> 

[//]: # («Raiffeisen», Frontend developer React middle)
<details><summary><b>«Raiffeisen», Frontend developer React middle (октябрь 2022)</b></summary><p>

Рассказ о себе
Обсудили мой pet-project - архитектура, почему такая структура папок, зачем использую Redux и т.д.

Вопросы:
- Стэйт-менеджменты кроме Redux (MobX и т.д.)
- Возможности Redux Toolkit
- Недостатки Redux
- Что такое CORS?
- WebSocket
- Что такое Sourcemap - файл для связи между исходным кодом и скомпилированным кодом.
- Что такое Webpack и зачем он нужен
- HTTP, HTTP2, HTTPS
- GrapQL
- Мемоизация в React. useMemo, useCallback, React.memo
- Как бороться с ререндерами в React
- Key. Можно ли использовать случайные числа в качестве key
- Из каких методов жизненного цикла делать запрос на сервер

Задачки:
- в каком порядке выведутся console.log
- Обработка строки (вырезать N восклицательных знаков)
  - Задача
    - Напишите функцию, которая принимает строку и удаляет из неё N восклицательных знаков
    ```js
      const removeExclamations = (str, count) => {};
      console.log(removeExclamations('!!!Hello, !!world!', 5)) //Hello, world!
    ```
  - Решение: [Legmo notes — Задачки для собеседования frontend](InterviewTasks.md#task-4)
- Написать функцию находящую пересечение двух массивов чисел.
  - Эту задачку пропустили - сказали что вроде знания у меня есть.
  - Задача
    ```js
    const a = [1, 10, 2, 6, 9, -32];
    const b = [-7, 1, 9, 8, 0, 1, 10];
    const intersect = (a,b) => {
      //your code here
    }
    //console.log(intersect(a,b)); //[1,9,10]
    ```
  - Решение: [Legmo notes — Задачки для собеседования frontend](InterviewTasks.md#task-5)
- Создать React-компонент, который по нажатию кнопки создаёт новый `<input>`. Все значения валидируются. Если форма невалидна — кнопка «Сохранить» disabled. 
  - Задача
    - Добавление любого количества input'ов по кнопке
    - Валидация введённого во все input значения с помощью функции `validate`
    - Если форма не валидна - кнопка «Сохранить» должна быть `disabled`
  - Решение: [Legmo notes — Задачки для собеседования frontend](InterviewTasks.md#task-7)

<br></p>
</details> 

[//]: # («Интеллектуальные решения», Frontend developer React middle)
<details><summary><b>«Интеллектуальные решения», Фронтенд разработчик (ноябрь 2022)</b></summary><p>

- от 150 000 до 250 000 руб. на руки
- https://hh.ru/vacancy/70869655

Рассказ о проекте.
Рассказ о себе

Вопросы:
- Что такое замыкания
- Что такое промисы
- Можно ли реализовать аналог callback-hell с использованием промисов (внутри промиса?)
- Какие есть циклы в JS
- Как работает цикл `for`, что у него под капотом? (Под капотом у него `while`, а у того — генератор)
- Что такое React
- Основные хуки
- Различия `udeCallback` и `useMemo`
- Как работает Virtual DOM
- Что такое Redux
- Thunk, Middleware
- TypeScript — Omit, Pick, Readonly

Задачки:
- реализовать алгоритм поиска квадратного корня, не используя `pow` и `log`
  - имелся ввиду оператор `Math.sqrt()`
  - Подробнее: [Legmo notes — Задачки для собеседования frontend](InterviewTasks.md#task-14)
- числа Фиббоначи — ок
  - Подробнее: [Legmo notes — Задачки для собеседования frontend](InterviewTasks.md)
- формула расчёта длины отрезка в двумерной системе координат — долго не мог понять как, потом сделал
  - по сути надо было написать фукнцию для формулы `Math.sqrt(pow((x2-x1),2) + pow((y2-y1),2))`. 
  - формулу можно было найти в поисковике
- проверить строку на уникальность символов (т.е. нет ли в ней повторяющихся символов - да/нет)
  - есть три решения
    - приводим строку к массиву `orig`, символы из строки пишем в массив `result`, и сравниваем `orig` и `result`. Сложность `O(n + n^2)`
    - из строки символы по одному присваиваем в объект hashMap (ключ = символ, значение = индекс символа в строке). Тогда при попытке присвоить второй такой же символ - он присвоится существующему. Потом можно посмотреть размер массива, например. И сравнить с длиной строке. Сложность алгоритма будет проще
    - символы строки присвоить коллекции Set и сравнить str.length === Set.size. Сложность `O(n)`
  - сделал одну реализацию из трёх (первую)
  - не смог посчитать сложность алгоритма
  - запутался что такое hashMap
  - не придумал вариант с ключом объекта => можно проверять символ по ключу
  - не придумал вариант с str.length !== Set.size
  - Подробнее: [Legmo notes — Задачки для собеседования frontend](InterviewTasks.md#task-15)

<br></p>
</details> 

[//]: # («Kamaz» цифровая платформа, Frontend developer React middle)
<details><summary><b>«Kamaz» цифровая платформа, Фронтенд разработчик (ноябрь 2022)</b></summary><p>

Собеседование без кодинга, теоретические вопросы — ~30 минут

Вопросы:
- Есть ли знания Node.JS? Желание изучить?
- Как организовать архитектуру приложения. Например, надо делить код между несколькими историями
- Как работает движок JS «под капотом» (event loop и т.д.)?
- Что такое WebWorkers API?
- Что такое Service Worker API?
- Как работает рендер браузера?
- Как оптимизировать рендер React-компонента?
- Что такое React.Memo? Отличия от useMemo?
- Какие ещё хуки используются для оптимизации работы React?
- Как я реализовал бы сложную форму на React? Formik, или custom hooks + MobX.
- TypeScript — нужен ли на проекте?
- TypeScript — какими возможностями пользуюсь?
- Различия между `any` и `unknow` в TS
- Настройки использования TypeScript в проекте — включаю ли поддержку `any`?
- Настройки использования TypeScript в проекте — включаю ли `strict node check` — не позволяет присваивать занчение `undefined`

<br></p>
</details> 

[//]: # («Kamaz» цифровая платформа, Frontend developer React middle — переаттестация)
<details><summary><b>«Kamaz» цифровая платформа, Фронтенд разработчик — переаттестация</b></summary><p>

  - GIT
    - стратегии слияния merge
    - head
    - конфликты
    - git add
  - JS
    - асинхроннность. Что такое окружение. Куча и стэк в  в эвент лупе
    - почитать про garbage collector (You don't know JS)
    - класс, объекты, ООП, 
    - инстансы
    - создание объекта через функции-конструкторы
    - как рабоатет класс в JS  
    - Модификаторы доступов классов - public, protected, private  в TS через декораторы/ ключевые слова
  - React - singleton
  
  - Задачки
    - промисы в консоль лог
    - Promise.all написать без promis.all
    - были ещё несколько задачек

<br></p>
</details> 

<br></p>
</details> 

[//]: # (Популярные задачки)
<details><summary><b>Популярные задачки</b></summary><p>

См [Legmo notes — Задачки для собеседования frontend](InterviewTasks.md)

<br></p>
</details> 

[//]: # (Алгоритм подготовки к собеседованию)
<details><summary><b>Алгоритм подготовки к собеседованию</b></summary><p>

- Изучить описание вакансии. Выписать технологии, повторить
- Просмотреть заметки [Lebmo notes](https://github.com/Legmo/notes). Знать что в каком файле лежит.
- Повторить темы из этого файла («Подборки вопросов-ответов для собеседования разработчика»). Особенно разделы:
  - «Повторять»
  - «Из личного опыта»
  - «Популярные задачки»
  - остальные можно «просканировать»
- Перечитать свои резюме (hh.ru, linkedin, doc-файлы...)
- Почитать переписку с рекуртёром, посмотреть свои заметки по вакансии
- Полистать свои публичные проекты на GitHub — чтоб ответить на вопросы по своему коду
- Подготовить открытые вкладки — подглядывать на собеседовании (Legmo notes, learnjs, mdm, reactjs.org, свои резюме, вакансия)
- Открыть редактор с JS кодом — набирать-проверять код. Например [plnkr.co](https://plnkr.co/edit/jXj1QgBx0iPp8IAh)
- Подготовить свои достижения/неудачи. Яркие, красивые примеры из своего рабочего опыта — какую выгоду получила ваша предыдущая компания от вашей деятельности, как вы помогли спасти ее от кризиса, как вы вывели ее в лидеры и т.д.
- Можно поискать в сети — как проходит собеседование в эту компании. Что спрашивают. Какие задачки задают.
- Если дали тестовое задание — поискать его на [GitHub](https://github.com), вероятно кто-то уже делал и выкладывал код своего решения.
- Полистать код тестовых заданий, которые делал для других компаний
- Пересмотреть [IT-Kamasutra #100 - Теория ReactJS + Redux за 90 минут](https://youtu.be/0AohM_oOjBc)
- Можно потренироваться в live coding
  - [leetcode.com](http://leetcode.com/)
  - [hackerrank.com](https://www.hackerrank.com/)
  - [codewars.com](https://www.codewars.com/)
  - [codingame.com](https://www.codingame.com)
  - [coderbyte.com](https://coderbyte.com/)
  - [Топ 8 лучших ресурсов для практики программирования в 2018](https://habr.com/ru/post/414009/)

<br></p>
</details> 

[//]: # (Уточнить у рекуртёра перед собеседованием)
<details><summary><b>Уточнить у рекуртёра перед собеседованием</b></summary><p>

- Сколько этапов? На этапе Х отсеиваются люди?
- Собеседование будет на русском? Предусмотрено какое-то общение на английском?
- Длительность?
- Какая платформа (Скайп, Zoom, Телемост...)?
- Видео потребуется?
- Сколько человек кроме меня участвует в собеседовании? Кто они?
- Есть примерный список тем/технологий, которые будем обсуждать?
- Будет ли какой-то live-coding?

- <br></p>
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
- [WebDev — Front-end. Вопросы на собеседовании»](https://trello.com/c/8TmMddqP/53-front-end-%D0%B2%D0%BE%D0%BF%D1%80%D0%BE%D1%81%D1%8B-%D0%BD%D0%B0-%D1%81%D0%BE%D0%B1%D0%B5%D1%81%D0%B5%D0%B4%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B8)

<br>
<br>

![](/Assets/Img/humor_js-interview-1.png)

<br>
<br>

*[Legmo, 2019-2023](https://github.com/Legmo/notes/)*