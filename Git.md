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

### Полезные ссылки:
- Ой, блин, гит! (https://ru.hexlet.io/blog/posts/oh-shit-git)