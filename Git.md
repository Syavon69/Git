## Основные команды GIT

- git status
- git add .
- git commit -m "GeekBrains > Yii2 > Lesson 4 > Complete"
- git push
- git pull
- git log

### create a new repository on the command line
- echo "# converter" >> README.md
- git init
- git add README.md
- git commit -m "first commit"
- git remote add origin https://github.com/avshatalov48/converter.git
- git push -u origin master

### push an existing repository from the command line
- git remote add origin https://github.com/avshatalov48/converter.git
- git push -u origin master

### Создание новой ветки
- git checkout -b <имяветки> (является шорткатом для git branch <имяветки> за которым идет  git checkout <имяветки>)