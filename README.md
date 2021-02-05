# Скрипт для отдела продаж

## Установка

1. git clone репозиторий

2. Установить зависимости
````
composer install
````

3. Переименовать .env.example в .env и в файле окружения (.env) указать название базы данных, user_name и пароль

4. Сгенерировать ключ приложения
````
php artisan key:generate
````

5. Migrate
````
php artisan migrate --seed
````

6. Install Node modules
````
npm install
````
***
## Запуск

- ```npm run watch``` или ```npm run dev```
- ```php artisan serve```
***

## Как пользоваться

### Начальная страница (Home, /) имеет 2 компонента:
* создание скрипта - здесь можно создать новый пустой скрипт
* список скриптов с ссылками на редактирование, запуск и список переменных

### Страница редактирования скрипта:
#### Создание элементов
Для создания вопроса кликните 2 раза левой кнопкой мыши - появится форма создания вопроса.

**Важно!** У скрипта должен быть один первый вопрос - ни больше ни меньше. Для этого в форме есть checkbox "Первый вопрос"
Больше одного создать нельзя, если их будет ноль - в запуске скрипта ничего не заработает (будет alert с предупреждением что нет первого вопроса).

Для создания ответа нужно у уже созданного вопроса нажать на +(плюс), удерживать мышь и тянуть к месту где хочется чтобы появился вариант ответа.
После того, как кнопка мыши будет отпущена появится окно с формой создания ответа.

Для того, чтобы указать следующий после ответа вопрос нужно воспользоваться кнопкой плюс у ответа и тянуть к нужному вопросу. Отпустить когда он (вопрос) покраситься в красный цвет и появится alert с вопросом: "Привязать к этому элементу?"

#### Редактировние элементов
Кнопка в правом верхнем углу - по нажатию появится форма с редактированием.

#### Переменные в редактировании и создании вопроса
Переменные создаются по ссылке в списке скриптов. Переменные добавляются в конец текстового редактора кликом в списке переменных выше.

#### Удаление элементов
Кнопка в левом верхнем углу. 

**Важно!** При удалении вопроса - удаляются все связанные с ним ответы.

### Страница запуска скрипта:
При начальной загрузке в диалоге появляется первый вопрос и возможные варианты ответов в select ниже. При выборе ответа отображается он и следующий по скрипту вопрос. Есть кнопка назад.
