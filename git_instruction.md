# Работа с **Git**
## 1. Проверка наличия установленного *Git*

- В терминале выполнить команду: `git version`
- Если **Git** установлен, появится сообщение с информацией о версии программыю Инача будет сообщение об ошибке

## 2. Установка **Git**

- Загружаем последнюю версию **Git** с сайта [git-scm.com](https://git-scm.com/downloads).

![pic_download](download.png)

- Устанавливаем с настройками по умолчанию

## 3. Настройка **Git**

При первом использовании **Git** необходимо представиться. Для этого нужно ввести в терминале 2 команды:
```
git config --global user.name "Ваше имя"
git config --global user.email ваша "почта@example.com"
```
## 4. Инициализация репозитория

- В терминале переходим к папке, в которой хотим создать репозиторий
- Выполняем команду `git init` 
- В исоходной папке появится скрытая папка *.git*

## 5. Фиксация текущего изменения в репозитории
- В начале работы с новым файлом его необходимо добавить в отслеживание **Git** -ом. Для этого используется команда `git add <имя файла>`
- Сохраняем текущий файл (`Ctrl + s`)
- Добавляем этот файл в текущую фиксацию (*коммит*) `git add <имя файла>`. Данное действие нужно выполнять каждый раз перед фиксацией коммита
- Сохраняем добавленный файл в текущем коммите, выполнив команду `git commit -m ""`, где ключ -m добавляет комментарий (в кавычках) сохраненного состояния

## 6. Проверка текущего состояния репозитория

- Для проверки состояния в любой можно набрать команду `git status`
- Команда `git diff` покажет разницу между текущим состоянием и последним коммитом

## 7. Просмотр истории коммитов

- Командой `git log` можно вызвать хронологию коммитов
    > Ключ --oneline позволит сократить запись коммита до одной строки
    >
    > Ключ --graph отобразить историю в графическом виде

## 8. Перемещение между сохранениями

- Сделать текущим любой коммит можно командой `git Checkout <name>` где <name> -- хэшкод нужного коммита
    > - Хэшкод нужного коммита можно скопировать из истории
    > - Для перехода достаточно ввести первые 4 символа хэшкода
- После совершенного перемещения нужно вернуться в актуальное состояние командой `git checkout master`

## 9. Игнорирование файлов
Для того, чтобы исключить из отслеживания в репозитории определенные файлы или папки необходимо создать там файл ***.gitignore*** и записать в него их названия или шаблоны, соответствующие таким файлам или папкам.

## 10. Создание веток в **Git**
Ветка в **Git** - это простой перемещаемый казатель на один из коммитов, обычно последний в цепочке коммитов. По умолчания имя основной ветки в **Git** - master.
Создать ветку можно командой:
```
git branch <имя новой ветки>
```
В результате создается новый указатель на текущий коммит. Список веток в репозитории можно посмотреть с помощью команды `git branch`.

Для переключения между ветками используется команда `git checkout <имя ветки>`
Чтобы при создании ветки сразу на нее переключиться можно использовать команды:
```
git checkout -b <имя новой ветки>
```
или
```
git switch -c <имя новой ветки>
```
## 11. Слияние веток и разрешение конфликтов
Для слияния выбранной ветки с текущей нужно выполнить команду:
```
git merge <название выбранной ветки>
```
Если была изменена одна и та же часть файла в обеих ветках то может возникнуть конфликт, который потребует участия пользователя. **Git** предлагает варианты разрешения.

Чтобы разрешить конфликт, нужно выбрать один из вариантов, либо объединить содержимое по-своему.

## 12. Удаление веток
После выполнения слияния нунужную ветку можно удалить командой:
```
git branch -d <название ветки>
```
