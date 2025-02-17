# Руководство пользователя
## Список основных команд Git
* git init
* git status
* git add
* git commit -m “message”
* git log
* git checkout
* git diff

## Краткое описание команд Git
***
Команда Git    | Краткое описание
:-------------:|:----------------
**git init**|*инициализация локального репозитория*
**git status**|*получение информации от git о его текущем состоянии*
**git add**|*добавление файла или файлов к следующему коммиту*
**git commit -m “message”**|создание коммита
**git log**|*вывод на экран истории всех коммитов с их хеш-кодами*
**git checkout**|*переход от одного коммита к другому*
**git checkout master**|*возврат к актуальному состоянию и продолжить работу*
**git diff**|*~~увидеть~~ отображение разницы между текущим файлом и закоммиченным файлом*
***

## Синтаксис работы с изображениями

Синтаксис картинки c `alt` текстом и тайтлом

    ![Alt text](Имя файла "Title")

Пример использования синтаксиса:

![Логотип GB](GB.JPG "Да, это логотип GB")

## Метод игнорирования файлов
Файлы, которых нет нужды хранить в репозитории, вносятся в специально создаваемый файл __.gitignore__ в котором они прописываются.
Затем этот файл добавляется в репозиторий и отслеживается.

## Список и синтаксис команд для работы с ветками
* __git branch__ - позволяет отображать ветки, создавать и удалять их
* __git merge <имя ветки>__- позволяет сливать ветки (по синтаксису вызываем команду из той ветки в которую хотим залить указанную)
* __git log --graph__ - позволяет увидеть историю изменений в виде дерева
* __git checkout <имя ветки>__ - переход с ветки на ветку
## Что такое удаленный репозиторий и список команд для работы с ним

### 1. Что такое удаленный репозиторий
Репозиторий, хранящийся в облаке на стороннем сервисе, специально созданном для работы с git, имеет ряд преимуществ. Во-первых - это своего рода резервная копия вашего проекта, предоставляющая возможность безболезненной работы в команде. А еще в таком репозитории можно пользоваться дополнительными возможностями хостинга. К примеру, визуализацией истории или возможностью разрабатывать вашу программу непосредственно в веб-интерфейсе.

Примеры таких сервисов: GitHub, BitBucket и т.п.
### 2. Подключение к удаленному репозиторию
Чтобы загрузить что-нибудь в удаленный репозиторий, сначала нужно к нему подключиться. Регистрация и установка может занять время, но все подобные сервисы предоставляют хорошую документацию.
Чтобы связать наш локальный репозиторий с репозиторием на GitHub, необходимо выполнить следующую команду в терминале:

    git remote add origin <адрес репозитория>
Проект может иметь несколько удаленных репозиториев одновременно. Чтобы их различать, давайте им разные имена. Обычно главный репозиторий называется origin.
### 3. Список команд для работы с удаленным репозиторием

* __Клонирование__

      git clone <адрес удаленного репозитория>
Клонирование - копирование удаленного репозитория к себе на локальный ПК. Это то, с чего обычно начинается любой проект. При этом вы переносите себе все файлы и папки проекта, а также всю его историю с момента его создания. Чтобы склонировать проект, сперва, необходимо узнать где он расположен и скопировать ссылку на него.
* __Отправка изменений на сервер__

      git push origin master
Для отправки изменений в удаленный репозиторий используется команда предназначенная для этого - push. Она принимает два параметра: имя удаленного репозитория (мы назвали наш origin) и ветку, в которую необходимо внести изменения (master — это ветка по умолчанию для всех репозиториев).

В зависимости от используемыз сервисов вам может потребоваться аутентифицироваться, чтобы изменения отправились. 
* __Запрос изменений с сервера__

      git pull origin master
Если были сделаны изменения в удаленном репозитории, другие пользователи могут скачать изменения при помощи команды pull.