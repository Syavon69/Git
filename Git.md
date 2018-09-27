## Основные команды GIT

- git status
- git add .
- git commit -m "GeekBrains > Yii2 > Lesson 4 > Complete"
- git push
- git pull
- git log

### Create a new repository on the command line
- echo "# converter" >> README.md
- git init
- git add README.md
- git commit -m "first commit"
- git remote add origin https://github.com/avshatalov48/converter.git
- git push -u origin master

### Push an existing repository from the command line
- git remote add origin https://github.com/avshatalov48/converter.git
- git push -u origin master

### Создание новой ветки
#### https://githowto.com/ru/creating_a_branch
- git checkout -b <имяветки> (является шорткатом для git branch <имяветки> за которым идет  git checkout <имяветки>)

### Операции отмены
#### https://git-scm.com/book/ru/v2/Основы-Git-Операции-отмены
Например, если вы фиксируете изменения, и понимаете, что забыли проиндексировать изменения в файле, который хотели включить в коммит, можно сделать примерно так:

- git commit -m 'initial commit'
- git add forgotten_file
- git commit --amend -m 'initial commit'

В итоге получится единый коммит — второй коммит заменит результаты первого.

### Переименование последнего коммита
#### https://ru.stackoverflow.com/questions/741280/как-переименовать-коммит-в-github
- git commit --amend -m 'Новое сообщение'
- git push --force origin <имя ветки на удаленном репозитории>

### Удаление последнего коммита (который ещё не запушен)
- git reset --hard HEAD~1
- HEAD~1 означает фиксацию перед головой

### Checkout
- git checkout ветка (переключиться на ветку)
- git checkout -b ветка (создать ветку из текущей и переключиться)

### Reset
- git reset --hard (отменить все незакоммиченное)
- git reset --hard HEAD~n (отменить все незакоммиченное и откатиться на n-коммитов)

### Удаление Git репозитория
Статья: http://gearmobile.github.io/git/github-how-to-delete-repository/
- Переходим в нужный репозиторий
- Копируем его имя
- Settings > Danger Zone (внизу страницы) > Delete this repository
- Вводим имя удаляемого репозитория
- Вводим пароль GiHub

### Stash
- Сохранения изменений: git stash
- Применение сохраненных изменений: git stash pop

### Убрать файл из отслеживания
- сделать git rm <название файла>, предворительно скопировав его, чтобы не потерять
- добавить файл в .gitignore
- закоммитить изменения

Если файл уже под контролем (был ранее добавлен в репозиторий), то .gitignore на нем работать не будет. Что, собственно, и логично. Есть два варианта:
- удалить файл -> закомитить -> добавить в .gitignore -> вернуть файл
- удалить из индекса (git update-index --assume-unchanged your-file) -> добавить в .gitignore

### Подробнее о файле .gitignore, наглядный пример:
```
# Игнор-лист файлов проекта
# Игнорировать ВСЕ файлы и директории, включая поддиректории и файлы в них
*
# ---- ФАЙЛЫ ----
# Игнорирование по типу файла, будут игнорироваться в АБСОЛЮТНО всех директориях
# Например /files/data.zip, /server.log, /uploads/users/data/info.xls
*.zip
*.log
*.pdf
*.xls
# Игнорирование файла во ВСЕХ директориях
# Например /params/db/config.php, /config.php
config.php
# Игнорирование конкретного файла ТОЛЬКО в корне проекта
# (корнём считается расположение файла .gitignore)
# Например НЕ БУДЕТ проигнорирован файл /db/config.php
/config.php
# Игнорирование конкретного файла ТОЛЬКО в указанной директории
# Например НЕ БУДЕТ проигнорирован файл /prod/params/config.php
/params/config.php
# ---- ДИРЕКТОРИИ ----
# Игнорирование всех файлов и папок ТОЛЬКО в конкретной директории(включая поддиректории и файлы в них)
# Например /images/user.jpg, /images/company/logo.png
# НЕ БУДУТ проигнорированы файлы и папки /prod/images/user.jpg
/images/*
# Игнорирование всех файлов и папок в ЛЮБЫХ директориях с указанным именем
# Например /images/user.jpg, /core/images/user.jpg
images/*
# Игнорирование ВСЕХ html-файлов в ОДНОЙ КОНКРЕТНОЙ директории(НЕ ВКЛЮЧАЯ поддиректории)
# Например /private/index.html
# НЕ БУДУТ проигнорированы файлы в /private/ivan/index.html
/private/*.html
# Игнорирование ВСЕХ html-файлов в КОНКРЕТНОЙ директории ВКЛЮЧАЯ поддиректории
# Например /private/info.html, /private/users/ivan/info.html
/private/**/*.html
# ---- РАЗНОЕ ----
# Исключение из игнорирования
# Игнорирование ВСЕХ файлов и папок внутри директории /secret,
# за исключением файла /secret/free.txt, он не будет проигнорирован
/secret/*
!/secret/free.txt
# Игнорирование файла с именем, содержащим спецсимволы
# Например !readme!.txt
\!readme!.txt
# Игнорирование всех JPG и JPEG файлов внутри директорий,
# которые начинаются на "h" и МОГУТ содержать ещё один символ после
# Например /images/h4/user.jpg, /images/h/company.jpeg
/images/h?/*.jp?g
```

### Полезные ссылки:
- Ой, блин, гит! (https://ru.hexlet.io/blog/posts/oh-shit-git)
- Как сделать свой первый Pull Request (https://rustycrate.ru/руководства/2016/03/07/contributing.html)
- Подробнее о файле .gitignore (http://orlov.io/ru/articles/podrobnee-o-faile-gitignore)