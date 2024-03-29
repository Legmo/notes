# Список frontend/full-stack компетенций Drupal 7-8 (старый) #

## Работа с командной строкой Windows/Unix ##
  - перемещение по каталогам
  - скопировать тест из строки
  - вставить тест в строку
  - вызов help
  - запуск команды с ключом
  - работа с логом

## База данных ##
  - общее понимание о базах, таблицах, SQL - что это, зачем и как работает
  - использование PHPMyAdmin
  - использование MySQL Workbench
  - создание базы
  - создание пользователя
  - установка прав
  - удаление (drop) базы/пользователя
  - импорт базы
  - экспорт базы
  - правка конкретного значения в конкретной таблице (например пароля админа)

## Установка Drupal (7 и 8) ##
  - через веб-интерфейс / drush
  - установка из готовой сборки
  - на удалённый сервер 
  - на локальны сервер
  - настройка settings.php
  - настройка robots.txt, закрытие сайта от индексации 
  
## Работа с Drush ##
  - что это и зачем
  - где найти документацию (описание основных команд)
  - установка drush на локальной машине
  - установка и включение модулей + зависимых модулей
  - удаление модуля
  - сброс кэша
  - обновление ядра Drupal через drush
  - генерация одноразового пароля
  - смена пароля у пользователя
  - работа с базой данных
  - работа с базовой сборкой: создаём копию сайт + дамп базы и разворачиваем новый сайт
  - проверка безопасности сайта (установка и ипользование drush asec)

## Общая структура папок Drupal 7/8 ##

## Создание темы Drupal 7/8 ##
  - стандартные темы Drupal
  - подключение и настройка сторонних тем
  - создание темы (файл инфо и т.д.)
  - создание суб-тем

## Работа с шаблонами Drupal 7/8 ##
  - шаблонизаторы (phpTemplate, Twig)
  - синтаксис php/twig, сокращённый синтаксис php
  - переменные
  - условия
  - arg
  - создание шаблонов для типов нод
  - вывод пути к теме через php
  - вывод картинок через php (как <img> и как style="background:..."), обработанных модулем image style и оригинальных
  
## Препроцессинг ##
  - что это и зачем
  - хуки
  - template.php
  - как работать с документацией
  
## Регионы ##
  - что это и зачем
  - создание и настройка
  - объявление в файле темы
  - использование в админке
  - использование в шаблонах
  
## Типы материалов, ноды ##
  - что это и зачем
  - создание и настройка
  - вывод информации (блока, текста картинкии...) только в нодах опр. типа. Условие в page.tpl
  - вывод ноды в colorbox
  
## Поля ##
  - что это и зачем
  - создание и настройка
  - стандартные поля Drupal (из коробки) + дополнительные поля (результат работы модулей)
  - отображение полей в ноде
  - отображение полей в админке
  - группировка полей
  - программный вывод отдельных полей ноды: в другом месте самой ноды, в блоке, в page...
  - вывод поля ноды в виде блока
  
## Блоки ##
  - что это и зачем
  - создание и настройка
  - вывод блоков с помощью кода
  - вывод нескольких блоков на странице
  - программный вывод блоков
  - вывод информации внутри блока в зависимости от значений полей в ноде. Если в настройке ноды какое-то поле стоит в режиме «true» - на транице этой ноды блок выводится так-то. Если стоит «false» — блок выводится иначе 

## Вьюсы (представления) ##
  - что это и зачем
  - создание и настройка
  - импорт/экспорт
  - вьюс в виде страницы и в виде блока
  - фильтры
  - модуль Exposed filters
  - контекстные фильтры
  - связи
  - поле «Глобальный: Пользовательский текст» + альтернативыне решения
  - ручная сорттировка вььюсов + Draggable Views
  
## Модули ##
  - что это и зачем
  - как работает модуль и как создать свой модуль (общее понимание)
  - поиск и подбор модулей на Drupal.org
  - установка через админку, через drush, через FTP
  - обновление и откат (downgrade)
  - модуль backup & migrate
  - модуль admin-menu
  - модуль image style
  - модули для crop'а картинок
  - модуль colorbox
  - модуль features
  - модуль pargraph
  - модуль panels
  - модуль rules
  - модули сontext и Сontext entity field
  - модуль тaxonomy CSV import-export (импорт каталога в словарь таксономии)
  - модули для создания аккордеонов, в т.ч. во вьюсе
  - модули для создания табов, в т.ч. во вьюсе
  
## Модуль Webform ##
  - что это и зачем
  - создание и настройка форм
  - вывод формы в блоке
  - страница подтверждения - отдельной страницей и в colorbox
  - статистика работы формы
  - формы в несколько шагов
  - AJAX
  - Webform + Colorbox
  - honeyPot и другие методы защиты от спама
  - капча

## Работа с меню ##
  - выпадающие меню
  - активный пункт меню
  - вложенные меню
  - меню с привязкой к таксономии
  
## Поиск ##
  - стандартные средства поиска Drupal
  - индексация
  - cron
  - шаблоны и темизация форм и результатов поиска
  - поиск от Яндекса и Гугла
  - поиск с морфологией (общее понимание)
  - фасетный поиск (общее понимание)
  - Search API (общее понимание)
  - Apache Solr (общее понимание)
  - Sphinx (общее понимание)
  
## JS и jQuery для Drupal ##
  - понимать специфику использования jQuery в ядре Drupal
  - использование jQuery из ядра для простых операций на странице (аккордеон программынми средствами и т.д.)
  - объявление jQuery в скриптах для Drupal
  - модуль jQuery update
  - behavior & once
  - подключение скрипта для всего сайта
  - подключение скрипта для отдельной страницы/типа материала
 
## Слайдеры ##
  - модули и их связки для создания разных слайдеров - слайдер картинок, слайдер нод, слайдер типов материалов. 
  - по одному элементу и по несколько в слайде. 
  - слайдеры с ссылкой на ноду, форму или colorbox. 
  - изменение настроек слайдера при изменении размера экрана (адаптивность)
  
## Общие вопросы ## 
  - мультисайтинг
  - мультиязычность, методы реализации
  - таксономия, создание каталога
  - настройка адресов/путей страниц
  - настройка прав (для редактора, для пользователей и т.д.)
  - включение/отключение кэширования css/js
  - работа с логами Drupal
  - хлебные крошки
  - дата, шаблон даты
  - вывод информации только на главной странице сайта (is_front)
  - убираем стандартный контент с Главной
  - импорт/экспорт содержимого нод и сайта вообще
  - отключение регистрации новых пользователей в Drupal 7
  - подключение css для отдельной страницы/типа материала

<br> 
<br> 

*[Legmo, 2019-2023](https://github.com/Legmo/notes/)*
