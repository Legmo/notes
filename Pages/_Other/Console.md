# Про консоли, терминалы и оболочки #
 
<details><summary><b>Термины «Консоль», «Терминал», «Эмулятор терминала» и «Оболочка»</b></summary><p>

<b>Консоль</b>
- Командный интерпретатор, интерпретатор командной строки
- Программа, часть операционной системы. Обеспечивает базовые возможности управления компьютером посредством интерактивного ввода команд через интерфейс командной строки или последовательного исполнения пакетных командных файлов.
- Как правило, его функции сводятся к
  - возможности запускать другие программы
  - может содержать базовые команды ввода-вывода
  - может содержать свой простой скриптовый язык программирования.
- значение слова - доска с кнопками, пульт управления (“organ console”, то есть “пульт органа”, на ЭВМ - operator’s console)
- совокупность устройств, которые позволяет вам взаимодействовать с устройством.
- исторически: терминал, который подключен напрямую к компьютеру. Большинство терминалов были соединены неявно, но хотя бы один был подключен напрямую к компьютеру. Консоль было разрешено использовать строго определенному кругу лиц, так как она позволяла настраивать компьютер.
- консоль, это работа непосредственно с самим устройство, терминал - некая удаленная работа.
- В компьютере клавиатура и монитор, подключенные непосредственно к компьютеру, называются Консоль. Терминал подключен через последовательный пор (это не часть самого компьютера), а консоль - это устройство, которое есть у самого компьютера, его часть. У компьютера есть только одна консоль. Когда компьютер запускается, вся информация будет отображаться на консоли, но не на терминале. Другими словами, консоль является базовым устройством компьютера, а терминал - дополнительным устройством.
- В операционной системе компьютера информация, не связанная с терминалом, такая как сообщения ядра и сообщения фоновой службы, может отображаться на консоли, но не на терминале. Терминал, который может напрямую отображать системные сообщения, называется консолью, а остальные называются терминалами. В системе Linux эта концепция была размыта.Но в других UNIX-подобных системах существует четкая разница между виртуальным терминалом и консолью. Например, система freeBSD. В freebsd только первый «терминал» является настоящей консолью. (То есть виртуальный терминал получается нажатием alt + f1), независимо от того, на каком виртуальном терминале вы выполняете вышеуказанную команду (даже если она выполняется на псевдотерминале, подключенном через сеть). Внутренняя информация о системе, например, какой пользователь вошел в систему на каком терминале, система имеет любое серьезное предупреждение об ошибке и другую информацию, отображается на этой реальной консоли. Здесь концепция терминала и консоли четко различается.

<b>Терминал</b> 
  - сейчас: графическое окно (обычно) для запуска реальной оболочки (shell). Инструмент для просмотра оболочки, как разные браузеры (Firefox, Chrome) = инструменты для просмотра Internet. Надстройка над консолью
  - исторически: комбинация дисплея и клавиатуры, то есть физическое устройство. Раньше это была комбинация принтера и клавиатуры. Обычно несколько терминалов подключались к одному и тому же компьютеру. Таким образом возможно было работать нескольким пользователям за одним и тем же компьютером, причем каждому выделялась своя сессия, независимая от других. Терминал был назван так потому, что он находился на конце терминального кабеля (terminal end).

<b>Эмулятор</b>
  - gnome-terminal, xterm, etc... 
  - программа, предоставляющая функционал терминала.

<b>Оболочка (Shell)</b> 
  - это программа, которую вы используете для взаимодействия с компьютером. Интерпретатор командной строки.  Главное предназначение — запускать другие программы. Это может быть интерфейс командной строки или графический интерфейс. Bash - это оболочка. 
  - это программа, которая принимает ваши команды (ls , cd и т.д.) И обрабатывает их, выполняя встроенные функции (например, cd) или вызывая внешние программы (например, ls или gcc).
  - Terminal Emulator — GUI приложение, то есть окно в X Window System. Shell — это command line interpreter, то есть просто исполнитель команд, он не имеет графической оболочки. Если говорить совсем правильно, вы не запускаете Bash, вы запускаете Terminal Emulator, который запускает внутри себя Bash. Terminal Emulator и Bash — абсолютно 2 различные программы. Первая отвечает исключительно за ввод/вывод, вторая — за обработку команд.

<b>Про Linux</b>
  - в Linux сложилось так, что текстовой консолью (просто консолью) называют вот те 6 (обычно, но может быть до 63-х) текстовые сессии (экраны), которые вы можете переключать Ctrl+Alt+F2, Ctrl+Alt+F3 и т.д.
  - в одной (но может быть и несколько) из таких консолей (обычно Ctrl+Alt+F1 или Ctrl+Alt+F7) запущена сессия графического сервера X Window ... то что вы видите как GUI...
  - а в этой графической сессии, среди других GUI программ может быть запущены разные программы эмулятров терминала (gnome-terminal и мн. др.)
  - вот эти окна или вкладки эмулятров терминала можете называть терминал ... если не блюсти в тщательности терминологическую девственность ;-) ... потому что нет других терминалов в современном Linux
  - наконец, в серверном Linux может вообще не быть графики (X Window), а значит и терминалов, но там всегда и обязательно может быть до 63 текстовых консолей...

<b>Как связаны</b>
  - Консоль = программа, часть ОС. Интерпретирует введенные команды и выдает результат.
  - К консоли может быть подключен терминал (или эмулятор терминала).
  - В окне консоли или терминала запускается программа-оболочка. Эта программа принимает мои команды и выводит некий результат. 
  - 
    <br></p></details>
<br>
<br>

<details><summary><b>Оболочка Cmd.exe</b></summary><p>

  - интерпретатор командной строки Windows
  - поставляется в комплекте с Windows
  - аналог COMMAND.COM, который используется в семействах MS-DOS и Windows 9x.
  - как запустить 
    - вызвать окно Run и набрать команду cmd. 
    - в меню Start кликнуть пиктограмму "Командная строка"
    - найти и запустить файл cmd в папке Windows/System32 

**Ссылки**
  - [Wikipedia - Cmd.exe](https://ru.wikipedia.org/wiki/Cmd.exe)
  - [zametkinapolyah.ru - CMD.exe. Как пользоваться интерпретатором командной строки Windows.](https://zametkinapolyah.ru/zametki-o-poleznyx-programmax/cmd-exe-komandnaya-stroka-windows.html)

<br></p></details>

<details><summary><b>Консоль IDE PhpStorm</b></summary><p>

  - Плагин в IDE PhpStorm. Позволяет прямо в IDE запускать команды для терминала
  - По-умолчанию терминалом для PhpStorm является стандартный терминал windows cmd.exe.
  - Можно изменить настройки на использование другого терминала File/Settings/Tools/Terminal
  - У меня стоит настройка "C:\Program Files\Git\bin\sh.exe" --login -i" + какая папка открывается при запуске (D:\Work\_Localsites\legmo_notes)

  **Ссылки**
  - [Git bash в PhpStorm для Windows](https://isaevdimka.ru/paper/all/git-bash-phpstorm-for-the-windows/)
  - [ru.stackoverflow.com - Настроить консоль phpStorm, чтобы были доступны unix-команды (как в Git bash)](https://ru.stackoverflow.com/questions/432445/%D0%9D%D0%B0%D1%81%D1%82%D1%80%D0%BE%D0%B8%D1%82%D1%8C-%D0%BA%D0%BE%D0%BD%D1%81%D0%BE%D0%BB%D1%8C-phpstorm-%D1%87%D1%82%D0%BE%D0%B1%D1%8B-%D0%B1%D1%8B%D0%BB%D0%B8-%D0%B4%D0%BE%D1%81%D1%82%D1%83%D0%BF%D0%BD%D1%8B-unix-%D0%BA%D0%BE%D0%BC%D0%B0%D0%BD%D0%B4%D1%8B-%D0%BA%D0%B0%D0%BA-%D0%B2-git-bash)
  - [JetBarins - Terminal PhpStorm](https://www.jetbrains.com/help/phpstorm/terminal-emulator.html)

<br></p></details>

<details><summary><b>Консоль FAR manager</b></summary><p>

  - FAR = консольный файловый менеджер для Windows
  - в качестве консоли использует `cmd` Windows. Также, сюда вписываются консольные команды при подключении к серверам по SSH (SFTP), FTP, WebDav
  - Есть много плагинов и всяких настроек.

<br></p></details>

<details><summary><b>Оболочка Git Bash</b></summary><p>

  - Оболочка `bash` (Bourne-Again Shell) - это улучшенная реализация оболочки sh, т.е. все, что вы можете делать в sh, также можно сделать в bash. Bash имеет дополнительные функции, упрощающие написание скриптов.
  - Оболочка `Git bash` - это оболочка `msys`, включенная в Git for Windows, поскольку Windows изначально не поддерживает функции `bash` (если вы не добавите Подсистема Windows для Linux).
  - Оболочка `Git bash` - приложение для сред Microsoft Windows, эмулирующее работу командной строки Git
  - Пакет, который устанавливает в Windows оболочку `Bash` (используется в Linux), некоторые распространенные утилиты `Bash` и систему `Git`.
  - Обычно ставится автоматически вместе с установкой Git для Windows

  
  **Ссылки**
  - [Bitbucket - Git Bash](https://www.atlassian.com/ru/git/tutorials/git-bash)
  - [Git. Краткое руководство по терминалу](https://github.com/netology-code/guides/blob/master/git-terminal/git-terminal.md)
  - [Stackoverflow - In the install path of Git for Windows, what's the difference between ./git-bash.exe and bin/bash.exe and bin/sh.exe?](https://stackoverflow.com/questions/53980686/in-the-install-path-of-git-for-windows-whats-the-difference-between-git-bash)

<br></p></details>

<details><summary><b>Различия Git Bash и Git CMD в Windows</b></summary><p>

- Не бывает `git cmd` или `git bash`. Есть одна сервисная утилита с разными именами: `git-cmd.exe` и `git-bash.exe`.
- Оба эти exe-файла делают следующее:
  1. Инициализация переменных окружения (PATH, и пр.)
  2. Запуск терминала.
- Разница между ними: 
   - `git-bash.exe` запускает терминал `mintty` с `bash` внутри. 
   - `git-cmd.exe` запускает стандартный терминал Windows с `cmd.exe`. Имеет ключик `--command=...` с помощью которого можно запустить в нём `bash` вместо `cmd` при желании.
- Реальные различия:
    1. Из командной строки `cmd.exe` несколько меняется синтаксис, т.к. `^` это управляющий символ `cmd.exe`. Например, вместо `git.exe rebase -i 2385397^1` нужно писать `git.exe rebase -i 2385397^^1`.
    2. Маски файлов, вроде вышеописанного `git add *.cpp` не "разворачиваются" в список файлов, то есть аргументы передаются без изменений и git самостоятельно выполняет поиск подходящих файлов. В итоге мы имеем ошибочное поведение когда `git add *.cpp` добавляет файлы из подкаталогов.
    3. В консоли `cmd.exe` (если только она не в ConEmu запущена) нельзя использовать 256 цветов в Vim.
  
  **Ссылки**
  - [Stackoverflow - Разница в использовании git cmd и git bash под windows](https://ru.stackoverflow.com/questions/512702/%D0%A0%D0%B0%D0%B7%D0%BD%D0%B8%D1%86%D0%B0-%D0%B2-%D0%B8%D1%81%D0%BF%D0%BE%D0%BB%D1%8C%D0%B7%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B8-git-cmd-%D0%B8-git-bash-%D0%BF%D0%BE%D0%B4-windows)
  - [Stackoverflow - In the install path of Git for Windows, what's the difference between ./git-bash.exe and bin/bash.exe and bin/sh.exe?](https://stackoverflow.com/questions/53980686/in-the-install-path-of-git-for-windows-whats-the-difference-between-git-bash)

<br></p></details>

<details><summary><b>Различия git-bash.exe, bash.exe, sh.exe в Windows</b></summary><p>

- В папке git для Windows есть 3 exe файла: `git-bash.exe`,`bin/bash.exe`, `bin/sh.exe`. В чём различия?
- `sh.exe` и `bash.exe` - это оболочки. Примеры оболочек: cmd, powershell, sh, bash, zsh и т.д. Bash и zsh — более мощные версии sh.
- `git-bash.exe` - это очень простое приложение-терминал `mintty`, которое автоматически открывает оболочку `bash`.

<br></p></details>

<details><summary><b>Node JS command prompt</b></summary><p>

- Это ярлык, который сначала запускает `cmd.exe`, а затем `node.exe` (через `.bat`). Аналогично тому, если бы вы сами запустили `[win+r] > cmd.exe > [enter]` и там запустили `node.exe` (через `.bat`).

<br></p></details>

<details><summary><b>Windows PowerShell</b></summary><p>

  - расширяемое средство автоматизации от Microsoft, состоит из
    - оболочки с интерфейсом командной строки
    - сопутствующего языка сценариев.
  - построен на базе .NET
  - Дополнительно предоставляет доступ к COM, WMI и ADSI, позволяет выполнять обычные команды командной строки
  - Скрипты Windows PowerShell хранятся в виде обычных текстовых файлов с расширением .ps1. Запустить их двойным кликом нельзя: нужно правой кнопкой мыши вызвать контекстное меню и выбрать пункт «Запустить в PowerShell»

**Ссылки**
  - [Habr - Что такое Windows PowerShell и с чем его едят? Часть 1: основные возможности](https://habr.com/ru/company/ruvds/blog/487876/)
  - [Windows PowerShell ISE и Windows PowerShell: в чем разница?](https://okzu.ru/windows-powershell-ise-i-windows-powershell-v-chem-raznicza/)

<br></p></details>

<details><summary><b>Windows PowerShell ISE</b></summary><p>
  
  - Integrated Scripting Environment — Интегрированная Среда Сценариев
  - является полноценной средой разработки с поддерживающим вкладки и подсветку синтаксиса редактором кода, конструктором команд, встроенным отладчиком и другими программистскими радостями. Если в редакторе среды разработки после имени команды написать знак дефис, вы получите в выпадающем списке все доступные параметры с указанием типа.

**Ссылки**
  - [Windows PowerShell ISE и Windows PowerShell: в чем разница?](https://okzu.ru/windows-powershell-ise-i-windows-powershell-v-chem-raznicza/)

<br></p></details>

<details><summary><b>Command.com</b></summary><p>

  - интерпретатор командной строки в операционных системах DOS, OS/2, семейства Windows 9x и ряда других.
  - 2 режима работы
    - интерактивный, когда пользователь вводит с клавиатуры команды, которые немедленно выполняются.
    - пакетный, когда COMMAND.COM выполняет последовательность команд, заранее сохранённую в пакетном файле с расширением .BAT.

<br></p></details>

<details><summary><b>Bash</b></summary><p>

  - Одна из наиболее популярных современных разновидностей командной оболочки UNIX. Особенно популярна в среде Linux, где она часто используется в качестве предустановленной командной оболочки.
  - командный процессор, работающий, как правило, в интерактивном режиме в текстовом окне. Bash также может читать команды из файла, который называется скриптом (или сценарием)

  **Ссылки**
  - [Wikipedia - Bash](https://ru.wikipedia.org/wiki/Bash)

<br></p></details>


**Прочее**
  - В Windows, при верной настройке, везде запускается cmd + поверх нее запускается приложение с доп. возможности (GitBash, Node JS command prompt и т.д.). Это приложение добавляет разные доп. функции (типо автодополнения команд) + позволяет быть уверенным, что все команды выполнятся в нужных каталогах, с использованием нужных путей. Поэтому, лучше работать в специализированной консоли, а не делать всё через какую-то одну.
  - С npm лучше работать через Node JS command prompt


**Ссылки**
- [Wikipedia - Интерпретатор командной строки](https://ru.wikipedia.org/wiki/%D0%98%D0%BD%D1%82%D0%B5%D1%80%D0%BF%D1%80%D0%B5%D1%82%D0%B0%D1%82%D0%BE%D1%80_%D0%BA%D0%BE%D0%BC%D0%B0%D0%BD%D0%B4%D0%BD%D0%BE%D0%B9_%D1%81%D1%82%D1%80%D0%BE%D0%BA%D0%B8)
- [Wikipedia - Интерфейс командной строки](https://ru.wikipedia.org/wiki/%D0%98%D0%BD%D1%82%D0%B5%D1%80%D1%84%D0%B5%D0%B9%D1%81_%D0%BA%D0%BE%D0%BC%D0%B0%D0%BD%D0%B4%D0%BD%D0%BE%D0%B9_%D1%81%D1%82%D1%80%D0%BE%D0%BA%D0%B8)
- [Wikipedia - Системная консоль](https://ru.wikipedia.org/wiki/%D0%A1%D0%B8%D1%81%D1%82%D0%B5%D0%BC%D0%BD%D0%B0%D1%8F_%D0%BA%D0%BE%D0%BD%D1%81%D0%BE%D0%BB%D1%8C)
- [ debuntu.ru - Чем консоль отличается от терминала](https://debuntu.ru/a/chem-konsol-otlichaetsya-ot-terminala/)
  <br> 
  <br> 

*[Legmo, 2019-2023](https://github.com/Legmo/notes/)*