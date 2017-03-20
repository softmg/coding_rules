# Правила работы с git на проекте

* В каждом проекте с git в корне должен быть файл .gitignore

* Для маленьких проектов все коммиты делаем в ветке master с названиями коммита в стиле <short_description> #<number-in-redmain>
<number-in-redmain> - номер из проекта http://redmine.softmg.ru/projects/<project name>

* Для средних проектов:

Для сравнительно больших проектов (при участии больше одного программиста на проекте) все задачи делаются в отдельных ветках. Существует два типа веток:

**feature, hotfix**

feature - объёмная история с любым приоритетом. (В крупных проектах создается от ветки develop)

hotfix - срочные баги или мелкие правки.

Принятое именование веток:

feature: <short_description>-<number-in-redmain>, пример: testdrive_year-2167

hotfix: hotfix-<number-in-redmain>, пример: hotfix-2213

<number-in-redmain> - номер из проекта http://redmine.softmg.ru/projects/<project name>


Как создавать ветку:

Сначала проверяем есть ли ветка в проекте

```
#!git
git fetch --all
git checkout <название ветки>
git pull origin/<название ветки>
```

Если ветки нет, то для веток feature и hotfix в ветке master

```
#!git
git checkout master
git pull origin/master
git checkout -b <название ветки>
... (доработка кода и коммит)
git push origin/<название ветки>
```

Для ветки hotfix делается всё тоже самое, но в ветке master

Слияние веток может делать как разработчик, так и главный программист.

* Для крупных проектов проектов используется следующий [git flow](http://nvie.com/posts/a-successful-git-branching-model/)

В крупных проектах добавляется следующие типы веток:

**release, develop**

release - ветка для последующего выката в релиз. Создаётся чтобы добить правки по текущим историям и чтобы другие недоработанные изменения не заливать в релиз.
(Используется в крупных проектах вместе с веткой develop для выката изменений с develop в master)

Принятое именование веток:
release: release-<number-version>, пример: release-0.1

Если ветки нет, то для веток feature и release в ветке develop

```
#!git
git checkout develop
git pull origin/develop
git checkout -b <название ветки>
... (доработка кода и коммит)
git push origin/<название ветки>
```

Для ветки hotfix делается всё тоже самое, но в ветке master

```
#!git
git checkout master
git pull origin/master
git checkout -b <название ветки>
... (доработка кода и коммит)
git push origin/<название ветки>
```

При мердже hotfix в master рекомендованно проставлять версию (v1.0.0), где первая цифра указывает на мажорную версию, вторая на минорную, третья - версия хотфиксов
В основу заложено [http://semver.org/lang/ru/](семантическое версионирование)

Для создания тега сначала проверяем, актуальный тег
```bash
git describe
```

Далее создаем следующий тег:
```bash
git tag -a<new version> -m"<shrot description>"
```

**Слияние веток рекоммендовано делать главному программисту.**