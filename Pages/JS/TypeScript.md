<h1>TypeScript</h1>

[//]: # (Общая информация)
<details><summary><b>Общая информация</b></summary><p>

- Разрабатывается с конца 2012
- Разрабатывается в Microsoft, но OpenSource
- Андерс Хейлсберг — создатель таких языков как Delphi, C#
- Angular 2+ и Vue3 полностью написаны на TypeScript

**Что это**

- Типизированное надмножество JavaScript — любая программа на JS является программой на TypeScript. Код на TS
  компилируется в JS.
- Строго типизированный и компилируемый язык (ближе к Java, C# и другим строго типизированным языкам).

**Зачем**

- Строгая типизация уменьшает количество потенциальных ошибок, которые могли бы возникнуть при разработке на JavaScript.
- Реализует в JS многие концепции, которые свойственны объектно-ориентированным языкам, как, например, наследование,
  полиморфизм, инкапсуляция и модификаторы доступа и так далее.
- Позволяет быстрее и проще писать большие сложные комплексные программы. Их легче поддерживать, развивать,
  масштабировать и тестировать, чем на стандартном JavaScript.

<br></p>
</details>

[//]: # (Типы переменных)
<details><summary><b>Типы переменных</b></summary><p>

- `number` - числа
- `string` - строки, в т.ч. шаблонные
- `boolean` - логическое значение
- `symbol` - symbol в js
- `null`  - null в js (*в js typeof null = object, так сложилось исторически*)
- `undefined` - undefined в js
- `never` - ТS only. Представляет отсутствие значения. Для типизации ответа функций, которые генерируют или возвращают
  ошибку. Или если в функции бесконечный цикл
- `void` - ТS only. Определят отсутствующие типы. Для типизации ответа функций, которые не возвращают ничего (нет
  return)
- `object`
- `array` - массивы (*number[] или `Array<number>`*)
- `tuple` - кортежи. Массивы в которых могут быть разные типы данных (*let x: [string,number]*)
- `enum` - перечисления. Задание понятных имён набору численных значений
- `any` - что угодно (ключевое слово)
- Void
- Object
- Function - представляет объект с методами bind, call, apply.
- Alias - псевдоним для своего типа
- Union - или (|)
- Discriminated
  Union https://medium.com/nuances-of-programming/typescript-%D0%BE%D1%81%D0%BD%D0%BE%D0%B2%D1%8B-728e88888723
- Intersection - и (&)
- Inference - автоматическое определние типа
- Assertion - as

**Ссылки**

- [WebDev - TypeScript. Базовые типы 1 (YouTube)](https://youtu.be/iugNHvMWBw4)
- [WebDev - TypeScript. Базовые типы 2 (YouTube)](https://youtu.be/MNcl1Fni4cw)

<br></p>
</details>

[//]: # (type - Псевдонимы типов, Allias)
<details><summary><b>type (Псевдонимы типов). Allias</b></summary><p>

- `type id = number | string;`
- псевдоним = Allias
- полезны для работы со сложными объектами `{name: string; age: number}`

<br></p>
</details>

[//]: # (& - Расширения)
<details><summary><b>& (Расширения)</b></summary><p>

- В одном типе можно заимствовать или расширять код других типов, при помощи операции `&`
  - ```ts
      type Person = {name: string; age: number};
      type Employee = Person & {company: string};
    ```

<br></p>
</details>

[//]: # (union - Объединения)
<details><summary><b>union (Объединения)</b></summary><p>

- `a | b` - позволяет комбинировать или объединить другие типы

<br></p>
</details>

[//]: # (? - Опциональные аргументы)
<details><summary><b>?(Опциональные аргументы)</b></summary><p>

- `let person: { name: string; age?: number };` - свойство age необязательное

<br></p>
</details>

[//]: # (Typeof - Определение типа)
<details><summary><b>Typeof (Определение типа)</b></summary><p>

- Команда (оператор) `typeof` работает только с базовыми типами данных.

<br></p>
</details>

[//]: # (Instanceof - Определение типа)
<details><summary><b>Instanceof (Определение типа)</b></summary><p>

- Работает почти так же, как `typeof`. Отличие в том, что может определять не только базовые типы, но и собственные..

<br></p>
</details>

[//]: # (Type assertion. As - Преобразование к типу)
<details><summary><b>Type assertion. As (Преобразование к типу)</b></summary><p>

- модель преобразования значения переменной к определенному типу
- есть две формы приведения
  - с применением оператора `as`: `const header = document.getElementById("header") as HTMLElement;`
  - угловыми скобками: `const header = <HTMLElement>document.getElementById("header");`. Перед значением в угловых
    скобках указывается тип, к которому надо выполнить приведение. Так, в данном случае мы получаем объект типа
    HTMLElement
- такие преобразования будут иметь силу, если мы точно знаем, что значение может быть преобразовано к целевому типу.
  Например, на странице есть элемент с id=header, поэтому мы можем преобразовать значение к типу HTMLElement. Если
  такого элемента нет, то во время выполнения мы получим ошибку.

<br></p>
</details>

[//]: # (Оператор in)
<details><summary><b>Оператор in</b></summary><p>

- Оператор in позволяет проверить наличие определенного свойства в объекте. Он возвращает true, если свойство есть в
  объекте, и false, если свойство отсутствует
  - ```ts
    function printUser(user: { name: string; age?: number }){
       if("age" in user){
        console.log(`Name: ${user.name} Age: ${user.age}`);
       }
       else{
        console.log(`Name: ${user.name}`);
       }
    }
    ```

<br></p>
</details>

[//]: # (Массивы)
<details><summary><b>Массивы</b></summary><p>

- `тип_элементов_массива[]` или `Array<тип_элементов_массива>`
- являются строго типизированными. Если изначально массив содержит строки, то в будущем сможет работать только со
  строками.
- с помощью индексов можно обращаться к элементам массива.
- ReadonlyArray - тип массивов, элементы которых нельзя изменять. `ReadonlyArray<тип_элементов_массива>`
  - `const people: ReadonlyArray<string> = ["Tom", "Bob", "Sam"];`
  - `const people: readonly string[]= ["Tom", "Bob", "Sam"];`
- массивы поддерживают декомпозицию на константы и переменные. https://metanit.com/web/typescript/2.9.php

<br></p>
</details>

[//]: # (Tuples - Кортежи)
<details><summary><b>Tuples - Кортежи</b></summary><p>

- Массивы, которые могут хранить значения разных типов. `let user: [string, number];`
- Кортежи могут иметь необязательные элементы, для которых можно не предоставлять значение. Чтобы указать, что элемент
  является необязательным, после типа элемента ставится `?`
  - ```ts
      let bob: [string, number, boolean?] = ["Bob", 41, true];
      let tom: [string, number, boolean?] = ["Tom", 36];
    ```
- многоточие - С помощью оператора `...` внутри определения типа кортежа можно определить набор элементов, количество
  которых неопределено. Например:
  - ```ts
      let math: [string, ...number[]] = ["Math", 5, 4, 5, 4, 4];
      let physics: [string, ...number[]] = ["Physics", 5, 5, 5];
    ```
- readonly - озволяет создавать кортежи только для чтения, элементы которого нельзя
  изменить `const tom: readonly [string, number] = ["Tom", 36]; `

<br></p>
</details>

[//]: # (Наполнение параметров - ...)
<details><summary><b>Наполнение параметров (...)</b></summary><p>

**Наполнение параметров**

- TypeScript позволяет использовать массивы для передачи данных сразу нескольким
  параметрам. https://metanit.com/web/typescript/2.12.php
  - ```ts
      const numbers = [1, 3, 5, 7, 9] as const;
      let num = sum(...numbers);
    ```

<br></p>
</details>

[//]: # (enum - Перечисления)
<details><summary><b>enum (Перечисления)</b></summary><p>

- Задание понятных имён набору численных значений
- ```ts
    enum Directions {
      Up, //0
      Down = 1,
      Left = 4,
      Right, //5
    }
  ```
- можно получать ключ по значению (`Directions.Up // 0`, `Directions['Up'']`)
- можно получать значение по ключу (`Directions[0] // 'Up'`) = Reverse Enum

- можно задавать свои индексы вместо чисел
- ```ts
    enum Links {
      vk = 'https://vk.com/',
      facebook = 'https://facebook.com/',
      youtube = 'https://youtube.com/',
    }
  ```
- теперь `Links[0]` или `Links['https://vk.com/']` не сработает
- сработает `Links.vk` или `Links['vk']`

**Константные перечисления**

- ссылки к enum всегда выполняются как доступы к свойству, и никогда не встраиваются. Т.е. написав enum, и описав его
  перечисляемые значения вы всегда получите генерацию объекта через функцию. Даже если этот объект не будет
  использоваться
- если надо оптимизировать ресурсы и мощности - используем константные перечисления. Тогда мы получим соответствующие
  значения только при обращении к опр. элементу enum. Генерации объекта при этом не происходит
- ```ts
  const enum Links {
  vk = 'https://vk.com/',
  facebook = 'https://facebook.com/',
  youtube = 'https://youtube.com/',
  }
  ```

- позволяет определить набор именованных констант, которые описывают определенные состояния.
- существует возможность создавать текстовые и числовые константы.

  **Ссылки**
- https://metanit.com/web/typescript/2.11.php
- [WebDev - TypeScript. Базовые типы 2 (YouTube)](https://youtu.be/MNcl1Fni4cw?t=200)
- [WebDev - TypeScript. Перечисления Enums (YouTube)](https://youtu.be/FltLrtKWMak)

<br></p>
</details>

[//]: # (Generic - Дженерики)
<details><summary><b>Generic (Дженерики)</b></summary><p>

- Создать массив можно с помощью дженерик-типа (обобщённого типа), написав `Array<Type>`
- `let numbers: Array<number> = [1, 2, 3, 4, 5]` Этот код создаёт числовой массив, содержащий 5 элементов.
- Дженерики (англ. generics) позволяют создавать компоненты, которые совместимы с большим количеством типов, а не только
  с одним. Это делает компоненты более «открытыми».
- Возможно у вас возникнет вопрос: а почему бы не использовать тип any для взятия сразу нескольких типов? Рассмотрев
  пример ниже, можно это легко понять.
- Допустим, нужно создать какую-нибудь функцию, которая возвращает переданный ей параметр:
- `function dummyFun(arg: any): any {return arg;}`
- Хоть any и является обобщающим типом, у него есть одно отличие. При использовании типа any у вас не получится узнать
  оригинальный тип передаваемой переменной. Ниже приведён пример того, как можно это реализовать с помощью дженерика:
- `function dummyFun(arg: T): T {return arg}`
- В этом коде используется generic-параметр T, тип которого можно будет захватить и в дальнейшем использовать.
-
- Что делать, если я передаю аргумент с определенным типом и у меня должен быть выход с точно таким же типом Ответ: Для
  таких случаев существуют обобщенные типы, это и есть дженерики
- нужны, когда мы производим действия над сущностями с одинаковым типом

<br></p>
</details>

[//]: # (Интерфейсы)
<details><summary><b>Интерфейсы</b></summary><p>

-Интерфейсы содержат свойства и методы кастомного типа, но не содержат их реализацию. Реализацию берёт на себя класс,
реализующий интерфейс.

- Возможности, которые есть у интерфейсов, но нет у типов:
  - Декларативное расширение (мерджинг) - Если мы объявим два интерфейса с одинаковыми именами, то TypeScript
    автоматически "сплюснет" их в один:
  - Расширение интерфейсов - Расширением интерфейса называется процесс, когда один интерфейс поглощает все свойства
    родителя и добавляет свои:

<br></p>
</details>

[//]: # (Классы)
<details><summary><b>Классы</b></summary><p>

```ts
  class User {
  public name: string;
  private nickName: string;
  protected age: number = 20; //задано дефолтное значение
  readonly pass: number;

  constructor(name: string, nickName: string, age: number, pass: number) {
    this.name = name;
    this.nickName = nickName;
    this.age = age;
    this.pass = pass;
  }
}
```

- TypeScript предоставляет нам все те же классы, однако с некоторыми улучшениями, а именно:
  - Поля
  - Параметры только для чтения
  - Модификаторы доступа
  - Перегрузка конструкторов
  - Наследование классов, а также имплементация интерфейсов
  - Расширение классов
  - Дженерики в классах
  - Параметризированные свойства
  - Абстрактные классы и инстансы

**4 модификатора доступа**

- управляют доступностью к свойствам класса
- `public` - значение по умолчанию. Можно получить свободный доступ.
- `private` - не доступен за предеалми класса. Ни классам-наследникам, ни объектам созданным с помощью данного класса
- `protected` - доступен только наследникам
- `readonly` - доступен только для чтения

<br></p>
</details>

[//]: # (Модули)
<details><summary><b>Модули</b></summary><p>

- ```ts
    interface Person{ name: string }
    const person: Person = {name: 'Gabriel'}
    const person2: Person = {names: 'Gabriel'} // Тип Person не присваивается
  ```
- В примере выше в первом свойстве реализуется интерфейс Person. Попытка реализации интерфейса в переменной person2
  выбросит исключение.

**! Barrel**

- Barrel-файлы дают возможность свести нескольких экспортируемых модулей в один более удобный. Для этого достаточно в
  проекте создать отдельный файл, который будет экспортировать несколько модулей сразу.
- ```ts
    export * from './person';
    export * from './animal';
    export * from './human';
  ```
- И после этого можно одной строкой можно импортировать все эти модули
  вместе: `import { Person, Animal, Human } from 'index';`

<br></p>
</details>

[//]: # (Декораторы)
<details><summary><b>Декораторы</b></summary><p>

- https://metanit.com/web/typescript/6.1.php

<br></p>
</details>

[//]: # (Типизация функций)
<details><summary><b>Типизация функций</b></summary><p>

```ts
  let MyFunc: (someArgName: string) => void;

function otherFunc(name: string): void {
  alert(`Hello ${name}!`);
};

myFunc = otherFunc
```

<br></p>
</details>

[//]: # (Ссылки)
<details><summary><b>Ссылки</b></summary><p>

- [Официальный репозиторий на GitHub](https://github.com/Microsoft/TypeScript)
- [WebDev - Лекции по TypeScript (YouTube)](https://www.youtube.com/playlist?list=PLNkWIWHIRwMEm1FgiLjHqSky27x5rXvQa)
- [Metanit.com - Введение в TypeScript](https://metanit.com/web/typescript/1.1.php)
- [Книга и Справочник TypeScript](https://scriptdev.ru/)
- [It-Kamasutra - Путь самурая 2.0 (YouTube)](https://www.youtube.com/playlist?list=PLcvhF2Wqh7DM3z1XqMw0kPuxpbyMo3HvN)
- [TypeScript и React с использованием create-react-app: пошаговое руководство по настройке вашего первого приложения](https://dev-gang.ru/article/typescript-i-react-s-ispolzovaniem-create-react-app-poshagovoe-rukovodstvo-po-nastroike-vashego-pervogo-prilozhenija/)
- [Справочник TypeScript for React & Redux (piotrwitek)](https://github.com/piotrwitek/react-redux-typescript-guide)
- [Habr - Статическая и динамическая типизация (2016)](https://habr.com/ru/post/308484/?ysclid=l75ndzru2v460218152)
-
  +
- [tproger - Вводный курс по TypeScript](https://tproger.ru/translations/course-on-typescript/)
- [Medium - TypeScript: основы](https://medium.com/nuances-of-programming/typescript-%D0%BE%D1%81%D0%BD%D0%BE%D0%B2%D1%8B-728e88888723)
- [VC - Крупный гайд по TypeScript](https://vc.ru/dev/423888-krupnyy-gayd-po-typescript)

  <br></p>
</details>
<br>
<br>

*[Legmo, 2019-2022](https://github.com/Legmo/notes/)*