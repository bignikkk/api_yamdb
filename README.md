### Проект YaMDb:

Проект YaMDb — это платформа для пользовательских отзывов о произведениях различных категорий, таких как книги, фильмы и музыка. Пользователи могут добавлять отзывы, ставить оценки и оставлять комментарии к произведениям.

### Авторы:
Автор: Timur Nagimov
GitHub: github.com/timur-nagimov

Автор: Nikita Blokhin
GitHub: github.com/bignikkk

### Технологии:

Python
SQLite3
Django REST Framework

### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/bignikkk/api_yamdb
```

```
cd api_yamdb
```

Cоздать и активировать виртуальное окружение:

```
python3 -m venv env
```

```
source env/bin/activate
```

```
python3 -m pip install --upgrade pip
```

Установить зависимости из файла requirements.txt:

```
pip install -r requirements.txt
```

Выполнить миграции:

```
python3 manage.py migrate
```

Запустить проект:

```
python3 manage.py runserver
```
### Пример запроса и ответа:

Открыть сервис для тестирования API - Postman,в строке ввода ввести:

```
GET http://127.0.0.1:8000/api/v1/titles/
```

В поле ответа вернется список произведений на которые можно написать отзыв. Далее в строке ввода надо изменить ссылку на:

```
POST http://127.0.0.1:8000/api/v1/titles/{title_id}/reviews/ , где {title_id} - id произведения на которое вы хотели бы оставить отзыв.
```

Далее под строкой ввода выбрать разделы Body, Row и тип запроса JSON, а после в поле ниже ввести данные и нажать SEND:

```
{
    "text": "Волшебно!"
    "score": 10 (любая оценка от 1 до 10)
}
```

Если все сделано корректно, то в поле ответа должно венуться:

```
{
"id": 1,
"text": "Волшебно!",
"author": "string" (ваш username),
"score": 10,
"pub_date": "2019-08-24T14:15:22Z"
}
```


