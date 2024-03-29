<h1>Заметки - как проводить собеседования?</h1>

[//]: # (Общие идеи)
<details><summary><b>Общие идеи</b></summary><p>

- Использую профессиональную лексику
  - «Реализовать» / «предложить реализацию» вместо «написать»
  - и т.д. (составить словарик?)
- Тестовое задание давать до собеседования 
  - На собеседование обсуждаем - почему сделал так, зачем это и т.д.
- Тестовое задание должно быть ограничено по времени (разумные рамки)
  - Влад Головач: никогда не стоит задача «сделать лучший дизайн». Стоит задача «сделать лучший дизайн за определенное время при определенном бюджете». Это разные вещи.
- При подготовке вопросов не используй русские статьи
  - Соискатель использует их же для подготовки. 
  - Если используешь статьи - бери англоязычные, и только за последние пару лет.
- Если спрашиваешь теоретические вопросы - спрашивай фундаментальные вещи
    - Как работает движок JS?
    - Как браузер отрисовывает страницу (Parsing, layout, paintnig...)
- Задавай общие вопросы на глубокое понимание 
  - Как вы понимаете — что значит «архитектура фронтенда»?
  - Что вы вкладываете в понятие «дизайн языка»?
  - Зачем в REST (и HTTP) вообще ввели разные методы? Почему не передавать всё одним-двумя методами, ну например GET и POST?
  - Зачем нам так много разных html-тэгов?
  - Какие есть проблемы у Redux?
  - Какие есть альтернативы у Virtual DOM? Что использовалось до его появления? (`dirty checking`...)
  - Что такое «семантическая» вёрстка?
  - Давайте напишем один и тот же очень простой код в разных парадигмах/стилях — императивном, ООП, функциональном 
  - У паттернов «модуль» и «класс» много общего в плане назначения. Что бы вы отметили в первую очередь? (Оба предназначены для организации кода — группировки данных и поведения в логических единицах. Оба появились в 2015 году в ES6 :))) “
  - Представим что я человек с почти «нулевым» уровнем знаний. Объясните мне что такое замыкания. Идея в том, чтоб объяснить очень просто — будет видно насколько глубоко человек сам понимает тему (область видимости, передача функций как значений, вызов функций в других контекстах выполнения и т.д.) 
- Полезно спрашивать "Что нового/полезного появилось в технологии Х за этот и прошлый год"?
  - показывает насколько человек сейчас погружен в тему, есть ли энтузиазм и т.д.
- Ещё примеры вопросов на вовлеченность в современные проблемы IT
  - какие современные альтернативы у формата JSON (Message Pack)
  - какие современные альтернативы у формата JPEG (WebP, AVIF)
  - какие новые подходы к архитектуре фронтенда появились за последние несколько лет? (на 2022 это, например, Feature Driven Architecture (FDA, 2018) и Feature Sliced Design (FSD, 2018))
- Теоретическое знание "Что такое замыкание" вообще не гарантирует что человек сможет применить его на практике и узнает
  когда с ним столкнётся. 
    - дать пример кода и спросить — что тут происходит? Почему? Что случится если изменить так? Как изменить чтоб работало эдак?
    - три основных уровня:
      - знаю теоретически
      - могу узнать в коде, если встречу
      - пойму что этот приём надо использовать при решении реальной задачи
- Если даешь `live coding` — давай реальные задачки.
  - Ищешь React-разработчика — дай задачку на доработку React-компонента, а не на алгоритм поиска чисел Фибоначчи.
  - Если так сильно хочешь проверить замыкания и т.д. — интегрируй их в задачу связанную с React.
- Описывай ситуации и проверяй как человек думает
  - надо сделать то-то. Как вы это сделаете?
  - есть работающая программа, поменяем в ней вот это - что произойдёт? 
  - например: что будет если в этом методе жизненного цикла поменять то-то
- Проверяй как человек называет переменные.
- Проверяй как человек ищет ошибки и отлаживает/дебажит
  - даёшь кусок когда. Этот код делал то-то, в нём есть ошибки, найдите их
- Если человек ответил неверно — он сбивается. Даже если вина не его (например вопрос был сформирован некорректно). Несколько неверных ответов - совсем зависнет. После нескольких ошибок лучше давать вопросы попроще, чтоб он собеседуемый немного выдохнул и почувствовал себя увереннее.
- 
- Хорошо бы до собеседования определиться со списком требований, на которые будешь обращать внимание 
  - теоретические знания (в каких сферах?)
  - навыки кодирования (что оцениваем - скорость, изящество решений, понятность кода...)
  - навыки общения (что надо - умение сгладить конфликт; критиковать не обижая; пробивная сила; умение понять проблему собеседника..)
  - ...
- Вычленить самые частые косяки junior-программистов в твоей команде, и задавать задачки/вопросы на эти темы 
- В процессе собеседования — отмечай результаты кандидата в табличке. Плюс, дописывай свои заметки впечатления сразу после собеседования. Можно будет объективно сравнить данные разных кандидатов.
- Хороший тон — дать обратную связь по результатам собеседования. 
  - «Спасибо, вы крутой и очень нам понравились. Мы пока не готовы сделать вам предложение. Вот ваши результаты...» 
    - были такие-то теоретические вопросы, по ним такие-то баллы; 
    - вот наши заметки по вашему коду (это решил, тут пропустил, тут неочевидные названия переменных...) 
    - вот наша субъективная оценка по soft-skills, вот более конкретные нюансы - что понравилось/смутило).

<br></p>
</details>

[//]: # (Чего мы хотим и что реально проверяем?)
<details><summary><b>Чего мы хотим и что реально проверяем?</b></summary><p>

Думаю, основная проблема с современным подходом к найму программистов (интервью и т.д.) лежит в сфере методологии.<br>
Чтобы получить необходимый результат — надо его чётко сформулировать.<br>
Каких специалистов мы ищем? Почему нужны именно эти качества? Как их проверить?
<br>
<br>

**Тезис**

Все проводят интервью и задают одни и те же вопросы/задачки потому что «так принято».<br>
По факту это далеко не самый эффективный способ отбора/поиска кандидатов.<br> 
Просто к нем привыкли, всем лень анализировать ситуацию и подбирать подход для решения своих конкретных задач.<br>
Пример альтернативного подхода — [учебная программа](https://vc.ru/hr/304764-kak-my-sdelali-besplatnuyu-programmu-obucheniya-veb-razrabotke-i-trudoustroili-60-vypusknikov) компании «MetaLamp»
<br>
<br>

**Как работает сейчас**

На интервью мы отбираем людей которые:
- хорошо проходят интервью — имеют опыт собеседований, не волнуются, умеют говорить...
- могут повторить куски теории из учебника — понимание проверяется редко, обычно достаточно «заучивания»
- могут быстро «щёлкать» традиционные задачки с LeetCode
- хотят устроиться на эту должность (основная причина, почему метод интервью работает — случайно могут попасться адекватные специалисты, которые смогли пройти интервью)
  <br>
  <br>

**Про эффективность интервью как метода подбора персонала**

Сейчас эффективность отбора кандидатов на интервью на 90% зависит от собеседующего. Если он крут и «чувствует» что человек подходит — то есть шанс что он наймёт подходящего специалиста.<br>
Т.е. сейчас это не про «эффективность системы отбора», а про «навык распознавания» подходящих людей в процессе общения.

Чем-то похоже на историю с эффективными методами психотерапии. <br>
В паре слов: методов психотерапии очень много, и некоторые исходят из диаметрально противоположных концепций относительно структуры человеческой психики.

Провели масштабное научное исследование — международная организации более 10 лет анализировала эффективность работы сотен психотерапевтов по всему миру. Хотели выяснить, какой метод психотерапии даёт больший процент излечений. Выяснилось что все методы дают примерно одинаковые результаты (в рамках статистической погрешности).

Но есть один фактор, который очень чётко коррелирует с эффективностью лечения. Чем больше часов практики у психотерапевта, тем эффективнее он помогает людям. Неважно каким методом.

Кажется, с интервью та же история — если для подбора персонала мы используем интервью, то важна не его структура, не вопросы, и т.д. Важен человек, который проводит интервью — сможет ли он «почувствовать» нужного кандидата, или нет.
<br>
<br>

**Варианты решения**

Перед поиском-отбором кандидатов надо понять:
- Какие качества нам нужны?
    - например «ответственность»
- В чём будет проявляться это качество?
    - как проявляется ответственность в ситуации Х (с нашей точки зрения)?
    - человек срочно бежит к начальству и сообщает о проблеме?
    - человек начинает решать проблему сам, не дергая начальство?
    - человек не отвлекается от своей работы, потому что эту проблему должны решать другие специалисты и «им виднее»?
    - При определенных условиях каждое из этих решений может быть правильным. Надо разобраться, чего хотим мы — и под эти требования искать человека.
- Как проверить это качество у кандидата?
    - каким образом проверить ответственность?
    - описать ситуацию на словах и проверить что человек сделает?
    - реально поставить в сложную ситуацию и посмотреть на реакцию?
    - показать как кто-то ведёт себя в этой ситуации (например фрагмент из фильма) и пропросить прокомментировать, что соискатель думает об увиденном?
    - ...

Надо понять чего и зачем мы хотим, каких людей ищем.
- Нужен крутой опытный программист? 
  - Ты не проверишь это на интервью. 
  - Надо смотреть код человека, зная какая задача ему ставилась, сколько времени и ресурсов было потрачено. 
  - Причём это должен быть большой код, не пара функций.
- Нужен толковый джун, который обладает минимальной базой и быстро учится?
  - Проведи серию бесплатных он-лайн уроков, в конце дай практическое задание на пройденный материал (ограниченное по времени). 
  - Те кто хорошо усвоили новое и успешно решили задание — отличные кандидаты.
- Нужен человек который будет учить других? С навыками преподавания и глубокими теоретическими знаниями?
  - За полчаса до интервью дай ему какую-то фундаментальную тему (например «Архитектура фронтенда») и попроси подготовить лекцию на 20 минут.
    - Послушай как он объясняет, насколько глубокое и ясное понимание у него самого. Задай «дурацких» вопросов, наводящих на серьёзные проблемы
- Нужен человек который хорошо проводит code-review и умеет выстраивать коммуникации в команде?
  - дай ему на ревью кусок кода с ошибками
  - устрой стресс-интервью со сложным клиентом

<br></p>
</details>

[//]: # (Про знание и заучивание. Фейнман)
<details><summary><b>Про знание и заучивание (Фейнман)</b></summary><p>

**Фейнман про физику в Бразилии.(«Вы наверное шутите мистер Фейман?»)**

Я обнаружил кое-что еще, - продолжал я. - Hаугад листая страницы и останавливаясь в любом произвольно выбранном месте, я могу показать вам, почему это не наука, а заучивание во всех случаях, без исключения. Я рискну прямо сейчас, в этой аудитории перелистать страницы, остановиться в произвольном месте, прочитать и показать вам.

Так я и сделал. Тррррр-ап - мой палец остановился на какой-то странице, и я начал читать: "Триболюминесценция. Триболюминесценция - это излучение света раздробленными кристаллами...".

Я сказал: "Вот, пожалуйста. Есть здесь наука? Hет! Здесь есть только толкование одного слова при помощи других слов. Здесь ни слова не сказано о природе: какие кристаллы испускают свет, если их раздробить? Почему они испускают свет? Вы можете представить, чтобы хоть один студент пошел домой и попробовал это проверить? Они не могут. Hо если бы вместо этого вы написали: "Если взять кусок сахара и в темноте расколоть его щипцами, вы увидите голубоватую вспышку. То же самое происходит и с некоторыми другими кристаллами. Hикто не знает, почему. Это явление называется триболюминесценцией. Тогда кто-нибудь проделал бы это дома, и это было бы изучением природы". Я использовал для доказательства этот пример, но мог взять и любой другой, - вся книга была такая.

- [Остальное здесь](https://andrew-vasilkov.livejournal.com/69467.html)

<br></p>

</details>

[//]: # (Про две системы мышления. Канеман)
<details><summary><b>Про две системы мышления (Канеман)</b></summary><p>

Дорофеев М «Джедайские техники. Как воспитать свою обезьяну, опустошить инбокс и сберечь мыслетопливо»

Согласно модели Канемана, наше сознание – это две системы, в его книге они так и называются: Система 1 и Система 2. Информация, поступающая в наш мозг от органов чувств, попадает в Систему 1, которая работает автоматически и почти «бесплатно» с точки зрения энергетических затрат. Система 1 вырабатывает определенное решение и передает это
       решение Системе 2. Система 2 – это наше медленное, но умное мышление. В отличие от Системы 1, она способна решать
       сложные задачи, но на этом ее преимущества заканчиваются. Система 2 – тяжелый, ленивый и неповоротливый
       инструмент. Получив от Системы 1 вариант решения, Система 2 может вмешаться, заменив его на другое, а может и
       оставить это решение в первоначальном виде и выдать его в качестве окончательного в виде нервных импульсов,
       которые уже заставят наше тело шевелиться, а сознание – думать «в определенную сторону».

Для иллюстрации подобной архитектуры мышления Канеман использовал простые задачки (многие из них вы могли
  встречать на собеседованиях). Попробуйте проследить за тем, как рождается в вашей голове решение такой задачи:
  - Бейсбольная бита и мяч вместе стоят 1 доллар 10 центов.
  - Бейсбольная бита дороже мяча на 1 доллар.
  - Сколько стоит мяч?

Правда же, первой вашей мыслью было: «10 центов», а потом уже в голову пришел правильный ответ? Если вы и сейчас
  считаете, что мяч стоит 10 центов, рекомендую отложить книгу, взять лист бумаги, ручку и попробовать честно решить
  эту задачу.

«10 центов» – ответ, который дает быстрое мышление. Получив его, вы, скорее всего, осознали, что ответ неверен и
  нужно честно и аккуратно вычислить правильный. Также наверняка вы ощутили, что начинать вычисления не очень-то
  хочется. Это не потому, что вы постарели и поглупели. Несмотря на то что Система 2 – самая мудрая наша часть,
  лишний раз она включаться не захочет. Нужен веский повод для того, чтобы она начала работать, например
  собеседование. Мало того, само по себе начало медленного мышления – момент не очень приятный, а потому мы
  подсознательно стараемся делать это как можно реже. Да-да, если говорить совсем простым языком, думать – больно
  или как минимум не очень приятно. Именно поэтому мы стараемся не делать этого слишком часто...

**Такое ощущение, что на собеседованиях мы исследуем у кандидата свойства Системы 2 (медленного мышления) в то
  время как после выхода на работу, адаптировавшись, человек начинает работать преимущественно Системой 1 (быстрым
  мышлением). Знакомо ощущение, будто вы собеседовали другого человека?**

<br></p>
</details>

<br> 
<br> 

*[Legmo, 2019-2023](https://github.com/Legmo/notes/)*