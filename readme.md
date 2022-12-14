
# Инструкция по работе с Git и с GitHub

Git - одна из реализаций распределенных систем контроля версий, позволяющая реализовать версионность, как локально, так и на удаленном сервере. Самая популярная платформа, реализующая Git, - [GitHub](https://github.com)

## Подготовка репозитория

Для создания в папке репозитория необходимо открыть эту папку в терминале и написать команду *git init*, после чего в этой папке создастся скрытая папка *.git*, и таким образом папка станер репозиторием

### Просмотр состояния репозитория

Для просмотра состояния репозитория используетс команда *git status*. В терминале с открытой папкой-репозиторием, необходимо написать команду *git status* в результате можно увидеть следующие выводы:
1. On branch *** nothing to comit - это означает нет активных изменений 
2. Untracked file - это означает, что имеются файлы, не отслеживаемые системой контроля версий

## Создание комитов

### Создание коммитов
Для создания фиксации используется команда *git commit*. Для этого в терминале с папкой-репозиторием необходимо написать команду *git commit -m <сообщение к комиту>*. Сообщение к комиту писать **ОБЯЗАТЕЛЬНО**.

### Перемещение между комитами

Для перемещениями между комитами используется команда *git checkout*. Для этого в терминале с папкой-репозиторием необходимо написать *git checkout <номер коммита>*. Номер коммита берется из журнала изменений ветки.

### Добавление файла к коммиту

Для того, чтобы добавить файл к сохранению, необходимо использовать команду *git add*. В терминале с открытой папкой-репозиторием необходимо написать *git add <название файла>*, и этот файл добавится в сохранение.

## Журнал изменений

Для просмотра истории изменений используется команда *git log*. Для этого в терминале с папкой-репозиторием необходимо написать *git log* и вы увидите список всех коммитов в этой ветке с описанием: имени, электронной почты, сообщение к коммиту и номер коммита.

## Ветки в Git

### Создание ветки

Для того, чтобы создать новую ветку используется команда *git branch*. Для этого в терминале с папкой-репозиторием необходимо написать *git branch <название ветки>. И таким образом создастся новая ветка, но вы останетесь в исходной.

### Просмотр списка веток

Для того чтобы простотреть список веток в локальном репозитории используется команда *git branch*. Для этого в терминале с папкой-репозиторием напишите команду *git branch* и тогда вы увидите список всех ваших локальных веток. Зеленым цветом и * будет выделена ветка, на которой вы сейчас стоите.

Флаг *-а* позволяет посмотреть все ветки, в том числе и в удаленном репозитории.

### Переключение между ветками
Для того, чтобы переключиться на другую ветку, используется команда *git checkout*. Для этого в терминале с папкой-репозиторием необходимо написать *git checkoit <название ветки>*. И тогда вы перейдете в указанную ветку. Для переключения между ветками, ветка должна существовать и в текущей ветке **НЕ ДОЛЖНО** быть активных изменений.

### Слияние веток и решение конфликтов

Работа над проектами часто ведется в несколько этапов, им могут соответствовать ветки. Отдельные ветки могут создаваться для срочного исправления багов, быстрого добавления временных функций, для делегирования части работы другому отделу и т.д.
Для объединения (слияния) веток используется команда *merge*.
Для слияния веток необходимо сначала перейти в ветку в которую нужно слить другую ветку, а далее в терминале с папкой-репозиторием написать *git merge <Название ветки>*.

Если при слиянии веток возникнут конфликты Git пометит общие части файлов из разных веток и сообщит о конфликтах.
Для разрешения конфликтов есть консольная утилита *git mergetool*
Однако если файл проекта объемный, а общих частей много, пользоваться ей не удобно. Общая рекомендация для таких случаев - пользоваться сторонними инструментами, как и в случае с текстовым редактором лоя Git.

Когда спорные участки всех файлов приведены к итоговому состоянию, нужно повторить стандартную процедуру и создать коммит.

## Удаление веток

Бывают ситуации, когда после слива каких то изменений из рабочей ветки в исходную версию проекти, ее, по правилам хорошего тоа, необходимо удалить, чтобы она более не мешалась в вашем коде.
Для этого необходимо перейти в основную ветку и в терминале с папкой-репозиторием прописать команду *git branch -d <Название ветки>*.
