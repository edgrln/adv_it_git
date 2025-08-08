Ввести информацию о разработчике

```bash
git config --global user.name "Edgar Lakshin"
git config --global user.email "e.lakshin@gmail.com"
```

Посмотреть информацию о разработчике
```bash
git config -l
```


# Добавление и сохранение изменений


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

```bash
git commit -m "first commit"
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

```bash
git log --pretty=oneline
```

# Создание SSH ключа

Посомтреть содержимое в папке ~/.ssh/
```bash
ls -l ~/.ssh/
```
Зайди в директорию ~/.ssh/
```bash
cd ~/.ssh/
```

Посмотреть ключ в файле id_rsa.pub
```bash
cat ~/.ssh/id_rsa.pub
```

# Подключиться к удаленному репозиторию


Посмотреть привзяанный удаленный репозиторий
```bash
git remote -v
```

Подключить удаленный репозиторий
```bash
git remote set-url git@github.com:edgrln/adv_it_git.git
```

…or create a new repository on the command line
echo "# adv_it_git" >> README.md

```bash
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:edgrln/adv_it_git.git
git push -u origin main
```


…or push an existing repository from the command line
```bash
git remote add origin git@github.com:edgrln/adv_it_git.git
git branch -M main
git push -u origin main
```



🔧 Вариант 1 — если ты хочешь объединить локальные и удалённые изменения:
```bash
git pull origin main --rebase
git push origin main
git pull --rebase подтянет коммиты с GitHub и "поставит" твои поверх них (чисто и аккуратно)
```

Затем push уже будет успешным

⚠️ Вариант 2 — если на GitHub только тестовые/ненужные коммиты, и ты хочешь принудительно переписать историю (осторожно):
```bash
git push origin main --force
```
🔥 Опасно! Это удалит коммиты на GitHub, которых нет у тебя локально.
Используй только если ты уверен, что хочешь заменить удалённую ветку своей локальной версией.



# Работа с ветками

Создать новую ветку
```bash
git branch feater_gcp
```

Посмотреть список веток
```bash
git branch
```

Переключиться на ветку feater_gcp
```bash
git checkout feater_gcp
```

Переключиться на ветку main
```bash
git checkout main
```

Удалить ветку
```bash
git branch -d feater_gcp
```

Создать ветку и сразу на нее переключиться
```bash
git checkout -b denis_fix_error
```


Смерджить 2 ветки
```bash
git merge feater_gcp
```

Переключиться на коммит 9292eb6bc70190df467a7df8bdbd73b7ea508a04
```bash
git checkout 9292eb6bc70190df467a7df8bdbd73b7ea508a04
```

Временно отложить изменения текущей директории
```bash
git stash
```

Вернуть изменения обратно (самый частый случай)
```bash
git stash pop
```

Посмотреть, что в stash-е
```bash
git stash list
```


✅ 3. Восстановить конкретный stash (если их несколько)
```bash
git stash apply stash@{1}
```

✅ 4. Удалить stash, если он больше не нужен
```bash
git stash drop stash@{0}         # удалить конкретный
git stash clear                  # удалить все
```


Изменить commit
```bash
git commit --amend
```

Удалить 2 последних коммита (навсегда)
```bash
git reset --hard HEAD~2
```


Удалить 3 последних коммита
```bash
git reset --soft HEAD~1
```





```bash
git commit -m "Git commands"
```

# Порядок работы с GitHub

✅ Как создать Pull Request на GitHub
Обычно процесс выглядит так:

1. Сделай новую ветку:
```bash
git checkout -b my-feature
```

2. Добавь коммиты:
```bash
git add .
git commit -m "Добавил новую фичу"
```

3. Запушь ветку на GitHub:
```bash
git push origin my-feature
```

4. 🧠 Создай Pull Request через веб-интерфейс GitHub:
Перейди по ссылке, которую GitHub покажет после push, или вручную открой:
https://github.com/USERNAME/REPO_NAME/compare
И выбери:
base: main ← compare: my-feature

🛠️ Командой через GitHub CLI (если установлен)
Если у тебя установлен GitHub CLI (gh), можно сделать PR из терминала:

```bash
gh pr create --base main --head my-feature --title "Добавил фичу" --body "Описание изменений"
```

Удалить удаленную ветку 
```bash
git push origin --delete my-feature
```



# Работа с тегами
Создать тег
```bash
git tag v1.0
```

Опубликовать тег
```bash
git push origin v1.0
```