# DZ_June

## Создание репозитория

Команда: **git init**

В результате выполнения Git начнет отслеживать файлы проекта и будет записывать изменения в скрытую папку .git.

## Список базовых команд для перемещения по проекту

**_pwd_** — просмотр текущего местоположения;

**_ls_** — список папок и файлов в текущей директории, где была выполнена команда;

**_ls -a_** — список открытых и скрытых папок и файлов в текущей директории, где была выполнена команда;

**_cd ~_** — переход в домашнюю директорию текущего пользователя;

**_cd .._** — переход на один уровень вверх в иерархии файловой системы;

**_cd <folder_name>_** — переход в выбранную папку;

**_mkdir <folder_name>_** — создание папки с указанным именем.

## Добавление файлов в индекс

Команды: 

1. Добавление в индекс одного файла
**git add <file_name>**
2. Добавление в индекс нескольких файлов
**git add <file_name_1> <file_name_2> <file_name_3>**
3. Добавление в индекс всех измененных файлов
**git add .**

## Проверка статуса репозитория

Команда: **git status**

Показывает, какие неотслеживаемые файлы попали в проект, какие файлы находятся в индексе и какие сохранённые файлы вы изменили в репозитории.

## Добавление файлов в репозиторий

Команда: **git commit -m <"Commit message">**

Переносит файлы из индекса в репозиторий.

## Команды для работы с коммитами

### Просмотр журнала коммитов
Команда: **git log**

Показывает историю коммитов в обратном хронологическом порядке. Можно посмотреть хеш, сообщение, дату и автора коммита.

### Просмотр коммита
Команда: **git show**

Выводит информацию об одном коммите. Сообщение делится на два блока: часть с метаданными и список изменений, внесённых в коммит.

### Просмотр изменений до коммита
Команда: **git diff**

Показывает разницу между последним коммитом и текущим состоянием репозитория

### Откат коммита
Команда: **git reset**

Позволяет отменить любое количество сделанных коммитов и вернуть проект к какому-то состоянию в прошлом.

Опции: 

**_--soft_** - проект откатывается к указанному коммиту и переводит все последующие коммиты в индекс. Можно сразу сделать новый коммит и перезаписать историю проекта, оставив исходные файлы без изменений.

**_--mixed_** - откаченные файлы попадают в неотслеживаемую зону. Можно эти файлы изменить, удалить или вернуть обратно в индекс.
    
**_--hard_** - Проект откатывается к указанному коммиту и удаляет все последующие коммиты без возможности их восстановления.

## Ветвление

Основные команды:

**git branch <branch_name>** - создание новой ветки

**git branch** - просмотр веток

**git checkout** - переключение между ветками

**git merge** - слияние репозиториев

**git branch -d <branch_name>** - удаление ветки

## Удалённый репозиторий

### Привязка локального и удалённого репозитория

Команда: **git remote add**

Установление связи между локальным и удалённым репозиторием на GitHub. Первым шагом необходимо переместится в каталог с проектом. Затем вызвать команду git remote add, добавив два параметра - имя удалённого репозитория и его адрес:

_git remote add origin git@github.com:имя_профиля/имя_репозитория.git_

Для просмотра удаленных репозитеориев предназначена команда **git remote**, для просмотра удалённых URL-адресов необходимо при вызове команды добавить опцию — v

### Отправка/получение изменений удаленного репозитория

Для отправки изменений в удаленный репозиторий используется команда **git push**, а для получения (и сохранения их в локальный репозиторий) - **git pull**