![Logo](git-blog-header.png)

# Работа с Git

## 1. Проверка наличия установленного Git
В терминале выполнить команду `git --version`, если Git установлен появиться сообщение с информацией о версии программы. Иначе будет сообщение об ошибке.

## 2. Установка Git
 Загружаем последнюю версию Git с сайта https://git-scm.com/downloads
 Устанавливаем с настройками по умолчанию.

 ## 3. Настройка Git
 При первом использавнии Git необходимо представиться. Для этого нужно ввести в терминале две команды:

```
 git config --global user.name "Ваше имя латиницей"
 git config --global user.email почта@gmail.com
 ```

 ## 4. Инициализация репозитория
С помощью команды **git init** в терминале для папки/файла "включается" Git - в папке появляется скрыйтая папка .git со служебными файлами. Теперь Git моежт отслежвиать все изменения, папка будет определяться как git-репозиторий.

 ## 5. Запись изменений в репозиторий 
Для записи изменений в репозиторий и их просмотра испльзуются следующие команды:
* git status
* git add
* git commit
* git diff

 Команда **git status** показывает в какие файлы в каком состоянии находятся(отслеживается /не отслеживается) и в какой ветке мы находимся.
 Команда **git add "название_файла"** (**git add .** добаляет папку целиком)добавляет файл добавляет файл под контроль Git(файл начинает отследиваться).  
 Команда **git commit -m "комментарий"** фиксирует и сохраняет состояние файла на данный момент в локальном репозитории.
 Команда **git diff** покажет различия между последним закоммиченный состоянием файла и текущем, если послн последнего коммита изменения не вносились, то команда ничего не вернет.

 ## 6. Просмотр истории коммитов
Для просмотра истории коммитов используется команда **git log**.
У каждого коммита будет хеш-код, автор(+почта) и дата и время сохранения(от старых к новым) и сам текст коммита.
**git log --oneline** выводит каждый коммит в одну строку

 ## 7. Перемещение между сохраненными коммитами

 Для перемещения между сохраненными коммитами испульзуются команды:
 * git checkout хеш-код - возвращает в состояние. в котором был сделан коммит;
 * git switch -  - возвращает в актуальное состояние;
 * git switch -c "new-branch-name" - создает и переносит нас на новую ветку.

# 8. Игноррование файлов
Для того, чтобы исключить из отслеживания репохиторием определенные папки или файлы, необходимо создать там файл ***.gitignore*** и записать в него их названия или шаблоны, соответствующие папкам/файлам.

# 9. Создание веток в Git
По умолчанию имя основной ветки в Git - **master**
Создатьсновую ветку можно командой 
```
git branch new_branch
git checkout -b new_branch
```

Список веток в репозитории можно посмотреть в помощью команды `git branch`

# 10. Слияние веток и разрешение конфликтов
Для слияния выбранной ветки с текущей нужно выполнить команду `git merge name_branch`
 
# 11. Работа с удаленным репозиторием

1. Создать аккаунт на GitHub.
2. Создать локальный репозиторий.
3. Создать удаленный репозиторий.
4. Связать удаленный репозиторий с локальным.

Добавить удаленный репозиторий к проекту можно с помощью команды 
```
git remote add "name_repository" "url-адрес репозитория"
```

Для получения и слияния изменений из удаленного репозитория используется команда:
 ```
git pull
``` 

Скопировать удаленный репозиторий на свой компьютер можно с помощью команды:
```
git clone "url-адрес репозитория"
```

Для отправки данных локального репозитория в удаленный репозиторий(связанный с проектом), используется команда:
```
git push
```