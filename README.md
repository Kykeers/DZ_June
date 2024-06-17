# DZ_June
Андрейченко Яна Борисовна
# Инструкция по работе с Git

## Установка Git

### Windows
1. Скачайте установочный файл с [официального сайта Git](https://git-scm.com/download/win).
2. Запустите установочный файл и следуйте инструкциям мастера установки.
 
### macOS
1. Установите [Homebrew](https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh), если он еще не установлен
    
2. Установите Git через Homebrew:
    
    ```
    brew install git
    ```
    
### Linux
На большинстве дистрибутивов Linux Git можно установить через менеджер пакетов:

- ***Debian/Ubuntu***:
    ```
    sudo apt-get update
    sudo apt-get install git
    ```

- ***Fedora***:
    ```
    sudo dnf install git
    ```

- ***Arch Linux***:
    ```
    sudo pacman -S git
    ```
## Настройка Git

После установки Git необходимо настроить ваше имя пользователя и email:
```
git config --global user.name "Ваше Имя"
git config --global user.email "ваш.email@example.com"
```
## Основные команды Git

### Создание репозитория

Создать новый репозиторий можно с помощью команды:
```
git init
```
### Клонирование репозитория

Для клонирования существующего репозитория используйте команду:
```
git clone <url-репозитория>
```
### Проверка состояния репозитория

Для проверки состояния репозитория используйте команду:
```
git status
```
### Добавление изменений в индекс

Чтобы добавить изменения в индекс (staging area), используйте команду:
```
git add <имя_файла>
```
Для добавления всех изменений:
```
git add .
```
### Коммит изменений

Для сохранения изменений в локальный репозиторий используйте команду:
```
git commit -m "Сообщение коммита"
```
### Просмотр истории коммитов

Для просмотра истории коммитов используйте команду:
```
git log
```
### Отправка изменений на удаленный репозиторий

Чтобы отправить изменения на удаленный репозиторий, используйте команду:
```
git push origin <ветка>
```
### Обновление локального репозитория

Чтобы получить изменения из удаленного репозитория, используйте команду:
```
git pull origin <ветка>
```
### Создание новой ветки

Для создания новой ветки используйте команду:
```
git branch <имя_ветки>
```
### Переключение между ветками

Для переключения на другую ветку используйте команду:
```
git checkout <имя_ветки>
```
### Слияние веток

Чтобы слить изменения из одной ветки в другую, сначала переключитесь на целевую ветку, затем выполните команду:
```
git merge <имя_ветки>
```
## Заключение

Это базовые команды для работы с Git. Для более углубленного изучения рекомендуется ознакомиться с [официальной документацией Git](https://git-scm.com/doc).
