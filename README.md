# Краткая инструкция для работы с Git

## Что такое Git?
Git - это одна из реализаций распределенных систем контроля версий, имеющая как локальные, так и удаленные репозитарии. Является самой популярной реализацией систем контроля версий в мире.
## Подготовка репозитария
Для создания репозитария необходиом выполнить команду *git init* в папке с репозитарием и у Вас создатся репозитарий (появится скрытая папка .git).

## Создание коммитов

### git add - добавление файла в индекс
Для добавления изменений в коммит (в индекс репозитария) используется команда *git add*. Чтобы использовать команду *git add*, напишите *git add <имя файла>*. Командой можно добавить новые файлы в индекс, добавить измененные (уже входящие в индекс - при этом фиксируются изменения на данный момент), удалить из индекса удаленные.

### git rm - удаление файла
Для удаления файлов из индекса используется команда *git rm*. Чтобы использовать команду *git rm*, напишите *git rm <имя файла>*. Команда удаляет файл как из индекса, так и из рабочего каталога. Если сначала удалить файл в рабочем каталоге, то последующий вызов команды только удалит файл из индекса. Если нужно сохранить файл в рабочем каталоге и удалить, но удалить его из индекса (сделать снова не отслеживаемым), то можно указать параметр *'cached'*. В команду git rm можно передавать файлы, каталоги или шаблоны. Это означает, что вы можете сделать что-то вроде: *git rm log/\\*.log*. Обратите внимание на обратный слеш (\\) перед *. Он необходим из-за того, что Git использует свой собственный обработчик имён файлов вдобавок к обработчику вашего командного интерпретатора. Если в файл внесены изменения, то вышестоящая команда выдаст ошибку, для принудительного удаления файла нужно указать параметр *-f*.

### git mv - перемещение/переименование файла
Команда перемещает/переименования файла: *git mv <file_from> <file_to>* Фактически это просто замена группы команд:

*mv <file_from> <file_to>\
git rm <file_from>\
git add <file_to>*

Так как git отслеживает файлы только по имени, то непосредственно отслеживать переименование или перемещение он не умеет. Переименованный/перемещенный файл будет добавлен в индекс как новый.

### git status - просмотр состояния репозитория (индекса)
Для того, чтобы посмотреть состояние репозитория, используется команда *git status*. Для этого необходимо в папке с репозиторием написать *git staus*, и Вы увидите были ли изменения в файлах, или их не было.

### git diff - просмотр отличий (измнений)
Ппросмотреть, что именно изменено можно командой *git diff*. Данная команда выводит список измнений во всех файлов, изменения которых еще не добавлены в индекс. При этом выводятся сравнивается снимок, уже помещенный в индекс (или хранящийся в репозитарии, если команда *add* еще не использовалась) и текущий файл. Чтобы посмотреть отличия от последнего коммита, то можно использовать параметр *staged* или *cached*: *git diff--staged*. Сравнение происходит одним из встроенных инструментов diff (по-умолчанию применяется алгоритм Майерса) или можно указать на внешний инструмент.

### git commit - создание коммитов
Для того, чтобы создать коммит (сохранение), необходимо выполнить команду *git commit*. Выполняется она так:

*git commit -m "Комментарий к точке ветки репозитария"* (можно использовать одинарные кавычки)

Если не указать параметр *m*, то git вызовет для написания комментария редактор (обычно консольный), зарегистрированный в системе по-умолчанию, и будет ждать вывода от него.

Если нужно исправить комментарий последнего коммита, то это можно сделать командой *git commit --amend -m "<Новый комментарий>"*. Эта команда также добавит незафкисированные измнения в индексе на данный момент к последнему коммиту, не создавая новый. Если нужно добавить только изменения, и не изменять комментарий, то можно передать параметр *no-edit*. Фактически создается новый коммит с новым идентификатором, а старый просто удаляется из истории коммитов.

### Просмотр коммитов
Увидеть весь список коммитов можно командой *git log*

### Переход к коммиту
Для того, чтобы перейти к ранее сохраненному состоянию (коммиту - все файлы, которые входят в сохранненый коммит репозитария будут соответствовать сохраненным в коммите данным), следует использовать команду *git checkout <часть идентификатора коммита или имя>*. Например, чтобы перейти к последнему коммиту, сохраненному в точке ветки master, необходимо написать *git checkout master* (важно - если сейчас текущая ветка итак указанная, то ничего не произойдет, даже если указатель сейчас не на последнем коммите этой ветки). Чтобы перейти к произвольной точки, нужно указать ее идентификатор или первые символы (не менее 4). Например, *git checkout 1234*.

## Управление ветками репозиторя

### Создание и удаление ветки
Для создания новой ветки следует использовать команду *git brunch*. Без дополнительных параметров команда отображает список имеющихся в репозитории веток и отмечает текущую. Для создания новой ветки нужно передать первым параметром имя ветки: *git brunch master2*. Для удаления ветки можно использовать параметр *-d*: *git brunch -d master2*. Если в настоящий момент есть не закоммиченные изменения, то для принудительного удаления следует использовать параметр *-D*. Создать новую ветку и сразу перейти к ней можно командой *checkout -b <имя новой ветки>*.

### Выбор ветки
Для перехода к ветке следует использовать уже известную команду *git checkout*, указав в качестве идентификатора точки имя ветки. Например, чтобы перейти к ветке master2, нужно написать *git checkout master2*.

### Слияние веток
Для слияния веток используется команда *merge*. Для слияние нужно сначала сделать текущей основную ветку и даже выполнить команду *git merge <имя другой ветки>*. Если в процессе слияния будут обнаружены конфликты, то git вставит в файл фрагменты из обоих веток, отделив их служебными символами. При этом коммита сделанных изменений не произойдет. Вывод команды будет содержать соответсвующие изменения. Нужно самостоятельно отредактировать файлы, разрешив конфликты и уже после этого добавить файлы в индекс и выполнить коммит. При этом сделанный коммит будет содержать идентификаторы слитых коммитов (как и при автоматическом коммите, когда конфликтов нет, но слияние происходило, в случае простого переноса указателя на последний коммит, нового коммита добавлено не будет).

## Удаленный и локальный репозитарий
Git поддерживает не только управление одним репозитарием, но и синхронизацию нескольких репозитариев между собой. При этом происходит не полная синхронизация, а синхронизация одной из веток, таким образом разные репозитории могут не быть полными репликами друг друга. Репозитарий, с котормы мы сейчас работаем (в контексте которого выполняются команды Git) называется локальным, другой репозитарий - удаленным. Удаленнный репозитарий может быть на этом же хосте, но в другой папке или же на другом хосте (в локальной или даже глобальной сети). Часто выбирается один репозитарий, который считается главным, именно в нем будут вся история и все ветки. Для локальной работы делается клон данного репозитария (обычно главной ветки) и вся работа ведется с ним, затем изменения передаются в главный репозитарий. В такой схеме локальных репозитариев может быть сколь угодно много. Взаимодействие с удаленным репозитарием происходит по схеме клиент-сервер, на удаленном хосте (если это не локальный хост) должет быть установлен git-сервер, git (клиент) при выполнении команд обращается к нему по указанному адресу и протоколу. Поддерживаются разные протоколы, в том числе http(s). Локальный репозитарий не просто является копией (репликой) удаленного, но и хранит связь для веток, с какими ветками удаленного репозитария связана ветка локального.

### Созадние локального репозитария путем клонирования удаленного репозитария
Клонирование репозитория осуществляется командой git clone <url>. Это команда создает в текущем каталоге подкаталог с именем удаленного репозитария, создает в нем подпаку ".git", скачивает все данные для этого репозитория и извлекает рабочую копию последней версии. Для того, чтобы клонировать репозиторий в каталог с именем, отличающимся от оригинального, необходимо указать желаемое имя, как параметр командной строки: *git clone <url> <требуемое имя>*. Команда клонирования также добавляет ссылку на удаленный репозитарий под именем *origin* и назначает для каждой ветки ветку удаленного репозитария.

### Добавление и удаление ссылки на удаленный репозитарий
Для управления ссылками на удаленные репозитарии используется команда *git remote*. Для добавления удаленного репозитария нужно использовать команду *git remote add <имя удаленного репозитария> <адрес удаленного репозитария>*. Для удаления удаленного репозитария нужно использовать команду *git remote rm <имя удаленного репозитария>*. Для переименования удалённого репозитория можно выполнить *git remote rename*.

### Просмотр удаленных репозитариев
Для того, чтобы просмотреть список уже настроенных удалённых репозиториев, вы можете запустить команду git remote. Она выведет названия доступных удалённых репозиториев. Если вы клонировали репозиторий, то увидите как минимум origin — имя по умолчанию, которое Git даёт серверу, с которого производилось клонирование в рамках репозитария.

Вы можете также указать ключ -v, чтобы просмотреть адреса для чтения и записи, привязанные к репозиторию:

*git remote -v\
origin	https://github.com/\<user>/<name\> (fetch)\
origin	https://github.com/\<user>/<name\> (push)*

Если у вас больше одного удалённого репозитория, команда выведет их все.

### Получение изменений из удалённого репозитория — Fetch и Pull
Для получения (загрузки) данных из удаленного репозитария предназначена команда *git fetch [remote-name]*.Данная команда связывается с указанным удалённым репозитарем и забирает все те данные оттуда, которых в локальном ещё нет. После того как вы выполнили команду, у вас должны появиться ссылки на все ветки из этого удалённого проекта, которые вы можете просмотреть или слить в любой момент. При клонировании автоматически добавляется репозитирий под именем *origin*. Таким образом, git fetch origin извлекает все наработки, отправленные на этот сервер после того, как вы его клонировали (или получили изменения с помощью fetch). команда git fetch забирает данные в ваш локальный репозиторий, но не сливает их с какими-либо вашими наработками и не модифицирует то, над чем вы работаете в данный момент. Вам необходимо вручную слить эти данные с вашими, когда вы будете готовы. Если ветка настроена на отслеживание удалённой ветки, то вы можете использовать команду *git pull* (затянуть их к себе) чтобы автоматически получить изменения из удалённой ветки и слить их со своей текущей.

### Отправка изменений в удалённый репозиторий - Push
Чтобы отправить данные на сервер (протолкнуть их на сервер), следует дать Git команду *git push <remote-name> <branch-name>*. Чтобы отправить локальную ветку master на сервер origin (клонирование  настраивает оба этих имени автоматически), можно выполнить следующую команду для отправки своих коммитов:

*git push origin master*
