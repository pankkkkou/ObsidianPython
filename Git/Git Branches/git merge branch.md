
Слияние используется в Git, чтобы собрать воедино разветвленную историю. Команда `git merge` выполняет слияние отдельных направлений разработки, созданных с помощью команды [[git branch]], в единую ветку.

Обратите внимание: все приведенные ниже команды выполняют слияние в текущую ветку, в то время как целевая ветка остается без изменений. Поэтому команда `git merge` часто используется в сочетании с командами [[git checkout]] (для выбора текущей ветки) и [[git branch -d]] (для удаления устаревшей целевой ветки).

---

## Порядок действий 

---

Команда `git merge` объединяет несколько последовательностей коммитов в общую историю. Чаще всего команду `git merge`используют для объединения двух веток. Этот вариант слияния рассматривается в следующих примерах. В таких случаях команда `git merge` принимает два указателя на коммиты (обычно последние в ветке) и находит общий для них родительский коммит. Затем Git создает коммит слияния, в котором объединяются изменения из обеих последовательностей, выбранных к слиянию.

Представим, что у нас есть новая функциональная ветка, которая отходит от главной ветки `main`. И мы хотим объединить эту функциональную ветку с `main`.

![Слияние ветки feature с веткой main](https://wac-cdn.atlassian.com/dam/jcr:7afd8460-b7bf-4c42-b997-4f5cf24f21e8/01%20Branch-2%20kopiera.png?cdnVersion=1492)

![Окно консоли](https://wac-cdn.atlassian.com/dam/jcr:7816f6da-4c53-46c3-8df3-c125249a4f87/collaborating-workflows-cropped.png?cdnVersion=1492)



[Читать руководство](https://www.atlassian.com/ru/git/tutorials/learn-git-with-bitbucket-cloud)

При вызове этой команды произойдет слияние указанной функциональной ветки с текущей — в данном случае с веткой `main`. Git автоматически определяет алгоритм слияния (подробнее см. ниже).

![Новый узел коммита слияния](https://wac-cdn.atlassian.com/dam/jcr:c6db91c1-1343-4d45-8c93-bdba910b9506/02%20Branch-1%20kopiera.png?cdnVersion=1492)

Коммиты слияния отличаются от других наличием двух родительских элементов. Создавая коммит слияния, Git попытается автоматически объединить две истории. Однако если Git обнаружит, что вы изменили одну и ту же часть данных в обеих историях, сделать это автоматически не удастся. Это называется конфликтом управления версиями, и для его разрешения Git потребуются действия пользователя. 

## Подготовка к слиянию 

---

Перед слиянием следует предпринять несколько подготовительных действий, чтобы операция прошла без проблем.

## Проверка выбора принимающей ветки 

---

Выполните команду [[git status]]. Это позволит убедиться, что `HEAD` указывает на ветку, принимающую результаты слияния. При необходимости выполните команду [[git checkout]] <принимающая-ветка>, чтобы переключиться на принимающую ветку. Для примера выполним команду [[git checkout]].

## Получение последних коммитов из удаленного репозитория 

---

Убедитесь, что в принимающей ветке и ветке для слияния содержатся последние изменения из удаленного репозитория. Выполните команду [[git fetch]], чтобы получить из него последние коммиты. Затем убедитесь, что в ветке `main` также содержатся последние изменения. Для этого выполните команду [[git pull]].

## Выполнение слияния 

---

После указанных выше действий по подготовке можете приступать к слиянию. Для этого выполните команду git merge  <название ветки>, где <название ветки> — название ветки, которая будет объединена с принимающей.

## Ускоренное слияние 

---

Ускоренное слияние происходит, когда последний коммит текущей ветки является прямым продолжением целевой ветки. В этом случае для объединения истории Git не выполняет полноценное слияние, а просто переносит указатель текущей ветки в конец целевой ветки. Объединение историй проходит успешно, поскольку все коммиты целевой ветки теперь доступны из текущей ветки. Так, ускоренное слияние одной из функциональных веток с веткой `main` будет выглядеть следующим образом:

![После ускоренного слияния главный узел и находящийся после него функциональный узел сошлись в один узел](https://wac-cdn.atlassian.com/dam/jcr:d90f2536-7951-4e5e-ab79-f45a502fb4c8/03-04%20Fast%20forward%20merge.svg?cdnVersion=1492)

Однако выполнить ускоренное слияние не получится, если ветки после разделения развивались независимо друг от друга. Если до целевой ветки нет прямого пути, Git будет вынужден объединить их методом трехстороннего слияния. Такое слияние выполняется с помощью специального коммита, который служит для объединения двух историй. Метод называется трехсторонним, поскольку Git использует три коммита для создания коммита слияния (последние коммиты двух веток и общий родительский элемент).

![Схема после трехстороннего слияния](https://wac-cdn.atlassian.com/dam/jcr:91aece4a-8fa0-4fc3-bae9-69d51932f104/05-06%20Fast%20forward%20merge.svg?cdnVersion=1492)

Хотя можно применять любую из этих стратегий слияния, многие разработчики предпочитают метод ускоренного слияния (с помощью [перебазирования](https://www.atlassian.com/ru/git/tutorials/rewriting-history/git-rebase)) для небольших функций или исправлений багов, а трехстороннее слияние — для интеграции функций с более продолжительным временем разработки. В последнем случае точкой соединения двух веток служит коммит слияния.

В первом примере демонстрируется ускоренное слияние. С помощью кода создается новая ветка, после чего в нее добавляется два коммита. Затем она включается в основную ветку посредством ускоренного слияния.

```zsh terminal
# Start a new feature
git checkout -b new-feature main
# Edit some files
git add <file>
git commit -m "Start a feature"
# Edit some files
git add <file>
git commit -m "Finish a feature"
# Merge in the new-feature branch
git checkout main
git merge new-feature
git branch -d new-feature
```

Это распространенная модель работы с ветками, отведенными под решение краткосрочных задач. Чаще они нужны, чтобы создать изолированную среду для разработчика, нежели для продолжительной работы над объемными функциями.

Обратите внимание, что теперь Git сможет без проблем выполнить команду `git branch -d`, поскольку ветка new-feature теперь доступна из главной ветки.

Если при ускоренном слиянии вам понадобится коммит слияния для учета изменений, вы можете выполнить команду git merge с параметром `--no-ff`.

```zsh terminal
git merge --no-ff <branch>
```

Эта команда выполнит объединение указанной ветки с текущей с обязательным созданием коммита слияния (даже если слияние будет ускоренным). Это полезно для учета всех слияний в репозитории.

## Трехстороннее слияние 

---

Следующий пример похож на предыдущий, но в нем слияние должно быть трехсторонним, поскольку работа над веткой `main` ведется одновременно с работой над функцией. Так часто происходит в случае объемных функций или когда над одним проектом одновременно работают несколько разработчиков.

```zsh terminal
Start a new feature
git checkout -b new-feature main
# Edit some files
git add <file>
git commit -m "Start a feature"
# Edit some files
git add <file>
git commit -m "Finish a feature"
# Develop the main branch
git checkout main
# Edit some files
git add <file>
git commit -m "Make some super-stable changes to main"
# Merge in the new-feature branch
git merge new-feature
git branch -d new-feature
```

Обратите внимание, что Git не может выполнить ускоренное слияние, потому что невозможно перенести указатель `main` на ветку `new-feature` без использования предыдущих коммитов.

В большинстве случаев ветка `new-feature` отводится под более объемные функции с продолжительным временем разработки, за которое в ветке `main` появляются новые коммиты. Если бы реальный размер вашей функциональной ветки был так же мал, как в приведенном выше примере, было бы проще перебазировать ее на ветку `main` и выполнить ускоренное слияние. В этом случае не потребовалось бы засорять историю проектов лишними коммитами слияния.


---
Ознакомится конкретнее [тут](https://www.atlassian.com/ru/git/tutorials/using-branches/git-merge).
