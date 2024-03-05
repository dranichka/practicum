# Базовые команды для работы с Git

## Навигация

pwd — покажи, в какой я папке

ls — покажи файлы и папки в текущей папке

cd (название папки) — перейди в папку

## Работа с файлами и папками

touch (название файла) — создай файл в текущей папке

mkdir (название папки) — создай папку в текущей папке

### Копирование и перемещение

cp (название файла) ~/(название папки) — скопируй файл в папку

mv (название файла) ~/(название папки) — перемести файл в папку

### Чтение

cat (название файла) — распечатай содержимое текстового файла

### Удаление

rm (название файла) — удали файл 

rmdir (название папки) — удали папку

rm -r (название папки) — удали папку и всё, что она содержит

# Навигация по коммитам. Статусы файлов

## Хеш — идентификатор коммита

Хеширование (от англ. *hash*, «рубить», «крошить», «мешанина») — это способ преобразовать набор данных и получить их «отпечаток» (англ. *fingerprint*).

При работе с Git хеши будут встречаться вам регулярно. Их можно будет передавать в качестве параметра разным Git-командам, чтобы указать, с каким коммитом нужно произвести то или иное действие.

## HEAD — всему голова

Файл HEAD (англ. «голова», «головной») — один из служебных файлов папки .git. Он указывает на коммит, который сделан последним (то есть на самый новый).

## Статусы файлов в Git

Статусы бывают:

1. untracked (англ. «неотслеживаемый»)
2. staged (англ. «подготовленный»)
3. tracked (англ. «отслеживаемый»)
4. modified (англ. «изменённый»)

Файл может находиться в разных статусах (состояниях) одновременно. Ниже представлена схема типичного жизненного цикла файла в Git.

### Типичный жизненный цикл файла в Git

```mermaid
graph LR;
untracked -- "git add" --> staged;
staged -- "git commit" -- > tracked;
```

## Как читать git status

Команда git status показывает только следующие состояния файлов:

* staged (Changes to be committed в выводе git status);
* modified (Changes not staged for commit);
* untracked (Untracked files).

# Стили оформления сообщений к коммитам

Базовые правила при оформлении сообщений к коммитам:

* сообщения должны легко читаться;
* сообщения должны быть информативными;
* сообщения должны быть оформлены в одном стиле.

## Корпоративный

Подходит для компания, использующих Jira. В корпоративном стиле в начале сообщения обычно указывается Jira-ID, а затем текст сообщения.

Пример использования:

```bash
$ git commit -m 'TEACHSIT-25523: Заниматься 2 часа'
```

## Conventional Commits

Сообщения в этом стиле составляются по формату: *type: сообщение*

Есть целый перечень типов изменений. Его можно найти [здесь](https://www.conventionalcommits.org/ru/v1.0.0-beta.4/#%D1%81%D0%BF%D0%B5%D1%86%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D1%8F).

Пример использования:

```bash
$ git commit -m 'fix: Исправить ошибку при планировании дня'
```

## GitHub-стиль

Используется в случае, когда полезно синхронизировать проект со списком задач этого проекта. Когда коммит «решает» какую-то задачу из списка, в сообщении удобно оставлять на нее ссылку.

Пример использования:

```bash
$ git commit -m 'Дополнить #354: Поработать еще 1 час'
```

Этой командой GitHub свяжет коммит с задачей.





