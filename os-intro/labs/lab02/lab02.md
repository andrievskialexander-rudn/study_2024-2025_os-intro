---

title: "Отчёт по лабораторной работе №2"
subtitle: "Первоначальная настройка git"
author: "Андриевский Александр"

lang: ru-RU
toc-title: "Содержание"
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
mainfont: IBM Plex Serif
monofont: IBM Plex Mono
header-includes:

* \usepackage{indentfirst}
* \usepackage{float}
* \floatplacement{figure}{H}

---

# Цель работы

Изучить идеологию и применение средств контроля версий. Освоить умения по работе с git: установка, настройка, генерация SSH и PGP ключей, создание репозитория на GitHub.

# Теоретическая часть

## Что такое системы контроля версий?

Системы контроля версий (VCS) позволяют отслеживать и управлять изменениями в файлах проекта. Они используются при работе нескольких человек над одним проектом для хранения истории изменений, совместной работы, отката и разрешения конфликтов.

Централизованные VCS (например, SVN) используют единый сервер. Распределённые VCS (например, Git) позволяют каждому пользователю иметь локальную копию всего репозитория.

## Git и его возможности

Git — это распределённая система контроля версий. Она обеспечивает:

* создание репозиториев (`git init`)
* фиксацию изменений (`git add`, `git commit`)
* создание веток (`git branch`, `git checkout`)
* отправку изменений на удалённый сервер (`git push`, `git pull`)

## Работа с репозиторием GitHub

Для взаимодействия с GitHub необходимы:

* SSH-ключ для авторизации
* PGP-ключ для подписи коммитов (опционально)

# Практическая часть

## Установка необходимого ПО

```bash
sudo dnf install git gh
```

## Базовая настройка Git

```bash
git config --global user.name "Андриевский Александр"
git config --global user.email "example@mail.com"
git config --global core.quotepath false
git config --global init.defaultBranch master
git config --global core.autocrlf input
git config --global core.safecrlf warn
```

## Генерация SSH ключей

```bash
ssh-keygen -t ed25519
```

Ключ сохраняется в `~/.ssh/id_ed25519`.

## Генерация PGP ключа и экспорт

```bash
gpg --full-generate-key
gpg --list-secret-keys --keyid-format LONG
gpg --armor --export <PGP-Fingerprint> | xclip -sel clip
```

## Добавление ключей на GitHub

* SSH-ключ добавляется в разделе SSH and GPG keys → New SSH key
* PGP-ключ добавляется в том же разделе → New GPG key

## Настройка автоматической подписи коммитов

```bash
git config --global user.signingkey <PGP-Fingerprint>
git config --global commit.gpgsign true
git config --global gpg.program $(which gpg)
```

## Авторизация в gh (GitHub CLI)

```bash
gh auth login
```

## Создание рабочего пространства

```bash
mkdir -p ~/work/study/2024-2025/"Операционные системы"
cd ~/work/study/2024-2025/"Операционные системы"
gh repo create study_2024-2025_os-intro --template=yamadharma/course-directory-student-template --public
git clone --recursive git@github.com:<username>/study_2024-2025_os-intro.git os-intro
```

## Настройка каталога курса

```bash
cd os-intro
rm package.json
echo os-intro > COURSE
make
git add .
git commit -am "feat(main): make course structure"
git push
```

# Выводы

Была выполнена первоначальная настройка Git, сгенерированы ключи SSH и PGP, связана учётная запись GitHub, выполнен вход через GitHub CLI, создан репозиторий и инициализировано рабочее пространство по шаблону.

# Контрольные вопросы

1. **Что такое VCS?** — это система для отслеживания изменений в коде.
2. **Основные термины:** commit — фиксация изменений; рабочая копия — файлы в локальной директории; история — все коммиты проекта.
3. **Централизованные vs распределённые:** SVN — централизованная; Git — распределённая.
4. **Работа в одиночку:** git init, git add, git commit, git log.
5. **Совместная работа:** git pull, git push, ветки, разрешение конфликтов.
6. **Основные команды:** git init, status, add, commit, push, pull, branch, checkout, merge.
7. **Примеры:** создание локального репозитория, клонирование с GitHub, работа с ветками.
8. **Ветвление:** позволяет работать над разными функциями независимо.
9. **.gitignore:** позволяет исключать из коммитов временные и ненужные файлы.

# Приложения

!\[Настройка Git и генерация ключей]\(screenshots/Снимок экрана от 2025-06-20 02-32-20.png){#fig:001 width=70%}

!\[Настройка подписи коммитов]\(screenshots/Снимок экрана от 2025-06-20 02-32-46.png){#fig:002 width=70%}

!\[Создание каталога и make]\(screenshots/Снимок экрана от 2025-06-20 02-32-55.png){#fig:003 width=70%}
