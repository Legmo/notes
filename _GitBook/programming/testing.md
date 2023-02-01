# Тестирование

<details>

<summary><strong>Зачем тестировать свой код</strong></summary>

* ты продумываешь детали еще до реализации, это помогает абстрагироваться от кода и уловить непонятные моменты в ТЗ на самом раннем этапе
* помогают наладить коммуникацию между разными членами команды: разработчиком, тестировщиком, менеджером и тд.
* раньше отлавливаются ошибки в коде, а чем раньше поймана бага, тем дешевле ее пофиксить
* меньше переходов туда-обратно таска от разработчика к тестировщику, значит, таски быстрее доедут до прода и меньше придется переключаться между тасками
* разгружаете своих ручных тестировщиков. Регрессионное тестирование — процесс очень трудоемкий. Если все покрыто автотестами, им достаточно просто описать тест-кейсы, код могут написать автоматизатор или разработчик
* можно смелее делать рефакторинг
* хорошие тесты — это еще и документация, и они помогают быстрее адаптироваться новым членам команды
* очень важно при использовании Agile-методик потому что они подразумевают `непрерывную интеграцию (CI)` и `непрерывную доставку (Continuous Delivery/CD)` — слитый merge-request сразу идёт в production. Автоматизированные сборки, автоматизированное тестирование и т.д.

\


</details>

<details>

<summary><strong>Типы автоматизированного тестирования</strong></summary>

Существует сразу несколько различных типов автоматизированного тестирования программного обеспечения.\
Это - некоторые из наиболее распространенных

* `Unit-тестирование` — проверка работы отдельных модулей по отдельности. Изолированно тестируем мин. сущности.\
  Компонентное/Модульное/Unit тестирование часто смешивают, точную разницу установить трудно.\
  При юнит-тестировании мы используем реальные объекты и драйверы как функциональные параметры, в модульном тестировании Юнит-тестами называют проверки отдельных классов нашего приложения, и это `техника белого ящика`.\
  – как особые значения.Классы это тоже «составная часть, элемент чего-либо» => юнит-тестирование — это разновидность компонентного тестирования, чаще всего используемая разработчиками.\

* `Модульное тестирование` — проверка работы отдельных модулей по отдельности. Например: конкретная функция возвращает ожидаемое значение, и предоставляет некоторые известные входные данные.\

* `Компонентное тестирование` — проверяем работу отдельного компонента. Каждый компонент должен находиться в независимом и контролируемом состоянии.\
  Тестирование составных частей программы по отдельности, изолированно.\
  Модульное тестирование от компонентного отличается тем, что в компонентном используют реальные объекты и драйверы, а в модульном – конкретные значения.\

* `Тест на «запах дыма»` — для проверки работоспособности системы. Например, в React - приложении мы можем визуализировать основной компонент приложения и вызывать его через день. Если он отображается правильно, мы можем быть уверены в том, что наше приложение будет отображаться в браузере.\

* `Интеграционный тест` — для проверки того, что два модуля (или более) могут хорошо работать вместе. Например, можно запустить тест, чтобы убедиться, что сервер и база данных действительно обмениваются данными.\

* `Функциональный тест` — для проверки того, что система соответствует своей функциональной спецификации.\

* `Сквозное тестирование` — использует приложение так же, как оно будет использоваться в реальном мире. Вы можете использовать такой инструмент, как cypress для E2E тестов.\

* `Приемочный тест` — Обычно подобный тест осуществляет владелец бизнеса, чтобы убедиться в том, что система соответствует спецификациям.\

* `Тест производительности` — чтобы увидеть, как система работает при значительной нагрузке. В веб-интерфейсе речь обычно идет о том, как быстро приложение загружается в браузер пользователя.

**Ссылки**

* [Как протестировать React-приложения с помощью React Testing Library](https://www.internet-technologies.ru/articles/test-react-priloz-s-pom-react-testing-library.html)
* [Модульное, компонентное и юнит-тестирование](https://natalyarukol.ru/2011/05/15/modulnoe-komponentnoe-i-yunit-testir/)
* [Модульное/юнит/компонентное тестирование](https://github.com/VladislavEremeev/QA\_bible/blob/master/vidy-metody-urovni-testirovaniya/modulnoe-yunit-komponentnoe-testirovanie-module-unit-component-testing.md)

\


</details>

<details>

<summary><strong>Unit тесты</strong></summary>

Проверка работы отдельных модулей самих по себе. Тестируем минимальные сущности по отдельности.

Например:

* Отдельно проверяем наличие кнопки на экране
* Отдельно проверяем какой текст на ней выводится
* Отдельно проверяем корректно ли работает её нажатие

\


</details>

<details>

<summary><strong>Snapshot тесты</strong></summary>

Тесты, которые делают скриншот экрана (эталонный скриншот) и сравнивают с актуальным скриншотом, который делается во время прогона тестов.

\


</details>

<details>

<summary><strong>MOCK, STUB и SPY</strong></summary>

При тестировании часто приходится заменять настоящие объекты «заглушками», чтобы тесты были проще и прямолинейнее.\
Два основных вида таких «заглушек»:

* `Stub` — заменяют объекты, но сами ничего не проверяют.
  * Их реализация простая, а зачастую — даже ничего не делает вовсе.
  * Нужны, чтобы заменить собой зависимость в системе и упростить окружение для тестов.
* `Mock` — тоже заменяют зависимости, но при этом позволяют проверять предположения.
  * Могут следить за вызовами методов, аргументами этих вызовов и т. д.
  * Моки удобны при тестировании функций с побочными эффектами
* `Spy` — следят за тем, какие функции у зависимостей вызываются.
  * По желанию могут также имитировать возвращаемые значения для этих методов
  * можно рассматривать как разновидность `Mock`

`Фиктивные объекты` — объекты-заменители зависимостей для тестируемых функций. Они реализуют те же интерфейсы, что и настоящие зависимости, но сильно проще в реализации.

Фиктивные объекты можно представить как беговые дорожки, которые заменяют собой настоящий большой парк. Только стабы — это дорожки попроще: крутящаяся лента без дисплея и настроек; а моки — дорожки, которые следят за темпом, ускорением, сердцебиением и т.д.

И стабы, и моки помогают избежать «постройки целого парка» при тестировании, но стабы нужны лишь для того, чтобы просто было, где бегать, а моки — чтобы знать, как именно проходила пробежка.

**«Если можно не мокать — лучше не мокать»** — чем меньше инфраструктуры для тестирования и объектов, за которыми надо следить и обновлять, тем быстрее и проще будет проходить работа с тестами.

**Ссылки**

* [Дока - Фиктивные объекты и данные, моки, стабы](https://doka.guide/js/testing-and-fake-objects/)

\


</details>

<details>

<summary><strong>TDD</strong></summary>

`Test Driven Development` — разработка через тестирование Подход, когда вначале пишутся тесты, а потом разрабатывается кусок программы из удовлетворяющий Хорошо подходит для `юнит-тестирования` (проверка работы отдельных модулей самих по себе). `TDD` проверяет работу функций.

**Юнит-тесты**\
Система состоит из маленьких блоков, функций (компоненты, селекторы, редьюсеры...). Каждый из них тестируем

**Преимущества**\


* Программа будет удобной (в частности её интерфейсы) — мы начинаем ей пользоваться до того как создали. А не «создали, теперь придумаем как её удобно использовать»
* Будет стройная модульная архитектура (иначе тестами не покроешь)
* Будет 100% покрытие тестами
* Тестирование и дебаг становится простым
* Можем отследить что возникли какие-то сайд-эффекты и побочные баги в связи с вводом новой функциональности. Есть 5 фич, все работают. Добавили шестую - одна из первых пяти сломалась. Так могли бы и не заметить - но тесты выявят проблему.
* В результате время на разработку уменьшается, т.к. правок меньше, режим дебага упрощается и логика изначально продумывается лучше.

**Недостатки**

* если заказчик не сказал точные требования - затраты времени будут большими. Когда даже ещё непонятно - как это будет работать (сегодня сказали «сделайте желтое», завтра: «пофиг на цвет, делайте прямоугольное»).

\


</details>

<details>

<summary><strong>BDD</strong></summary>

`Behavior Driven Development` — разработка на основе поведения Расширение TDD-подхода. Хорошо подходит для тестирования `интеграционного` (как отдельные модули работают друг с другом) и `e2e` (проверка всей системы целиком). `BDD` проверяет пользовательские сценарии.

\


</details>

<details>

<summary><strong>Различия TDD/BDD</strong></summary>

* `TDD` хорошо подходит для юнит-тестирования, т.е. для проверки работы отдельных модулей самих по себе.
* `BDD` хорошо подходит для тестирования `интеграционного` (как отдельные модули работают друг с другом) и `e2e` (проверка всей системы целиком).
* `TDD`: тесты сразу реализуются в коде,
* `BDD` чаще всего описываются шаги на языке, понятном всем, а не только разработчикам.
* `TDD`: юнит-тесты пишут сами разработчики.
* `BDD` требует объедения усилий разных членов команды. Обычно тест-кейсы (шаги) описываются ручным тестировщиком или аналитиком и воплощаются в код тестировщиком-автоматизатором. В нашей команде мы (фронтенедеры) описываем шаги вместе с тестировщиками, а код тестов пишет фронтенд-команда.
* `TDD` проверяет работу функций
* `BDD` проверяет пользовательские сценарии.

\


</details>

<details>

<summary><strong>JEST</strong></summary>

Среда запуска тестов JavaScript, фрэймворк.\
В `CreateReactApp` встроена изначально.

Разработана Facebook

Это фреймворк, разработанный с учетом простоты и предлагающий мощный и элегантный API для создания изолированных тестов, сравнения снимков, фиксации, покрытия тестами и многого другого.

Jest — это раннер на основе Node. Это означает, что тесты всегда выполняются в среде Node, а не в реальном браузере.

* [Hexlet - JS: React. Тестирование](https://ru.hexlet.io/courses/js-react/lessons/tests/theory\_unit)
* [Habr - React: тестируем компоненты с помощью Jest и Testing Library](https://habr.com/ru/company/timeweb/blog/670480/)
* [Тестирование компонентов в React с использованием Jest: основы](https://code.tutsplus.com/ru/articles/testing-components-in-react-using-jest-the-basics--cms-28934)
* [IT-Kamasutra #92 - Тестируем компоненты, тесты, react-test-renderer](https://youtu.be/Kyc\_Z\_2b2Hc)
* [IT-Kamasutra #92 - как протестить APP](https://youtu.be/Kyc\_Z\_2b2Hc?t=1653)
* [Habr - React: тестируем компоненты с помощью Jest и Testing Library](https://habr.com/ru/company/timeweb/blog/670480/)
* [Hexlet - Unit-тестирование React](https://ru.hexlet.io/courses/js-react/lessons/tests/theory\_unit)
* [Тестирование компонентов в React с использованием Jest: основы](https://code.tutsplus.com/ru/articles/testing-components-in-react-using-jest-the-basics--cms-28934)
* [Как протестировать React-приложения с помощью React Testing Library](https://www.internet-technologies.ru/articles/test-react-priloz-s-pom-react-testing-library.html)

**Пример**

```js
describe('ProductHeader', () => {

  it('passing test', () => {
    expect(true).toBeTruthy();
  })

  it('failing test', () => {
    expect(false).toBeTruthy();
  })
})
```

**Описание**

* Набор тестов начинается с блока `describe` — глобальная функция Jest, принимает два параметра:
  * название набора тестов,
  * фактическая реализация.\

*   `it()` — каждый `it()` в наборе тестов соответствует тесту или спецификации.\


    * ```js
      it('failing test', () => {
         expect(false).toBeTruthy();
      })
      ```

    ```
    ```
* `matchers` — сопоставители для сравнения значений. Используются для проверки равенства, сравнения двух чисел или строк и проверки правильности выражений.
  * Список популярных матчей в Jest:
    * toBe();
    * toBeNull()
    * toBeDefined()
    * toBeUndefined()
    * toBeTruthy ()
    * toBeFalsy()
    * toBeGreaterThan()
    * toBeLesserThan()
    * toMatch()
    * toContain()
  * [Справочник](https://jestjs.io/docs/en/using-matchers)
  * Пример:
    * ```js
      test('two plus two is four', () => {
        expect(2 + 2).toBe(4);
      });
      ```
* `expects` — ожидание. Утверждение, которое либо возвращает `true` / `false`.
  * Когда все утверждения в спецификации верны, говорят, что они прошли. В противном случае тест считается неудачным.
  * Тест содержит одно или несколько ожиданий, которые проверяют состояние кода.\

  * `expects(true).toBeTruthy();`
* Запуск набора тестов в «Create React APP» - `yarn test`

\


</details>

<details>

<summary><strong>Enzyme и React Testing Library</strong></summary>

Когда дело доходит до тестирования React-приложений, есть сразу несколько возможных вариантов, наиболее распространенными из которых являются `Enzyme` и `React Testing Library`.

**React Testing Library**

Библиотека для тестирования JavaScript, созданная специально для тестирования компонентов React.\
Имитирует взаимодействие пользователя с изолированными компонентами и утверждает их выходные данные, чтобы гарантировать правильное поведение пользовательского интерфейса.

В `CreateReactApp` надо устанавливать отдельно?\
Официальная рекомендация команды разработчиков React.

Если вы хотите протестировать компоненты отдельно от дочерних компонентов, которые они отображают, мы рекомендуем использовать react-testing-library. react-testing-library— это библиотека для тестирования компонентов React таким образом, чтобы они были похожи на то, как эти компоненты используются конечными пользователями. Он хорошо подходит для модульного, интеграционного и сквозного тестирования компонентов и приложений React. Он работает более непосредственно с узлами DOM, и поэтому рекомендуется использовать с jest-dom для улучшенных утверждений.

React Testing Library является подмножеством семейства пакетов @testing-library. Ее философия очень проста. Вашим пользователям все равно, используете ли вы redux или context для управления состоянием. Они меньше заботятся о простоте хуков или о различии между классом и функциональными компонентами. Они просто хотят, чтобы приложение работало определенным образом. Поэтому не удивительно, что основным руководящим принципом этой библиотеки является:

«Чем больше ваши тесты похожи на то, как используется ваше программное обеспечение, тем больше уверенности они могут вам дать».

Поэтому, что бы вы ни делали, помните о конечных пользователях и тестируйте приложение так, как они будут его использовать или уже используют.

Выбор React Testing Library предоставляет целый ряд преимуществ. Во-первых, с ней гораздо легче начать работать. Каждый новый проект React, загруженный с помощью Create-React-App,поставляется с настроенными React Testing Library и Jest. Документация React также рекомендует этот инструмент в качестве библиотеки тестирования. Наконец, руководящий принцип имеет большой смысл - функциональность, а не детали реализации.

\


</details>

<details>

<summary><strong>Тестирование React-component</strong></summary>

См. «React - Тестирование React-component»

\


</details>

<details>

<summary><strong>Ссылки</strong></summary>

* [Что такое TDD и BDD на пальцах, и что должен знать о них фронтендер](https://medium.com/@lucyhackwrench/%D1%87%D1%82%D0%BE-%D1%82%D0%B0%D0%BA%D0%BE%D0%B5-tdd-%D0%B8-bdd-%D0%BD%D0%B0-%D0%BF%D0%B0%D0%BB%D1%8C%D1%86%D0%B0%D1%85-%D0%B8-%D1%87%D1%82%D0%BE-%D0%B4%D0%BE%D0%BB%D0%B6%D0%B5%D0%BD-%D0%B7%D0%BD%D0%B0%D1%82%D1%8C-%D0%BE-%D0%BD%D0%B8%D1%85-%D1%84%D1%80%D0%BE%D0%BD%D1%82%D0%B5%D0%BD%D0%B4%D0%B5%D1%80-701a10e06bb9)
* [IT-ликбез из тачилы. TDD - Разработка посредством тестирования](https://youtu.be/LGgMD\_Evz\_M)
* [IT-Kamasutra #89 - Тесты, jest, tdd, тестируем reducer - React JS](https://youtu.be/fJlx8B9cU7w)
* [https://learn.javascript.ru/testing-mocha - Автоматическое тестирование c использованием фреймворка Mocha](https://learn.javascript.ru/testing-mocha)

\


</details>