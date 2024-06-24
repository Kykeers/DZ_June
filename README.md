# DZ_June
# Clone repository dz

# Файл Readme  
## Сайт для тренировки навыков GIT: https://learngitbranching.js.org  
### Основные команды Git  
git init – инициализация локального репозитория  
git status – получить информацию от git о его текущем состоянии  
git add имя_файла – добавить файл или файлы к следующему коммиту  
git commit -m “message” – создание коммита.  
git reset хэш коммита - отменяет коммит  
git revert хэш коммита - отменяет коммит, создавая коммит об этом действии  
git restore хэш коммита - сброс состояния файла до того, на которое указать  
git log – вывод на экран истории всех коммитов с их хеш-кодами  
git reflog - выводит на экран полную истоию всех измнений, в том числе удаления коммитов  
git log graph - вывод на экран истории всех коммитов с графическими ветками  
git checkout – переход от одного коммита к другому (а также между ветками)  
git checkout -b имя_ветки - создание новой ветки и переход на нее  
git checkout имя_ветки^ - переместиться на один коммит вверх по ветке  
git checkout имя_ветки^^ - переместиться на два коммита вверх по ветке  
git checkout Имя_ветки~num - переместиться на указанное num количество коммитов вверх по ветке  
git branch - вывод списка всех веток  
git branch имя_ветки - создание новой ветки  
git branch -f имя_ветки номер коммита/HEAD^/HEAD~num - переносит ветку на указанный коммит или на указанное число коммитов от HEAD  
git checkout master – вернуться к актуальному состоянию и продолжить работу  
git diff - позволяет увидеть разницу между текущим файлом и законченным файлом  
git merge имя_ветки - слияние ветки с той веткой, в котрой находишься в данный момент  
git rebase имя_ветки - переносит все изменения ветки так что все изменения выглядят последовательно выполненными  
git reset HEAD~1/имя_ветки - отмена изменений на один коммит (работает для локального репозитория, но не работает для удаленного)  
git revert имя_ветки - отменяте одно изменение и делится этим изменением с пользователями этого репозитория  
git cherry-pick <commit 1> <commit 2> <...> - копирует несколько коммитов на то место, где сейчас находишься (для использования этой команды нужно точно знать хэши нужных коммитов)  
git remote show origin - показывает все изменения по потношению к удаленному репозиторию  
git remote -v - показывает путь для связи с удаленным репозиторием  
git remote remove origin - удаление удаленного репозитория  
git remote set-url origin <путь к удаленному репозиторию> - изменяет привязку локального репозитория к удаленному  
git remote add vendor <адресс удаленного репозитория> - добавляет еще один удаленный репозиторий к локальному  
git fetch --all - добавляет данные в локальный репозитроий из всех подключенных удаленных  
Создание удаленного репозитория на GitHub  
…or create a new repository on the command line echo "# GIT-instruction" >> README.md  

git init  
git add README.md  
git commit -m "first commit"  
git branch -M main  
git remote add origin https://github.com/Datitov1986/GIT-instruction.git  
git push -u origin main  
…or push an existing repository from the command line  

git remote add origin https://github.com/Datitov1986/GIT-instruction.git  
git branch -M main  
git push -u origin main  
…or import code from another repository  
You can initialize this repository with code from a Subversion, Mercurial, or TFS project.  
