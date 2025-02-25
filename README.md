# Лабораторной работа IWNO3: Первый контейнер

## Цель работы.

Данная лабораторная работа знакомит с основами контейнеризации и подготавливает рабочее место для выполнения следующих лабораторных работ.

## Задание.

Установить Docker Desktop и проверить его работоспособность.

## Описание выполнения работы с ответами на вопросы.

### Подготовка

Скачал и установил Docker Desktop.

<img src="/images/Screenshot_8.png" style="WIDTH: 30vw">

<!-- ![](images/Screenshot_8.png) -->

### Выполнение

Открыл Visual Studio Code, открыл терминал, зашел в папку cv-labs.
Создал репозиторий containers02 и клонировал его себе на компьютер.

```
git clone https://github.com/falcon-ov/containers02
```

![](images/Screenshot_10.png)

![](images/Screenshot_1.png)

Создал в папке containers02 файл Dockerfile со следующим содержимым:

![](images/Screenshot_2.png)

В той же папке проекта создал папку site. В новой папке создал файл index.html с произвольным содержимым.

### Запуск и тестирование

В терминал в папке containers02 и выполнил команду:

```sh
docker build -t containers02 .
```
Образ создавался `11.8` секунд.

![](images/Screenshot_4.png)

Выполнил команду для запуска контейнера:

```sh
docker run --name containers02 containers02
```

![](images/Screenshot_5.png)

Вывелось `hello from 21000cae1c71`, то есть выполнился скрипт `sh -c "echo hello from $HOSTNAME"` из `Dockerfile`, где `$HOSTNAME` — `21000cae1c71` уникальный идентификатор (хэш) моего контейнера, который Docker присвоил при запуске.

Удаляю контейнер и запускаю снова, выполнив команды:

![](images/Screenshot_6.png)

Далее выполяю следующие команды, перешел по пути и посмотрел наличие файлов с подробностями:

![](images/Screenshot_9.png)

- `total 4`: общий размер содержимого в килобайтах (4 КБ).
- `-rwxr-xr-x`: права доступа к файлу. Это значит:
- `-`: это файл (не директория).
- `rwxr-xr-x`: владелец (root) имеет права на чтение, запись и выполнение (rwx), группа и остальные пользователи — только чтение и выполнение (r-x).
- `1`: количество ссылок на файл.
- `root root`: владелец файла и группа — оба root (ты работаешь в контейнере как root-пользователь).
- `215`: размер файла в байтах (215 байт).
- `Feb 25 18:15`: дата и время создания или модификации файла (25 февраля, 18:15).
- `index.html`: имя файла, который ты скопировал из локальной папки site.

Использую команду `exit`.

![](images/Screenshot_11.png)

## Выводы.

В ходе работы я освоил установку Docker Desktop, научился создавать и запускать контейнеры на основе Dockerfile, а также проверил их работоспособность. Задание помогло подготовить среду для дальнейшей работы с контейнерами.

# Используемые источники.

[github.com/mcroitor/app_containerization_ru](https://github.com/mcroitor/app_containerization_ru)
[grok.com](https://grok.com/)
