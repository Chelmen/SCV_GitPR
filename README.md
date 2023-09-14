![Logo](Git-Logo-2Color.png)
# Работа с Git
## 1. Проверка наличия установленного Git
В терминале выполнить команду `Git --version`. Если Git установлен, появится сообщение с информацией о версии программы, иначе будет сообщение об ошибке.
## 2. Установка Git
Загружаем последнюю версию Git с [сайта](https://git-scm.com/downloads). Устанавливаем с настройками по умолчанию.
## 3. Настройка Git
При первом использовании Git необходимо представиться. Для этого нужно ввести в терминале две команды:
```Bash
git config --global user.name "Ваше имя английскими буквами"
git config --global user.email "Ваша почта@example.com"
```
## 4. Создание репозитория
Для создания репозитория пройдите в папку вашего проекта:
`cd <путь к вашему проекту>`
Далее, выполните команду:
`git init`
Теперь Git отслеживает изменения файлов вашего проекта.
## 5. Основные команды
```Bash
#Добавим все файлы проекта в нам будующий commit
git add .
#Или так
git add --all

#Если хотим добавить конкретный файл то можно так
git add <имя_файла>

#Теперь создаем commit. Обязательно указываем комментарий.
git commit -m "<комментарий>"

#Эта команда показывает состояния файлов в рабочем каталоге и индексе: какие файлы изменены, но не добавлены в индекс; какие ожидают коммита в индексе
git status

#Данная команда показывает разницу между текущим статусом и предыдущим сохранением
git diff

#Помощь по основным командам
git help
```
## 6. Просмотр и перемещение между версиями
Для просмотра истории(логов) коммитов воспользуйтесь следующей командой:
```Bash
git log

#Для вывода в одну строку
 git log --oneline

#Для вывода последних коммитов
 git log -<Число>
```
Для перехода к другой версии используйте команду:
```Bash
git checkout <№ commit>/<Имя объекта>
или
git switch <№ commit>/<Имя объекта>

Например, для возврата к состоянию мастер (последнему commit):
git checkout master
```
## 7. Игнорирование файлов
Для того, чтобы исключить из отслеживания в репозитории определенные файлы или папки необходимо создать там файл ***.gitignore*** и записать в него их названия или шаблоны, соответствующие таким файлам или папкам.
Также, можно исключать категории файлов по их расширению. Например, строка ***.png*** исключит из отслеживания все файлы с расширением .png
## 8. Создание веток в Git
Ветки в Git представляют собой указатель на снимок изменений. Если нужно добавить новую возможность или исправить ошибку (незначительную или серьезную), вы создаете новую ветку, в которой будут размещаться эти изменения.
По умолчанию название основной ветки - `master`
Создать ветку можно одной из команд:
```Bash
git branch <имя новой ветки>
git checkout -b <имя новой ветки>
git switch -c <имя новой ветки>
```
Для просмотра списка всех веток в репозитории следует ввести команду:
`git branch`
где зеленым подсвечивается, в какой ветке мы находимся.

## 9. Слияние веток и разрешение конфликтов
Для слияния выбранной ветки с текущей нужно выполнить команду
```Bash
git merge <Название выбранной ветки>
```
Если была изменена одна и та же часть файла в обеих ветках, то может возникнуть конфликт, который потребует участие пользователя.
После разрешения конфликта следует сделать коммит слияния.

## 10. Удаление веток
Для удаления ветки нужно перейти в соседнюю ветку (через команду git switch/checkout) и воспользоваться следующей командой:
`git branch -d <Имя ветки>`
Если данные не были перенесены в master, Git предложит варианты решения конфликта.

## 11. Работа с удаленными репозиториями

1. Создать аккаунт на GitHub.
2. Создать локальный репозиторий.
3. Создать удалённый репозиторий.

Добавить удаленный репозиторий к проекту:
```Bash
git remote add <Repo name> <URL repo>
```

4. Связать удалённый репозиторий с локальным.

Для получения и слияния изменений из удаленного репозитория используется команда `git pull`.

Отправить изменения локального репозитория в удаленный можно с помощью команды `git push`.
