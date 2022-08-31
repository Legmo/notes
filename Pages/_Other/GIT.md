<h1>GIT</h1>

[//]: # (Методологии работы с GIT &#40;workflow&#41;)
<details><summary><h3>Методологии работы с GIT (workflow)</h3></summary><p>

- [Кратко о git-flow](http://ruwhynot.com/2016/03/08/briefly-about-gitflow/)
- [В чём состоит отличие между различными workflow?](https://ru.stackoverflow.com/questions/676514/%D0%92-%D1%87%D1%91%D0%BC-%D1%81%D0%BE%D1%81%D1%82%D0%BE%D0%B8%D1%82-%D0%BE%D1%82%D0%BB%D0%B8%D1%87%D0%B8%D0%B5-%D0%BC%D0%B5%D0%B6%D0%B4%D1%83-%D1%80%D0%B0%D0%B7%D0%BB%D0%B8%D1%87%D0%BD%D1%8B%D0%BC%D0%B8-workflow)
- [Модели ветвления в Git: какую выбрать?](https://proglib.io/p/git-workflow)
- [Оригинальная статья Vincent Driessen с описанием модели GitFlow (перевод на русский)](https://habr.com/ru/post/106912/)

<br></p>
</details>

[//]: # (Rebase)
<details><summary><h3>Rebase</h3></summary><p>

Способ объединить изменения, сделанные в одной ветке, с другой веткой.<br>
Альтернатива `merge`.<br>

Последовательно берет все коммиты из выбранной ветки и заново применяет их к новой ветке.<br>
Результат:

- Переприменяя коммиты, Git создает новые коммиты. Даже если они содержат те же изменения, то рассматриваются Git как
  новые и независимые коммиты.
- Git rebase переприменяет коммиты и не удаляет старые. После выполнения rebase ваши старые коммиты продолжат храниться
  в .git.

**Отличие от merge**

- `rebase` - повторно применяет коммиты поверх другой базовой ветки. Перезаписывает историю
- `merge` - объединяет две или более историй разработки”. Сохраняет историю в первозданном виде

**Ссылки**

- [Git Rebase: руководство по использованию](https://habr.com/ru/post/161009/)
- [Git Rebase для начинающих](https://habr.com/ru/post/337302/)

<br></p>
</details>

[//]: # (Squash)
<details><summary><h3>Squash</h3></summary><p>

Берём серию коммитов и «уплотняем», сжимаем ее.<br>
Серию из N коммитов преобразуем в один коммит.

Применяется, чтобы превратить большое число малозначимых коммитов в небольшое число значимых. Так легче отслеживать
историю Git.

Также этот прием используется при объединении ветвей. Чаще всего вам будут советовать всегда сжимать коммиты и выполнять
перебазирование с родительской ветвью (например, master или develop). В таком случае история главной ветки будет
содержать только значимые коммиты, без ненужной детализации.

**Ссылки**

- [Как сжимать коммиты в Git с помощью git squash](https://medium.com/nuances-of-programming/%D0%BA%D0%B0%D0%BA-%D1%81%D0%B6%D0%B8%D0%BC%D0%B0%D1%82%D1%8C-%D0%BA%D0%BE%D0%BC%D0%BC%D0%B8%D1%82%D1%8B-%D0%B2-git-%D1%81-%D0%BF%D0%BE%D0%BC%D0%BE%D1%89%D1%8C%D1%8E-git-squash-8a84b9f62734)

<br></p>
</details>

[//]: # (Про текстовый редактор для коммитов)
<details><summary><h3>Про текстовый редактор для коммитов</h3></summary><p>

- Я использую nano

**Ссылки**

- [stackoverflow - Замена дефолтного редактора кода в git (ru)](https://ru.stackoverflow.com/questions/437331/%D0%97%D0%B0%D0%BC%D0%B5%D0%BD%D0%B0-%D0%B4%D0%B5%D1%84%D0%BE%D0%BB%D1%82%D0%BD%D0%BE%D0%B3%D0%BE-%D1%80%D0%B5%D0%B4%D0%B0%D0%BA%D1%82%D0%BE%D1%80%D0%B0-%D0%BA%D0%BE%D0%B4%D0%B0-%D0%B2-git)
- [Связывание текстового редактора с Git](https://ymatuhin.ru/tools/git-default-editor/)

<br></p>
</details>

**Ссылки**

- [Wikipedia - GIT](https://ru.wikipedia.org/wiki/Git)
- [GIT Book (ru)](https://git-scm.com/book/ru/v2)
- [Pro Git (ru)](http://www.linuxcookbook.ru/books/progit/index.html)
- [Хабр - Git. Коротко о главном](https://habr.com/ru/post/588801/)
- [Hexlet - Что такое Git и для чего он нужен](https://guides.hexlet.io/ru/git-guide/)
- [GIT за полчаса](https://proglib.io/p/git-for-half-an-hour)
- [Конспект по GIT](https://gist.github.com/vchernogorov/030144a7b0832c683adc3e0b502ad3e5)
- [GeekBrains - Git. Базовый курс (бесплатный)](https://gb.ru/courses/1117)
- [GeekBrains - Git. Базовый курс (бесплатный, YouTube)](https://www.youtube.com/playlist?list=PLmRNNqEA7JoM77hOJkPrLOfJQGizCLR3P)
- [Хабр - Поддержание аккуратной истории в Git с помощью интерактивного rebase](https://habr.com/ru/company/flant/blog/536698/)
- [Как сжимать коммиты в Git с помощью git squash](https://medium.com/nuances-of-programming/%D0%BA%D0%B0%D0%BA-%D1%81%D0%B6%D0%B8%D0%BC%D0%B0%D1%82%D1%8C-%D0%BA%D0%BE%D0%BC%D0%BC%D0%B8%D1%82%D1%8B-%D0%B2-git-%D1%81-%D0%BF%D0%BE%D0%BC%D0%BE%D1%89%D1%8C%D1%8E-git-squash-8a84b9f62734)
- [Habr - Git Wizardry (краткое введение в Git)](https://habr.com/ru/post/60347/?ysclid=l6y8sw0gaj91345487)
  <br>
  <br>

*[Legmo, 2019-2022](https://github.com/Legmo/notes/)*