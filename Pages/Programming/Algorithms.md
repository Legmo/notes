<h1>Алгоритмы</h1>

[//]: # (Алогоритмическая сложность todo: доработать)
<details><summary><b>Алогоритмическая сложность</b></summary><p>

- Вычислительная сложность (алгоритмическая сложность) - понятие, обозначающее функцию зависимости объема работы алгоритма от размера обрабатываемых данных.
- Пытается ответить на центральный вопрос разработки алгоритмов: как изменится время исполнения и объем занятой памяти в зависимости от размера входных данных?

<br></p>
</details>

[//]: # (Big O нотация todo: доработать)
<details><summary><b>Big O нотация</b></summary><p>

- `Big O нотация` — нужна для описания сложности алгоритмов.
- Это мера эффективности «в худшем случае», верхняя граница того, сколько времени потребуется для выполнения задачи, или сколько памяти для этого необходимо. Например, поиск элемента в несортированном списке имеет значение O(n).
- 
- Алгоритмы описывают с помощью двух характеристик — «времени» и «памяти».
- **Время**
  - Когда говорят о `Time Complexity` — речь идёт именно о количестве операций.
  - Проблема: секунды, минуты и часы — это не очень показательные единицы измерения. 
  - Кроме того, время работы алгоритма зависит от железа, на котором он выполняется, и других внешних факторов. 
  - Поэтому время считают не в секундах и часах, а в `количестве операций, которые алгоритм совершит`.
  - в О-нотации на операции с одной или двумя переменными вроде i++, a * b, a / 1024, max(a,b) уходит всего одна единица времени.
- **Память**
  - объём оперативной памяти, который потребуется алгоритму для работы. 
  - Потребление памяти обычно называется `Space Complexity` или просто `Space`, редко `Memory`.
  - Одна переменная — это одна ячейка памяти, а массив с тысячей ячеек — тысяча ячеек памяти.
  - Все ячейки считаются равноценными. Например, int a на 4 байта и double b на 8 байт имеют один вес.
  - `in-place` — алгоритмы, которые используют исходный массив как рабочее пространство. Они потребляют мало памяти и создают одиночные переменные — без копий исходного массива и промежуточных структур данных. 
  - `out-of-place` — алгоритмы, требующие дополнительной памяти, называют. 
  - Прежде чем использовать алгоритм, надо понять, хватит ли на него памяти, и если нет — поискать менее прожорливые альтернативы.
- 
- При расчёте Big O Notation используют **два правила**:
  - Константы откидываются. 
    - Нас интересует только часть формулы, которая зависит от размера входных данных. Проще говоря, это само число n, его степени, логарифмы, факториалы и экспоненты, где число находится в степени n.
  - Если в O есть сумма, нас интересует самое быстрорастущее слагаемое. 
    - Это называется асимптотической оценкой сложности
- 
- **Сценарии работы алгоритмов**
  - У каждого алгоритма есть худший, средний и лучший сценарии работы — в зависимости от того, насколько удачно выбраны входные данные. Часто их называют случаями.
  - `Худший случай `(worst case)
    - rогда входные данные требуют максимальных затрат времени и памяти.
  - `Лучший случай` (best case) 
    - полная противоположность worst case, самые удачные входные данные.
    - Правильно отсортированный массив, с которым алгоритму сортировки вообще ничего делать не нужно. В случае поиска — когда алгоритм находит нужный элемент с первого раза.
  - `Средний случай` (average case) 
    - между best case и worst case, но далеко не всегда понятно, где именно. 
    - Часто он совпадает с worst case 
    - всегда хуже best case, если best case не совпадает с worst case. Да, иногда они совпадают.
    - Как определяют средний случай? Считают статистически усреднённый результат: берут алгоритм, прокручивают его с разными данными, составляют сводку результатов и смотрят, вокруг какой функции распределились результаты. В общем, расчёт average case — дело сложное.
- 
- **Как определяют сложность алгоритмов?**
  - `На глаз`
  - `Амортизационный анализ` (разновидность "На глаз")
    - если на X «дешёвых» операций (например, с O(1)) приходится одна «дорогая» (например, с O(n)), то на большом количестве операций суммарная сложность получится неотличимой от O(1).
  - `Мастре-теорема`
    - широко исползуют для оценки сложности рекурсивных алгоритмов.
    - По сути, это набор правил по оценке сложности. Он учитывает, сколько новых ветвей рекурсии создаётся на каждом шаге и на сколько частей дробятся данные в каждом шаге рекурсии. Это если вкратце.
  - `Метод Монте-Карло`
    - применяют довольно редко — только если первые два применить невозможно. Особенно часто с его помощью описывают производительность систем, состоящих из множества алгоритмов.
    - Суть метода: берём алгоритм и гоняем его на случайных данных разного размера, замеряем время и память. Полученные измерения выкладываем на отдельные графики для памяти и времени. А затем автоматически вычисляется функция, которая лучше всего описывает полученное облако точек.
- 
- **Сложность поплулярных алгоритмов**
  - Линейный поиск - сравнивать значения одно за другим. Работает с любыми массивами. Сложность  O(n^2)
  - Бинарный поиск - упорядочить массив, потом открыть по середине и смотреть - нужно больше или меньше. Телефонный справочник.  работает только с отсортированныйми массивами, Сложность  O(n)
- 
- **Какие ещё есть оценки сложности нотаций**
  - `Big O` обозначает верхнюю границу сложности алгоритма. Это идеальный инструмент для поиска worst case.
  - `Big Omega` (которая пишется как подкова) обозначает нижнюю границу сложности, и её правильнее использовать для поиска best case.
  - `Big Theta` (пишется как О с чёрточкой) располагается между О и омегой и показывает точную функцию сложности алгоритма. С её помощью правильнее искать average case.
  - `Small o` и `Small omega` находятся по краям этой иерархии и используются в основном для сравнения алгоритмов между собой.

- **Ссылки**
  - [Habr - Big O](https://habr.com/ru/post/444594/)
  - [Big O Notation: что это такое и как её посчитать](https://skillbox.ru/media/code/big-o-notation-chto-eto-takoe-i-kak-eye-poschitat/)
  - [Proglib - Big O нотация: что это такое и почему ее обязательно нужно знать каждому программисту](https://proglib.io/p/big-o-notaciya-chto-eto-takoe-i-pochemu-ee-obyazatelno-nuzhno-znat-kazhdomu-programmistu-2022-02-17)

<br></p>
</details>

[//]: # (Структуры данных todo: доработать)
<details><summary><b>Структуры данных*</b></summary><p>

- `Стек` (Stack)
  - стопка тарелок
  - Last In First Out (LIFO) — последним вошел, первым вышел.
  - Массив в JS имеет атрибуты стека (но они умеют больше)
- `Очередь` (Queue)
  - First In First Out (FIFO) — первым вошел, первым вышел.
- `Связный список` (Linked List)
  - цепочечная структура данных, где каждый узел состоит из двух частей: данных узла и указателя на следующий узел/
  - в узле 1 ссылка на узел 2, а в нём на узел 3 и далее. Чтобы попасть в узел 3 надо найти узле 1, из него узел2 и только потом узел 3
  - в списках долго искать нужное произвольное значение
  - зато в списках быстро можно добавить/удалить значение в середине
- `Коллекция` (Set)
  - в отличии от массивов коллекция не допускает включения повторяющихся элементов и не содержит индексов.
  - т.е. нет индексво и каждая сущность встречается только 1 раз
- `Хеш-таблица` (Hash Table)
  - строится по принципу ключ-значение.
  - имеет hash function, преобразующую ключи в список номеров, которые используются как имена (значения) ключей. 
  - Одинаковые ключи должны возвращать одинаковые значения — в этом суть функции хэширования.
  - Из-за высокой скорости поиска значений по ключам, она используется в таких структурах, как Map, Dictionary и Object.
- `Дерево` (Tree)
  - нелинейная структура, в отличие от массива, стека и очереди. 
  - очень эффективно в части добавления и поиска элементов.
- `Нагруженное (префиксное) дерево` (Trie, читается как «try»)
  - разновидность поискового дерева. 
  - Данные в нем сохраняются последовательно (шаг за шагом) — каждый узел дерева представляет собой один шаг. 
  - Используется в словарях, поскольку существенно ускоряет поиск. Каждый узел дерева — буква алфавита, следование по ветке приводит к формированию слова. Оно также содержит «булевый индикатор» для определения того, что текущий узел является последней буквой.
- `Граф` (Graph)
  - также известный как сеть (Network), 
  - коллекция связанных между собой узлов. 
  - Бывает два вида графов — ориентированный и неориентированный, в зависимости от того, имеют ли ссылки направление. 
  - Графы могут быть представлены в виде списка или матрицы.

- **Ссылки** 
  - [Habr - 8 распространенных структур данных на примере JavaScript](https://habr.com/ru/post/497476/)


<br></p>
</details>

[//]: # (Оптимизация алгоритмов todo: доработать)
<details><summary><b>Оптимизация алгоритмов*</b></summary><p>

  - Вообще не очень понятно о чём речь.
  - Вероятно — выбор оптимального алгоритма под заадчу? 
  - Ну, например есть такая статья: [techrocks.ru - Оптимизация программного кода](https://techrocks.ru/2019/01/25/code-optimization-tips/)

<br></p>
</details>

[//]: # (Ссылки)
<details><summary><b>Ссылки</b></summary><p>

- [Алгоритмическая сложность](https://tproger.ru/translations/algorithms-and-data-structures)
- [Сортировки. Пузырьковая сортировка/фильтрация](https://tproger.ru/translations/sorting-for-beginners)
- [Бинарное дерево](https://tproger.ru/translations/binary-search-tree-for-beginners)
- [Wikipedia - Дональд Кнут «Искусство программирования»](https://ru.wikipedia.org/wiki/%D0%98%D1%81%D0%BA%D1%83%D1%81%D1%81%D1%82%D0%B2%D0%BE_%D0%BF%D1%80%D0%BE%D0%B3%D1%80%D0%B0%D0%BC%D0%BC%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D1%8F)
- [Адам Леос — Разбираемся в алгоритмах и структурах данных. Доступно и понятно](https://techrocks.ru/2019/12/12/algorithms-and-data-structures-basics/)

<br></p>
</details>