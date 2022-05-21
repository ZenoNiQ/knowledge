# Visual Studio Code. Настройка и применение. Часть 1

Первая часть глубоко субъективного гайда по VSCode.

Статья получилась объёмная, поэтому я решил разделить её на две части. Перейти ко 2-ой части можно по этой ссылке.

Некоторое время назад перешёл на редактор кода VSCode, и в ходе изучения у меня скопился набор общих подходов и настроек, которыми было бы полезно поделиться. В данной статье затронуты все аспекты, к которым я прибегаю в ходе своей рабочей практики. Выбор редактора и его настройка — вещь глубоко субъективная, поэтому и этот гайд я решил сделать таким же персонифицированным. Здесь нет призывов к действию, практически нет и общего описания функций редактора — за этим вы можете обратиться к официальной документации, кстати хорошо написанной. Я же здесь просто последовательно пройдусь по различным аспектам применения редактора и покажу, как лично я им пользуюсь. Если после прочтения раздела вам понравится описанный в нём подход, то вы можете делать также, если же у вас уже есть сформировавшееся видение на этот счёт, то просто посмотрите на иную точку зрения. Так что тут будет много “я”, но так и задумано 😉

Сразу оговорюсь, ввиду специальности описанный функционал будет подаваться под призмой frontend-разработки, хотя большая часть настроек имеет общий характер.

В вопросе пользования редакторов ранее я пользовался Sublime Text в его стандартной комплектации, т.к. он покорил меня своими функциями редактирования с множественным курсором, которые тогда были в новинку. Потом услышал про Brackets — он был заточен специально под frontend, в нём была возможность просмотра стилей блока прямо из разметки, так называемый “peek”, и поддерживался Live Reload. Однако он был гораздо медленнее и забагованее, чем Sublime, из-за чего на нагруженных рабочих проектах вкупе со слабым железом он стал неюзабелен. Так что после него я решил опробовать Atom — в принципе, приятный редактор, но пробыл на нём недолго по той же причине — он был быстрее, но всё равно периодически намертво зависал. Ну и в итоге я вернулся обратно на Sublime— он решил все вопросы со скоростью, и на этот раз я подверг его значительной кастомизации, и с десятком расширений он преобразился. С тех пор я был ярым сублаймщиком, пока не услышал про VSCode, который стали рекомендовать респектабельные разработчики из моей области на Западе, и в различных видеокурсах, где можно видеть редактор, я стал замечать в 95% VSCode. В общем, решил дать ему шанс.

Главное преимущество VSCode заключается в том, что он быстрый, как редакторы кода (быстрее только Sublime), но при этом функциональный, как полноценная IDE. Почему я никогда не пользовался IDE — потому что они тяжеловесные и в плане интерфейса сильно нагруженные. Это противоречит всем моим представлениям о работе фронтенда. VSCode же прост внешне, похож на кастомизированный Sublime, но при этом на другом уровне функциональности, специально заточен под фронтенд и постоянно развивается (разработчики ежемесячно выкатывают апдейт с новыми фишками) — чего ещё можно желать?

Так что давайте пройдёмся по различным аспектам этого редактора, посмотрим как получить профит от его сильных сторон, и как ещё улучшить его дефолтную конфигурацию.

В рамках 1-ой части мы рассмотрим следующие аспекты работы с редактором:

    Палитра команд. Это основной интерфейс для вашего общения с редактором. Рассматриваем разнообразные способы его применения.
    Управление настройками. Общий подход к заданию настроек. Прописываем ряд полезных глобальных настроек и решаем вопрос синхронизации между различными рабочими устройствами.
    Управление рабочим пространством. Подходы по оптимизации пространства редактора, отводимого под работу с кодом.
    Написание кода. Инструменты и подходы, позволяющие ускорить набор кода. Использование Emmet в VSCode и редактирование с множественным курсором.
    Навигация по проекту. Преимущества символьного поиска над текстовым в ряде типовых ситуаций. Рассматриваем способы применения механизма хлебных крошек для ориентирования в тяжёлых файлах.
    Работа с проектами. Подход к управлению проектами с возможностью быстрого переключения между ними.
    Встроенный терминал. Применение интегрированного терминала, как более удобная альтернатива сторонним приложениям.
    Система контроля версий. Встроенные возможности по работе с Git. Оборудуем VSCode ультимативным инструментом для навигации по истории коммитов.

[Source](https://medium.com/@p1t1ch/visual-studio-code-настройка-и-применение-часть-1-7f1a26806522)