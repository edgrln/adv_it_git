Ввести информацию о разработчике

```bash
git config --global user.name "Edgar Lakshin"
git config --global user.email "e.lakshin@gmail.com"
```

Посмотреть информацию о разработчике
```bash
git config -l
```

Инициировать локальный репозиторий
```bash
git init .
```

Добавить в индекс все файлы в директории
```bash
git add *
```

или Добавить в индекс все файлы в директории

```bash
git add .
```


# История изменений
Посомтреть текущей статус локального репозитория
```bash
git status
```

Файл .gitignore для игнорирования гитом файлов и папок


Убрать все изменения
```bash
git checkout -- <file name>
```

Покажет информацию, которая будет записана в Git log
```bash
git diff --staged
```



Сделать snapshot текущего состояния проиндекстированных файлов
```bash
git commit -m "My initial version"
```

История коммитов
```bash
git log
```

История коммитов (последний коммит)
```bash
git log -1
```

История коммитов (последний коммит) с детальной информацией
```bash
git log -1 -p
```



…or create a new repository on the command line
echo "# adv_it_git" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:edgrln/adv_it_git.git
git push -u origin main



…or push an existing repository from the command line
git remote add origin git@github.com:edgrln/adv_it_git.git
git branch -M main
git push -u origin main