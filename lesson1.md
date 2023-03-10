# Инструкция для работы с Git и удалёнными репозиториями

### Что такое Git?
Git - это одна из реализаций распределённых систем контроля версий, имеющая как и локальные, так и удалённые репозитории. Является самой популярной реализацией систем контроля версий в мире.
## Подготовка репозитория
Для создание репозитория необходимо выполнить команду *git init*  в папке с репозиторием и у вас создаться репозиторий (появится скрытая папка .git)
### Пример команды (находясь в нужной папке!):
*git init*
### Ответ терминала, если все ок:
*Initialized empty Git repository in C:/Users/UserName/Desktop/"Имя нужной папки"/.git/*


### Фото пример ответа системы в терминале, если git уже был добавлен в эту папку ранее (то есть если репозиторий уже создан):

![<Reinitialized existing Git repository in C:/Users/Evgeniy/Desktop/new_lesson/.git/>](<1.jpg>)

## Создание коммитов

### Git add
Для добавления измений в коммит используется команда *git add*. Чтобы использовать команду *git add* напишите:
* Для конкретного файла:
  * *git add <имя файла>* 
* Для всех файлов в папке:
  * *git add .*
  * *git add --all*

### Просмотр состояния репозитория
Для того, чтобы посмотреть состояние репозитория используется команда *git status*. Для этого необходимо в папке с репозиторием написать *git status*, и Вы увидите были ли измения в файлах, или их не было.

### Создание коммитов
Для того, чтобы создать коммит(сохранение) необходимо выполнить команду *git commit*. 

Выполняется она так: 

*git commit -m "<сообщение к коммиту>*. 

Все файлы для коммита должны быть ***ДОБАВЛЕНЫ*** и сообщение к коммиту писать ***ОБЯЗАТЕЛЬНО***.  Сообщение должно содержать суть внесенных изменений. 

>>>Перед каждым коммитом надо делать git add???
Ответ из практики: да, перед каждым коммитом надо делать адд. 

## Журнал изменений
Для того, чтобы посмтреть все сделанные изменения в репозитории, используется команда *git log*. Для этого достаточно выполнить команду *git log* в папке с репозиторием. Логов может быть много, в этом случае в терминале финальным симвовлом после команды будет двоеточие, чтобы листать журнал логов, необходимо нажимать enter или стрелку вниз (ы конце журнала будет слово END). Чтобы выйти из журнала, необходимол нажать Q.

## Перемещение между сохранениями
Для того, чтобы перемещаться между коммитами, используется команда: 

* *git checkout*

Используется она в папке с репозиторием следующим образом:
 
* *git checkout <номер коммита>*

Номер коммита берется из журанала логов, достаточно первых 4-6 символов номера.

Чтобы вернуться обратно в актуальную версию и продолжить работу, необходимо ввести:

* *git checkout master*

## Отмена коммитов

Более подробно по этому вопросу по
[ссылке](https://www.atlassian.com/ru/git/tutorials/undoing-changes)


## Ветки в Git


### Создание ветки

Для того, чтобы создать ветку, используется команда:
* *git branch* 

Делается это следующим образом в папке с репозиторием: 
* *git branch < new brance name >*

Для создания ветки и одновременного переключения в нее:
* *git checkout -b < new brance name >*


## Слияние веток

Для того чтобы слить ветки (перенести изменния из одной ветки в другую) используется команда:
* *git merge < name branch >*

### ***Важно!!! слияние происходит из той ветки, в которую переносим информацию!***

## Конфликты при слиянии веток

Если при мердже в одной и той же строке указана разная информация, то будет предложено решение конфликты вручную. Варианты: 
* принять информацию текущей ветки
* принять информацию входящей ветки
* оставить оба варианта

## Удаление веток

Для удаления ветки ввести команду:
* *git branch -d < name branch >*

Если в ветке присутствуют изменения, которые не были смерджены, гит выдаст ошибку. Удалить такую ветку без мерджа, можно командой:
* *git branch -D < name branch >*


## Клонирование существующего репозитория ## 

Для для создания копии (клонирования) удаленного репозитория необходимо ввести командуq :
* *git clone < repo url >*


## Совместная работа с разными репозиториями ##

Чтобы отправить все изменения в удаленный репозиторий необходимо воспользоваться командой: 
* *git push*

Если мы отправляем новую ветку в удаленный репозиторий, то команда будет :
* *git push --set-upstream origin lists*

Для извлечения и загрузки содержимого из удаленного репозитория использется команда: 
* *git pull*


