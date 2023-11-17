<h1>Паттерны проектирования</h1>

[//]: # (Общее)
<details><summary><b>Общее</b></summary><p>

  - Повторяемая архитектурная конструкция, представляющая собой решение проблемы проектирования в рамках некоторого часто возникающего контекста.
  - Наиболее известны 23 классических шаблона проектирования
  - Описаны в книге «Приёмы объектно-ориентированного проектирования. Паттерны проектирования» (банда четырёх - Эрих Гамма, Ричард Хелм, Ральф Джонсон, Джон Влиссидес)

<br></p>
</details>


**Основные шаблоны (Fundamental)**

- `Шаблон делегирования` (Delegation pattern) - Объект внешне выражает некоторое поведение, но в реальности передаёт
  ответственность за выполнение этого поведения связанному объекту.
- `Шаблон функционального дизайна` (Functional design) - Гарантирует, что каждый модуль компьютерной программы имеет
  только одну обязанность и исполняет её с минимумом побочных эффектов на другие части программы. н/д
- `Неизменяемый интерфейс` (Immutable interface) - Создание неизменяемого объекта. н/д
- `Интерфейс` (Interface) - Общий метод для структурирования компьютерных программ для того, чтобы их было проще понять.
  н/д
- `Интерфейс-маркер` (Marker interface) - В качестве атрибута (как пометки объектной сущности) применяется наличие или
  отсутствие реализации интерфейса-маркера. В современных языках программирования вместо этого могут применяться
  атрибуты или аннотации. н/д
- `Контейнер свойств` (Property container) - Позволяет добавлять дополнительные свойства для класса в контейнер (внутри
  класса), вместо расширения класса новыми свойствами. н/д
- `Канал событий` (Event channel) - Расширяет шаблон Publish/Subscribe, создавая централизованный канал для событий.
  Использует объект-представитель для подписки и объект-представитель для публикации события в канале. Представитель
  существует отдельно от реального издателя или подписчика. Подписчик может получать опубликованные события от более чем
  одного объекта, даже если он зарегистрирован только на одном канале.

**Порождающие шаблоны (Creational)**<br>
шаблоны проектирования, которые абстрагируют процесс инстанцирования. Они позволяют сделать систему независимой от
способа создания, композиции и представления объектов. Шаблон, порождающий классы, использует наследование, чтобы
изменять инстанцируемый класс, а шаблон, порождающий объекты, делегирует инстанцирование другому объекту.

- `Абстрактная фабрика` (Abstract factory
- `Строитель` (Builder)
- `Фабричный метод` (Factory method)
- `Отложенная инициализация` (Lazy initialization)
- `Объектный пул` (Object pool)
- `Прототип` (Prototype)
- `Получение ресурса есть инициализация` (Resource acquisition is initialization (RAII))
- `Одиночка` (Singleton)

**Структурные шаблоны (Structural)**<br>
определяют различные сложные структуры, которые изменяют интерфейс уже существующих объектов или его реализацию,
позволяя облегчить разработку и оптимизировать программу.

- `Адаптер` (Adapter / Wrapper)
- `Мост` (Bridge)
- `Компоновщик` (Composite)
- `Декоратор` или `Обёртка` (Decorator/Wrapper)
- `Фасад` (Facade)
- `Единая точка входа` (Front controller)
- `Приспособленец` (Flyweight)
- `Заместитель` (Proxy)

[//]: # (Поведенческие шаблоны (Behavioral))
<details><summary><b>Поведенческие шаблоны (Behavioral)</b></summary><p>

- Определяют взаимодействие между объектами, увеличивая таким образом его гибкость
- 
- `Цепочка обязанностей` (Chain of responsibility) — [Описание 1](https://refactoring.guru/ru/design-patterns/chain-of-responsibility), [Описание 2](https://makarov-ivan.gitbook.io/patterns/patterns/behavioral-patterns/chain-of-responsibility)
- `Команда` (Action, Transaction Command) — [Описание 1](https://refactoring.guru/ru/design-patterns/command), [Описание 2](https://makarov-ivan.gitbook.io/patterns/patterns/behavioral-patterns/command)
- `Интерпретатор` (Interpreter)
- `Итератор` (Cursor Iterator) — [Описание 1](https://refactoring.guru/ru/design-patterns/iterator), [Описание 2](https://makarov-ivan.gitbook.io/patterns/patterns/behavioral-patterns/iterator)
- `Посредник` (Mediator) — [Описание 1](https://refactoring.guru/ru/design-patterns/mediator), [Описание 2](https://makarov-ivan.gitbook.io/patterns/patterns/behavioral-patterns/mediator)
- `Хранитель` (Memento, Опекун, Наблюдатель) — [Описание 1](https://refactoring.guru/ru/design-patterns/memento), [Описание 2](https://makarov-ivan.gitbook.io/patterns/patterns/behavioral-patterns/memento)
- `Null Object` ()
- `Слуга` (Servant)
- `Спецификация` (Specification)
- `Состояние` (State) — [Описание 1](https://refactoring.guru/ru/design-patterns/state), [Описание 2]()
- `Стратегия` (Strategy) — [Описание 1](https://refactoring.guru/ru/design-patterns/strategy), [Описание 2](https://makarov-ivan.gitbook.io/patterns/patterns/behavioral-patterns/strategy)
- `Шаблонный метод` (Template method) — [Описание 1](https://refactoring.guru/ru/design-patterns/template-method), [Описание 2](https://makarov-ivan.gitbook.io/patterns/patterns/behavioral-patterns/tamplate-method)
- `Посетитель` (Visitor) — [Описание 1](https://refactoring.guru/ru/design-patterns/visitor), [Описание 2](https://makarov-ivan.gitbook.io/patterns/patterns/behavioral-patterns/visitor)
- `Простая политика` (Simple Policy)
- `Event listener` (Event listener)
- `Одноразовый посетитель` (Single-serving visitor)
- `Иерархический посетитель` (Hierarchical visitor )
  
<br></p>
</details>


[//]: # (Ссылки)
<details><summary><b>Ссылки</b></summary><p>

  - [Habr - Паттерны ООП в метафорах](https://habr.com/ru/post/136766/)
  - [Шпаргалка по шаблонам проектирования](https://habr.com/ru/post/210288/)
  - [Wiki - Шаблон проектирования](https://ru.wikipedia.org/wiki/%D0%A8%D0%B0%D0%B1%D0%BB%D0%BE%D0%BD_%D0%BF%D1%80%D0%BE%D0%B5%D0%BA%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F)
  - [Doka - Архитектура и паттерны проектирования](https://doka.guide/js/architecture-and-design-patterns/)
  - [Doka - Порождающие паттерны](https://doka.guide/js/design-patterns-creational/)
  - [Doka - Структурные паттерны](https://doka.guide/js/design-patterns-structural/)
  - [Doka - Поведенческие паттерны](https://doka.guide/js/design-patterns-behaviorial/)
  - .
  - [refactoring.guru](https://refactoring.guru/ru)
  
<br></p>
</details>

<br> 
<br> 

*[Legmo, 2019-2022](https://github.com/Legmo/notes/)*
