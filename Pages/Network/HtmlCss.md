<h1>HTML и CSS</h1>

Ссылки на материалы для самоподготовки
<br>

[//]: # (HTML)
<details><summary><b>HTML</b></summary><p>

- [schoolsw3.com — HTML Самоучитель](https://www.schoolsw3.com/html/html_form_attributes.php)
- [html5book.ru — HTML и HTML5](https://html5book.ru/html-html5/)
- [Estelle Weyl, Rachel Andrew, Jhey Tompkins — Учим HTML5](https://hcdev-ru.pages.dev/learn/html5/)
- [itchief.ru — Подробное руководство по HTML и CSS](https://itchief.ru/html-and-css/)
- [MDN — Основы HTML](https://developer.mozilla.org/ru/docs/Learn/Getting_started_with_the_web/HTML_basics)
- [Дока — HTLM](https://doka.guide/html/)
- [html5css.ru — HTML с нуля. HTML учебник для начинающих и чайников](https://html5css.ru/html/default.php)
- [w3schools.com — HTML Tutorial (en)](https://www.w3schools.com/html/default.asp)
- [html5beginner — Уроки по HTML/CSS/JavaScript/PHP для начинающих (w3schools.com на русском)](https://html5beginner.github.io/)

<br></p>
</details>

[//]: # (CSS)
<details><summary><b>CSS</b></summary><p>

[//]: # (Общее)
- <details><summary><b>Общее</b></summary><p>

  - [hcdev-ru — Учим CSS3](https://hcdev-ru.pages.dev/learn/css3/)
  - [html5book.ru — CSS и CSS3](https://html5book.ru/css-css3/)
  - [MDN — Основы CSS](https://developer.mozilla.org/ru/docs/Learn/Getting_started_with_the_web/CSS_basics)
  - [itchief.ru — Подробное руководство по HTML и CSS](https://itchief.ru/html-and-css/)
  - [Дока — CSS](https://doka.guide/css/)
  - [MDN — Css селекторы ](https://developer.mozilla.org/ru/docs/Web/CSS/CSS_Selectors)
  - [w3schools.com — CSS Tutorial (en)](https://www.w3schools.com/css/default.asp)

  <br></p>
  </details>

[//]: # (Что нового?)
- <details><summary><b>Что нового?</b></summary><p>

  - Примеры «новых» возможностей на осень 2023:
    - Контейнерные запросы (`@container`, `container queries`)
      - стилизовать элементы в зависимости от размера их родительского контейнера.
    - Запросы стиля (`style queries`)
      - если у родителя есть аттрибут `style = "someStyle"`, примени такие-то правила
    - Псевдокласс `:has` 
      - стилизовать элементы с учетом наличия у них определенного потомка
    - Директива `@apply` 
      - переиспользовать набор стилей, определенных в классе. Примени к `.redButton` все стили от `.defaultElement`
    - Свойство `color-adjust` 
      - корректировать цвета элемента с учетом фонового цвета. Гарантирует четкое отображение текста поверх фоновой картикни или цвета
    - Микросинтаксис `:nth-of`
      - продвинутая вресия псевдокласса `:nth-child`
    - `Text-wrap: balance` 
      - сбалансированный перенос текста для заголовков
    - `Initial-letter` 
      - стилизация первой буквы текста (работает в свзяке с `:first-letter`)
    - Динамические единицы измерения области просмотра (`viewport`) 
      - учитывает например, автоматически скрываемые навигационные панели на мобильных.
      - `svh` и `svw` — наименьший активный размер области просмотра;
      - `lvh` и `lvw` — наибольший активный размер области просмотра;
      - `dvh` и `dvw` — динмамические. Автоматически получают новые значения при отображении/скрытии дополнительных браузерных панелей (поиск, панель управления...)
    - Цветовые пространства с широкой гаммой 
      - можно использовать новые цвета (sRGB, Display-p3, A98-RGB,, Rec202, ProPhoto). Раньше были только RGB, RGBa, HEX, HSL и HWB.
    - Функция `Color-mix()` 
      - получение цвета смешиванием значений двух исходных цветов. Напрмиер можно «высветлять» цвет не делая его прозрачным
    - Вложенность селекторов (`nesting`)
      - вкладывать селекторы друг в друга, как в SASS
    - Каскадные слои (`cascade layers`)
      - можно гибко управлять приоритетом стилей
    - Стили с ограниченной областью видимости (`scoped styles`)
      - создавать пространства имен CSS
    - Тригонометрические функции
    - Индивидуальные свойства трансформации
      - функции в правиле `transform` можно задавать по отдельности, не надо каждый раз повторять все (translateX, rotate, scale) 
    - HTML-аттрибут `Popover`
      - превращает лемент во сплывающее окно. Избалет от необходимости писать ему z-index, логику кнопки зактрытия и т.д. 
    - Позиционирование якоря (`anchor positioning`)
      - позицинирование всплывающих оконо относительно желемнта, над которым они появились
    - `Selectmenu`
      - различный фишки для создания удобных выпадающих меню
    - Дискретные свойства переходов
      - возможность анимирования дискретных свойств, таких как `z-index` и `display`.
    - Анимации, управляемые прокруткой (`scroll-driven animations`)
      - при скролле контейнерв вверх и вниз, анимация проигрывается вперед и назад (эффектом параллакса и т.д.)
    - Переходы отображения (`view transitions`)
      - модифицировать DOM за один шаг путем создания перехода между двумя состояниями

  - **Ссылки**
    - [Habr — Новинки CSS и UI: I/O 2023](https://habr.com/ru/articles/741914)
    - [Medium — Обзор функциональностей CSS, которые появились в 2022 году](https://medium.com/nuances-of-programming/%D0%BE%D0%B1%D0%B7%D0%BE%D1%80-%D1%84%D1%83%D0%BD%D0%BA%D1%86%D0%B8%D0%BE%D0%BD%D0%B0%D0%BB%D1%8C%D0%BD%D0%BE%D1%81%D1%82%D0%B5%D0%B9-css-%D0%BA%D0%BE%D1%82%D0%BE%D1%80%D1%8B%D0%B5-%D0%BF%D0%BE%D1%8F%D0%B2%D0%B8%D0%BB%D0%B8%D1%81%D1%8C-%D0%B2-2022-%D0%B3%D0%BE%D0%B4%D1%83-9b754380e700)

    <br></p>
    </details>

[//]: # (Grid)
- <details><summary><b>Grid</b></summary><p>

  - [Habr — Полное визуальное руководство/шпаргалка по CSS Grid](https://habr.com/ru/company/macloud/blog/564182/)
  - [Дока — Гайд по Grid](https://doka.guide/css/grid-guide/)
  - [hcdev-ru — Grid](https://hcdev-ru.pages.dev/learn/grid/)

  <br></p>
  </details>

[//]: # (Flexbox)
- <details><summary><b>Flexbox</b></summary><p>
  
  - [Habr — Полное руководство по Flexbox](https://habr.com/ru/articles/467049/)
  - [Дока — Гайд по Flexbox](https://doka.guide/css/flexbox-guide/?ysclid=lpqk079mmj22424324)
  - [hcdev-ru — Flexbox](https://hcdev-ru.pages.dev/learn/flex/)
  - [webref.ru — Визуальное руководство по свойствам flexbox](https://webref.ru/layout/visual-guide-flexbox/usage)
  - [webref.ru — Руководство по флексбоксам](https://webref.ru/layout/flexbox-tutorial)

  <br></p>
  </details>

[//]: # (Отдельные темы)
- <details><summary><b>Отдельные темы</b></summary><p>

  - [Дока — Контекст наложения](https://doka.guide/css/stacking-context/)
  - [Дока — Специфичность](https://doka.guide/css/specificity/)
  - [Дока — Принцип каскада](https://doka.guide/css/cascade/)
  - [Дока — Наследование](https://doka.guide/css/inheritance/)
  - [Дока — Блочная модель](https://doka.guide/css/box-model/)
  - [Дока — Единицы измерения](https://doka.guide/css/numeric-types)
  - [Дока — Вендорные префиксы](https://doka.guide/css/vendor-prefixes)
  - [Дока — Псевдоэлементы](https://doka.guide/css/pseudoelements)
  - [Дока — Псевдоклассы](https://doka.guide/css/pseudoclasses)
  - [Дока — Кастомные свойства](https://doka.guide/css/custom-properties/)
  - [Дока — Свойство inset](https://doka.guide/css/inset/)
  - [Дока — Свойство image-set()](https://doka.guide/css/image-set/)
  - [Дока — HTML-тэг `<picture>`](https://doka.guide/html/picture/)
  - [html5book.ru — CSS3-фильтры](https://html5book.ru/css3-filtry/)
  - [html5book.ru — Объединение и смешивание слоев](https://html5book.ru/obedinenie-i-smeshivanije-sloev/)
  - [Habr — Методы скрытия элементов веб-страниц (2020)](https://habr.com/ru/companies/ruvds/articles/485640/)
  - [shpargalkablog.ru — Перенос слов в CSS](http://shpargalkablog.ru/2013/02/word-wrap.html)
  - [Дока — Блок по центру экрана](https://doka.guide/recipes/center/?ysclid=lpqsutznis953455996)
  - [learn.javascript.ru — Центрирование горизонтальное и вертикальное](https://learn.javascript.ru/css-center)
  - **Поток и свойство «float»**
    - [Дока — Поток документа](https://doka.guide/html/flow)
    - [habr — Подробно о свойстве float](https://habr.com/ru/articles/142486/)
    - [Дока — Float](https://doka.guide/css/float)
    - [learn.javascript.ru — float](https://learn.javascript.ru/float)
    - [designformasters.info — CSS Float в теории и на практике (WebArchive)](https://web.archive.org/web/20101127115023/http://designformasters.info/posts/css-float-theory-and-practice/)
    - [css-tricks.ru — Всё о свойстве floats](http://www.css-tricks.ru/articles/Details/AllAboutFloats)
    - [css-tricks.com — All about floats](https://css-tricks.com/all-about-floats/)

  <br></p>
  </details>

<br></p>
</details>

[//]: # (Анимация CSS/JS)
<details><summary><b>Анимация CSS/JS</b></summary><p>

- CSS-анимация
  - [webref.ru — CSS-анимация для начинающих](https://webref.ru/layout/cssanimation101)
  - [Дока — CSS-анимация](https://doka.guide/css/animation/)
  - [hcdev.ru— CSS-анимация](https://hcdev.ru/learn/css3/animations/)
- JS-анимация
  - [learn.javascript.ru — JavaScript-анимации](https://learn.javascript.ru/js-animation)
  - [Skillbox — Как создать анимацию в JavaScript за 30 минут](https://skillbox.ru/media/code/kak_sozdat_animatsiyu_v_javascript_za_30_minut/?ysclid=lpqkb0tgtt164953922)
  - [codelab.pro — Подробное руководство про анимацию в JavaScript](https://codelab.pro/podrobnoe-rukovodstvo-pro-animacziyu-v-javascript/?ysclid=lpqkb2t378674522801)
  - 
  - [MDN — Canvas API](https://developer.mozilla.org/ru/docs/Web/API/Canvas_API)
  - [metanit.com — Canvas API](https://metanit.com/web/javascript/21.1.php)
  - [metanit.com — Введение в WebGL](https://metanit.com/web/webgl/1.1.php)
  - [webformyself.com — Использование GSAP 3 для веб-анимации](https://webformyself.com/ispolzovanie-gsap-3-dlya-veb-animacii)
  - [threejs.org — Three JS. Официальная документация](https://threejs.org/manual/#ru/fundamentals)

<br></p>
</details>

[//]: # (CSS-фрэймворки)
<details><summary><b>CSS-фрэймворки</b></summary><p>

- [v2.tailwindcss.ru — Документация по Tailwind CSS](https://v2.tailwindcss.ru/docs/installation/)
- [bootstrap5.ru — Документация по Bootstrap](https://bootstrap5.ru/docs/getting-started/introduction)
- 
<br></p>
</details>

[//]: # (UiKit's)
<details><summary><b>UiKit's</b></summary><p>

- [MaterialUI — англйиская документация (оф.)](https://mui.com/)
- [MaterialUI — русская документация (неоф.)](https://mui-ru.artyom.me/material-ui/getting-started/overview/)
- [Ant Design — англйиская документация (оф.)](https://ant.design/)

<br></p>
</details>


[//]: # (Прочее)
<details><summary><b>Прочее</b></summary><p>

- [Legmo — Некоторые вопросы по вёрстке для собеседования frontend](https://github.com/Legmo/notes/blob/master/Pages/JobSearch/HtmlCssQuestions.md)
- [BEM — официальная документация](https://ru.bem.info/methodology/quick-start/)
- [MDN — CSS-переменные](https://developer.mozilla.org/ru/docs/Web/CSS/Using_CSS_custom_properties)
- [SASS — Документация на русском](https://sass-scss.ru/?ysclid=lpqm4hl0m7451762557)
- [LESS — Введение в LESS](https://tokmakov.msk.ru/articles/item/5)
- [Habr — Краткий обзор отличий LESS от SASS (2011)](https://habr.com/ru/articles/130886/)
- [html5book.ru — Веб-типографика](https://html5book.ru/web-topography/)

<br></p>
</details>


<br>
<br>

*[Legmo, 2019-2023](https://github.com/Legmo/notes/)*
