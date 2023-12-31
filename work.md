![logo](1color-lightbg@2x.png)
# Работа с Git

## 1. Проверка наличия установленного Git:
В терминале выполнить команду `git -- version`.
Если Git установлен появится сообщение с информацией о версий программы, иначе будет сообщение об ошибке.

## 2. Установка Git:
Загружаем последнюю версию Git с [сайта](https://git-scm.com/downloads).
Устанавливаем с настройками по умолчанию.

## 3. Настройка Git
При первом использовании Git необходимо представиться. 
Для этого нужно ввести в терминале 2 команды:
```
git config --global user. name «Ваше имя английскими буквами»
git config --global user.email ваша почта@example.com
```

## 4. Инициализация репозитория:
Создайте папку для вашего нового репозитория на вашем компьютере.
Откройте командную строку (терминал) и перейдите в созданную папку.
Используйте команду `git init`, чтобы инициализировать новый репозиторий:


## 5. Запись изменений в репозиторий:
Создайте или измените файлы в вашем проекте.
Добавьте файлы в индекс с помощью команды `git add`:
```
git add <имя_файла>
```
или для всех файлов:
```
git add .
```
Зафиксируйте изменения в репозитории с помощью команды `git commit`:
```
git commit -m "Ваше описание коммита"
```


## 6. Просмотр истории коммитов:
Чтобы просмотреть историю коммитов, используйте команду `git log`:
```
git log
```
Вы увидите список всех коммитов в вашем репозитории, включая автора, дату и сообщение коммита.

## 7. Перемещение между сохранениями:
Вы можете перемещаться между коммитами с помощью команды `git checkout` и указанием идентификатора коммита (хэша):
```
git checkout <идентификатор_коммита>
```
Это позволяет вам просматривать состояние проекта на конкретный момент времени. После выполнения `checkout`, вы находитесь в "режиме просмотра" и не можете совершать новые коммиты. Чтобы вернуться к последнему коммиту, используйте `git checkout <ветка>`.

## 8. Игнорирование файлов: 
Для того, чтобы исключить из отслеживания в репозитории определённые файлы или папки необходимо создать там файл ***.gitignore*** и записать в него их названия или шаблоны, соответствующие таким файлам или папкам.

## 9. Создание веток  в Git:
По умолчанию имя основной ветки в Git - **master**.
Создать ветку можно командой:
```
git branch «имя новой ветки>
```
Список веток в  репозитории можно посмотреть с помощью команды `git branch`
Текущая ветка будет отмеченена звёздочкой: **\* master**.

## 10. Слияние веток, разрешение конфликтов.
Шаг 1: Переход к ветке, в которую вы хотите выполнить слияние.
Используйте команду `git checkout`, чтобы переключиться на целевую ветку, в которую вы хотите выполнить слияние:
```
git checkout <целевая_ветка>
```
Шаг 2: Слияние веток
Используйте команду `git merge`, чтобы выполнить слияние другой ветки в текущую:
```
git merge <ветка_для_слияния>
```
Шаг 3: Разрешение конфликтов
Если при слиянии возникли конфликты, Git сообщит об этом. Откройте файлы с конфликтами в текстовом редакторе и разрешите их вручную, удалив метки конфликта и сохраняя нужные изменения.
После разрешения конфликтов сохраните измененные файлы.

Шаг 4: Фиксация слияния
Добавьте изменения к коммиту:
```
git add <измененные_файлы>
```
Зафиксируйте слияние с помощью команды `git commit`:
```
git commit -m "Слияние <ветка_для_слияния> в <целевая_ветка>"
```

## 11. Удаление веток.
Шаг 1: Проверьте текущую ветку
Убедитесь, что вы не находитесь в ветке, которую вы собираетесь удалить. Если вы находитесь в этой ветке, выполните переход к другой ветке с помощью команды `git checkout`.

Шаг 2: Удаление локальной ветки
Используйте команду git branch -d, чтобы удалить локальную ветку:
```
git branch -d <имя_ветки>
```
Если ветка содержит несохраненные изменения, Git не позволит вам её удалить. В этом случае используйте `git branch -D`, чтобы принудительно удалить ветку.

Шаг 3: Удаление удаленной ветки
Если ветка была удалена локально и вы хотите также удалить её на удаленном репозитории, используйте команду `git push` с флагом `--delete`:
```
git push origin --delete <имя_удаляемой_удаленной_ветки>
```

# Работа с удалённым репозиторием

## 1. Создать аккаунт на GitHub:
GitHub - это платформа для хостинга и управления Git-репозиториями. Чтобы начать работу, создайте аккаунт на GitHub:

Перейдите на официальный сайт GitHub по адресу https://github.com/.
Нажмите кнопку "Sign up" (Регистрация), чтобы начать процесс создания аккаунта.
Заполните необходимые поля, включая имя пользователя, адрес электронной почты и пароль.
Следуйте инструкциям для подтверждения адреса электронной почты и завершения создания аккаунта.

## 2. Создать локальный репозиторий:
Локальный репозиторий - это ваш проект, хранящийся на вашем компьютере. Вот как создать локальный репозиторий:

Откройте командную строку (терминал) на вашем компьютере.

Перейдите в каталог, где вы хотите создать новый локальный репозиторий с помощью команды `cd`:
```
cd /путь/к/каталогу
```
Используйте команду `git init`, чтобы инициализировать новый локальный репозиторий:
```
git init
```
## 3. Создать удаленный репозиторий на GitHub:
После создания аккаунта на GitHub, вы можете создать удаленный репозиторий:

Войдите в свой аккаунт на GitHub, если вы ещё не вошли.
Нажмите на плюсик в верхнем правом углу и выберите "New repository" (Новый репозиторий).
Заполните необходимые поля для создания репозитория, включая имя репозитория, описание и другие параметры.
Опционально, вы можете выбрать публичный или частный доступ к репозиторию.
Нажмите кнопку "Create repository" (Создать репозиторий), чтобы завершить создание.

## 4. Связь удаленного репозитория с локальным:
Скопируйте URL удаленного репозитория на GitHub (обычно это URL, оканчивающийся на `.git`).

В локальной командной строке (терминале) перейдите в каталог вашего локального репозитория.

Используйте команду `git remote add`, чтобы добавить удаленный репозиторий с именем "origin" и URL удаленного репозитория:
```
git remote add origin <URL_удаленного_репозитория>
```
Проверьте, что связь создана, выполнив команду:
```
git remote -v
```
## 5. Клонирование удаленного репозитория:
Чтобы начать работу с удаленным репозиторием, вам нужно его склонировать на свой компьютер. Для этого используйте команду `git clone`:
```
git clone <URL_удаленного_репозитория>
```
## 6. Подключение к удаленному репозиторию:
Когда вы уже клонировали репозиторий, он автоматически становится удаленным репозиторием под именем "origin". Вы можете проверить список удаленных репозиториев с помощью команды:
```
git remote -v
```
## 7. Получение обновлений из удаленного репозитория:
Чтобы получить последние изменения из удаленного репозитория, используйте команду `git pull`:
```
git pull origin <ветка>
```
## 8. Отправка изменений в удаленный репозиторий:
Чтобы отправить свои локальные изменения в удаленный репозиторий, выполните следующие действия:

Добавьте изменения в индекс:
```
git add <измененные_файлы>
```
Сделайте коммит:
``` 
git commit -m "Ваше_сообщение_коммита"
```
Отправьте изменения на удаленный репозиторий:
```
git push origin <ветка>
```
## 9. Создание новой ветки на удаленном репозитории:
Если вы хотите создать новую ветку на удаленном репозитории, выполните следующие действия:

Создайте новую локальную ветку:
```
git checkout -b <новая_ветка>
```
Отправьте новую ветку на удаленный репозиторий:
```
git push origin <новая_ветка>
```
## 10. Удаление ветки на удаленном репозитории:
Если вам нужно удалить ветку на удаленном репозитории, используйте команду:
```
git push origin --delete <удаляемая_ветка>
```
## 11. Работа с несколькими удаленными репозиториями:
Если у вас есть несколько удаленных репозиториев (не только "origin"), вы можете добавить их с помощью команды `git remote add`:
```
git remote add <имя_репозитория> <URL_репозитория>
```