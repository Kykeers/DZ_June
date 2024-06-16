# DZ_June
# First Seminar
* Ввести изменения
* Сохранить изменения (CTRL+s)
* Добавить с изменениямиж
* Закомитить

## git init
Инициализация гита
## git add file_name
Добавка файла в репозиторий
## git commit -m "comment"
Добавка коммита с комментарием
## git status
Статус состояния текущего репозитория
## git diff
Увидеть разницу между сохраненным и зафиксированным файлом
## git commit --amend -m "New instruction"
- Меняет коментарий последнего коммита
## git checkout название_коммита
- Переход на нужный коммит, достаточно нескольких первых символов названия для перехода, названия можно увидеть с помощью git log или git log --graph (видим граф иерархической последовательности коммитов)

## Creating branches
git branch branch_name

а чтобы сразу создать ветку и на нее перейти git checkout -b branch_name
## Merging branches
git merge branch_name
## Conflicts
конфликты возникают при затрагивании общего пространства


new information on the master for conflict
test of the conflict
## Delete of the branch

git branch -d branch_name

Выдаёт ошибку если что то не промержино

git branch -D branch_name 

Удаляет насильно

## Options to remote repository connection:
1. __*Or create a new repository on the command line*__
<ol type="a">
<li> echo "# Repos_name" >> README.md </li>
<li> git init </li>
<li> git add README.md </li>
<li> git commit -m "first commit" </li>
<li> git branch -M main </li>
<li> git remote add origin https://github.com/UserName/Repos_name.git </li>
<li> git push -u origin main </li>
</ol>

2. __*Or push an existing repository from the command line*__
<ol type="a">
<li> git remote add origin https://github.com/UserName/Repos_name.git </li>
<li> git branch -M main </li>
<li> git push -u origin main </li>
</ol>
