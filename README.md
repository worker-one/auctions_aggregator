## Auctions Aggregator

В рамках данного ТЗ осуществляется разработка сервиса для агрегации и последующей фильтрации предложений с аукционов.

## Спринт 1: Минимальный прототип

В рамках данного спринта выполняется проверка гипотезы о релевантности парсинга сайта "торги-россии.рф" как основного источника данных об аукционах. Для этого реализуются следующие работы.

### Работы

#### Инструмент парсинга сайта

Создается и тестируется инструмент для парсинга данных с сайта "торги-россии.рф". В качестве данных используются объекты из категорий "Жилая недвижимость" и "Коммерческая недвижимость" в районе "г. Москва". В качестве результата инструмент выдает следующую информацию:

```
{
    "id лота": int,
    "заголовок": string,
    "описание": string,
    "текущая цена": string,
    "валюта": string,
    "регион": string
}
```

Если той или иной информации не содержится, то проставляется значение NULL.

#### Обогащение результата с помощью парсинга текстового описания

Создается и тестируется инструмент для извлечения данных из неструктурированного текстового описания объекта аукциона (столбец "Описание лота"). В качестве результата мы ожидаем получить следующую информацию:

```
{
    "город": string,
    "адрес": string,
    "кадастровый номер": string,
    "площадь кв. м": float,
    "номер телефона": string,
    "собственник": string
}
```
Если той или иной информации не содержится, то проставляется значение NULL.

#### Разработка сервиса для тестирования инструментов парсинга

Создается сервис, который объединяет инструменты парсинга сайта и текстового описания. В качестве входных данных сервис принимает ссылку на страницу с лотами и возвращает таблицу с объединенными результатами двух парсеров.

#### Разработка графического веб-интерфейса для тестирования

Разрабатывается веб-интерфейс для взаимодействия с сервисом парсинга.

- **Дизайн**. Интерфейс будет иметь примитивный графический дизайн. Выбор дизайна остается за исполнителем.
- **Функционал**. Интерфейс будет позволять выбрать категорию лота (нежилая или жилая недвижимость), а также количество последних по времени публикации лотов для выдачи. В качестве результата веб-интерфейс будет выдавать ссылку на скачивание Excel-таблицы с результатами работы. Пример таблицы в приложении [1].

### Ресурсы

Для выполнения данных работ необходимы следующие ресурсы:

- Сервер. Для непрерывной работы сервиса необходим сервер. Исполнитель предоставляет свой сервер на момент тестирования, т.е. в рамках данного спринта.
- База данных. Для хранения данных, необходимых для работы сервиса, требуется база данных. Исполнитель предоставляет свою базу данных на момент тестирования.
- Сроки. Для выполнения данных работ необходимо 10-14 дней.
- Стоимость. 20 000 руб.

## Спринт 2: Разработка полноценного пользовательского веб-интерфейса

### Приложения

[1] Пример результата работы сервиса и веб-интерфейса: https://docs.google.com/spreadsheets/d/1cumXvgAfsgWXVrc7ybf8YcjWF57u0bC3/edit?usp=sharing&ouid=116826442056623255845&rtpof=true&sd=true
