# Процесс тестирования нового функционала
Решение задания лежит в файле test_strategy.docx

# Автоматизация тестирования API. Часть 1
Решение задания лежит в папке tests

## Проблемы в API
Так как эндпоинты отвечают некорректно по стандартам индустрии, 
некоторые тесты были помечены `@pytest.mark.xfail`, пока проблемы не будут исправлены.

### За истину брались следующие стандарты:
#### 200 - код ответа, если запрос отработал успешно
#### 400 - код ответа, если запрос отработал с ошибкой Bad request. Передан невалидный параметр
#### 404 - код ответа, если запрос отработал с ошибкой Not found. Передан валидный параметр, но не существует в бд

##### Не пройденные тесты, так как требуется поправить функциональность:

###### tests/test_delete_negative.py
- удаление несуществующего поста по валидному id
- удаление поста по невалидному id
- удаления постов по существующим значениям параметров id, userId, title, body
- удаление поста без id

###### tests/test_get_negative.py
- получение поста по всем несуществующим валидным параметрам
- получение поста по всем невалидным параметрам
- получение постов по одному неcуществующему валидному параметру userId, id, title, body
- получение постов по одному невалидному параметру userId, id, title, body
- получение поста по существующему id и не существующему usedId
- получение поста по не существующему id и существующему usedId

###### tests/test_post_negative.py
- создание поста без заданных параметров
- создание поста с пустым значением параметра userId, title, body
- создание поста с пустым значением параметра userId, title, body
- создание поста с пробелом в значении параметра userId, title, body
- создание поста с недопустимым типом данных в значении параметра userId, title, body
- создание поста с HTML-скриптом в значении параметра userId, title, body
- создание поста с SQL-инъекцией в значении параметра userId, title, body

###### tests/test_post_positive.py 
- создание поста со всеми валидными несуществующими параметрами
- создание поста по одному несуществующему валидному параметру userId, title, body

## Запуск тестов
### Склонировать проект
`git clone https://github.com/MaksimTsybikov/QaCloudCamp.git`

### Перейти в проект
`cd QaCloudCamp`

#### Создать виртуальную среду

Windows `python -m venv env`
MacOS/Linux `python3 -m venv env`

#### Активировать виртуальную среду

Windows `env\Scripts\activate`
MacOS/Linux `source env/bin/activate`

### Установить зависимости

Windows  `pip install -r requirements.txt`
MacOS/Linux `pip3 install -r requirements.txt`

### Команды запуска Тестов

#### Запуск всех тестов
`pytest`

#### Запуск одного теста
`pytest tests/test_get_positive.py`

# Автоматизация тестирования API. Часть 2
Решение задания лежит в файле Dockerfile

## Запустить приложение docker desktop

## Сборка образа
`docker build -t qacloudcamp .`

## Запустить контейнер
`docker run qacloudcamp`

# Информация для связи

## Максим Цыбиков
### Номер телефона: `+79096669965`
### Почта: `tsybikov.maksim05@mail.ru`
### Телеграм: `@guccicrowd`
