# DZ_June

Changes from Sogdiana. (Это я в рамках урока проходила) 

# Конспект инструкции по работе с гитом (git)

## 1 Урок. Скачивание гита. Основные команды. 
1. Для начала необходимо скачать приложение git и VS Code.
2. Далее на рабочем столе создаем папку желательно на английском.
3. Заходим в VS Code. Оттуда открываем только что созданную папку.
4. Открываем терминал и прописываем туда следующую команду:
* git init - она позволяет гиту инициализоваться
5. Далее в VS Code создаем файл (с английским наименованием) в только что открытой папке, в конце этого папки прописываем .md
6. Добавляем эту папку с помощью команды:
* git add (и имя этой папки)- эта команда позволяет гиту отслеживать нашу папку и все изменения в ней.
7. Далее в самой папке можем вносить любые изменения.
8. внеся изменения и сохранив их с помощью ctrl+S мы их в терминале добавляем в папку с помощю команды git add (и имя этой папки). Далее делаем коммит:
* git commit -m "Любое название вашего коммита" - и нажимаем Enter

В гите также есть следующие команды:
* __git status__ - позволяет увидеть статус нашей папки на предмет неослеживаемых изменений
* __git log__ - данная команда показывает все коммиты которые вы совершали, их названия, которые вам будут необходимы чтобы к ним возвращаться.
* __git checkout (и первые 4 символа вашего коммита)__ - позволяет переходит на тот коммит который вы хотите
* __git diff__ - показвает чем отличается наш текущий файл и сзменениями от того, что уже сохранено (закоммичено).

## Урок 2. Работа с ветками. Основные команды.
Ветки это грубо говоря черновики для основной ветки **master**. Они позволяют нам создавать собственные изменения в скопированном тексте от ветки master в нашей созданной ветке.
1. Создаем новую ветку с помощью команды git branche branch_name (вконце название ветки)
2. Смотрим текущие ветки с помощью команды git branch
3. Переходим на созданную ветку с помощю команды git checkout branch_name.
4. Далее можем работать в этой ветке и создавать коммиты.
5. Можем соединить ветки с помощью команды git merge branch_name. 

__! Важно !__ Команда git merge вызывается с той ветки с которой мы хотим соединить нашу новую ветку т.е. будучи в ветке **master**.

6. Можем удалить ветку с помощью команды git branch -d branch name.
7. С помощью команды git log --graph можем вывести дерево наших коммитов.



