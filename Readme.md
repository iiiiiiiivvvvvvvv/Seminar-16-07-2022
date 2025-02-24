# Инструкция по работе с git и удалёнными репозиториями

## Что такое git?
*Git* одна из реализаций распредённых систем контроля версий. *Git* на данный момент является самой полулярной реализацией. Самой популярной реализацией *Git* является [GitHub](https://github.com) Также служит для отслеживания и ведения истории изменения файлов, в вашем проекте. Чаще всего его используют для кода, но можно и для других файлов. Например, для картинок - полезно для дизайнеров.
 С помощью Git-a вы можете откатить свой проект до более старой версии, сравнивать, анализировать или сливать свои изменения в репозиторий.


## Подготовка репозитория
Подготовить локальный репозиторий можно двумя способами: создать репозиторий с нуля с последующим
переносом изменений в удаленный репозиторий и сделать клон удаленного репозитория.
Первый способ создание локального репозитория с нуля командойgit iit.
Второй способ. Сделать на локальной машине клон удалённого репозитория командойgit clone.

## Состояние репозитория
Для того, чтобы посмотреть состояние репозитория, используется команда *git status* Для этого в терминале с папкой-репозиторием необходмо написать *git status*, и возможно увидеть несколько состояний:
1. Nothing to commit - репозиторий не содержит изменений
2. Unversioned file - папка содержит файл, к которому не добавлена версионность

# Просмотр сделанных изменений
Для того, чторбы просмотреть разницу между текущей версией файла, и версией файла в полследнем коммите, используется команда *git diff*. Для этого в терминале с папкой с репозиторием, напишите *git diff*

## Создание коммитов
Команда git commit делает для проекта снимок текущего состояния изменений, добавленных в раздел проиндексированных файлов. Такие подтвержденные снимки состояния можно рассматривать как «безопасные» версии проекта — Git не будет их менять, пока вы явным образом не попросите об этом. Перед выполнением команды git commit необходимо использовать команду git add, чтобы добавить в проект («проиндексировать») изменения, которые будут сохранены в коммите. Эти две команды, git commit и git add, используются чаще всего.
Для создание нового "сохранения" испольузется команда *git commit*. Используется она следующим образом: в терминале с папкой-репозиторием пишется *git commit -m <сообщение к коммиту>*. Сообщение к коммиту писать **ОБЯЗАТЕЛЬНО**!!!

### Добавление файла к коммиту
Команда git add — это первая команда в цепочке операций, предписывающей Git «сохранить» снимок текущего состояния проекта в истории коммитов. Когда git add используется как отдельная команда, она переносит ожидающие изменения из рабочего каталога в раздел проиндексированных файлов.
 Для добавления файла к коммиту используется команда *git add*. Пишется она следующим образом *git add <имя файла>* в терминале в папке с созданным репозиторием.

## Журнал изменений
Для просмотра журнала измений используется команда *git log*. Для этого в терминале в папке с репозиторием достаточно написать *git log*.
 По умолчанию, она показывает лишь историю текущей ветки, но может быть настроена на вывод истории других, даже нескольких сразу, веток.

## Перемещение между "сохранениями"
Для перемещения между сохранениями используется команда *git checkout*. Для того, чтобы перемиститься на указанный коммит в терминале в папке с репозиторием пишем *git checkout <номер коммита>*. **Номер коммита** берется из журнала изменений, о котором сказано выше. После перемещния на указанный коммит мы попадаем в состояние **detached head*. Чтобы вернуться к обычной работе, необходимо написать *git checkout master*.

## Ветки в git
Ветки в *git* нужны, чтобы работать с "чистовиком" и "черновиками". Для того, чтобы создать новую ветку используется команда *git branch*. В терминале в папке с репозиторием, напишите *git branch <название ветки>*.

## Слияние веток и разрешение конфликтов
Для слияния двух веток используется команда *git merge*. Для её использования необходимо перейти в ту веку, куда Вы хотите сделать слияние, после чего в терминале в папке с репозиторием написать *git merge <название сливаемой ветки>*. Чаще всего слияние проиходит автоматически, но возможны **КОНФЛИКТЫ**. В таком случае, необходимо вручную получить желаемую версию файла и сделать коммит.

## Удаление веток
Для удаления ветки используется команда *git branch -d*. Для этого необходимо в папке с репозиторием в терминале написать *git branch -d <название ветки>*. Удаляемая ветка **ОБЯЗАТЕЛЬНО** должна быть **СЛИТА**

## Получение удалённого репозитория
Для того, чтобы скачать удалённый репозиторий необходимо использовать команду *git clone*. В терминале, в котором открыта любая пустая папка, необходимо написать *git clone <ссылка на репозиторий>*. Репозиторий скачатеся в папку, название которой будет совпадать с названием репозитория.

## Скачивание изменений с удалённого репозитория
Для того, чтобы скачать изменения с удалённого репозитория, необходимо использовать команду *git pull*. В терминале с  папкой с репозиторием, связанным с удалённым репозиторием, пишем *git pull origin <название ветки>* для того, чтобы принять изменения из указанной ветки удалённго репозитория в текущую ветку.

## Отправка изменений Github
Для отправки изменений в удалённый репозиторий необходимо использовать команду *git push*. Для этого в терминале с папкой с репозиторием, связанным с удалённым репозиторием, пишем команду *git push origin <название ветки>*, <название ветки> - это ветка в удалённом репозитори, куда необходимо отправить совершённые изменения

## Создание форка репозитория на GitHub. Пулл-реквест.

Форк (от англ. fork – вилка) – точная копия репозитория, но в вашем аккаунте. Форки нужны, чтобы вносить свои изменения в проект, к репозиторию которого у вас нет прямого доступа.
1. Для начала зайдем на страницу репозитория проекта. Нажимаем на кнопку Fork, как показано на картинке. После этого Git создаст точную копию этого репозитория в вашем аккаунте.
2. Клонируем репозиторий к себе на компьютер командой git clone. Создадим файл README.md с описанием проекта, чтобы другим пользователям было понятно, в чем отличие этой реализации от остальных.
3. Сделаем коммит и выполним git push, чтобы загрузить наши изменения в удаленный репозиторий.
4. Теперь GitHub подсказывает нам, что наша ветка опережает ветку исходного репозитория на один коммит и предлагает сделать пулл-реквест.
5. Нажимаем на кнопку Compare на подсказке GitHub, либо переходим на вкладку Pull Requests и нажимаем New pull request.
6. Перед нами откроется страница создания пулл-реквеста.Здесь мы можем просмотреть внесенные изменения и выбрать две ветки: одну в исходном репозитории, на нее будут залиты наши изменения, вторую – в нашем репозитории, с нее будут скачаны изменения. Как только мы выбрали ветки и убедились, что не внесли никаких лишних изменений, нажимаем кнопку Create pull request.
7. Теперь мы попадаем на страницу описания наших изменений.Здесь необходимо описать, что за изменения вы внесли и почему они были необходимы. Сообщение, которое оставили мы, видно на картинке. Оно отражает суть и необходимость внесенных изменений. Как только мы закончили с описанием, можно нажимать кнопку Create pull request.
8. Теперь мы попадаем на страницу уже созданного пулл-реквеста в изначальном репозитоии.
