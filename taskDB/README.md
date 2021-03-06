## Задача БД

### Условия

Автобусный рейс имеет название, количество мест, дату начала движения, дату окончания движения (сезон, т.е. в датах в этом интервале он ходит, для простоты каждый день), список городов, через которые проходит, для каждого города есть расписание, т.е. номер дня пути и время прибытия в город, время выезда из города.

Необходимо сделать:
1. Схему БД - хранение описаний рейсов/маршрутов. (Используя именования и правила проекта, в отдельной базе)
2. Написать запрос, получающий список всех рейсов с городом отправления, городом прибытия и общим временем в пути.
3. Написать запрос, который по заданной дате, городу отправления и городу прибытия выведет список возможных рейсов, количество остановок и общее время между этими городами.
4. Написать запрос, которые по заданной дате, городу отправления и городу прибытия выведет нумерованный список промежуточных городов: № остановки, город, время прибытия, время отбытия (включая конечную и начальную точки).


### Автобусный парк

- Программа работает на порту 8000 (localhost:8000) чтобы визуально посмотреть результаты поиска
- В программе есть заранее созданные затем заполненные псевдо данными таблицы
- Есть 8 таблиц, но в данном этапе применяются 3 таблицы в которые записаны некоторые данные (таблицы: bus_flights, intermediate_bus_station, time_flights)
- Данные таблицы связаны между собой ключами(в данной программе по id)
- Таблицы intermediate_bus_station и time_flights связаны с таблицей bus_flights (таблица промежуточных остановок и дата рейсов привязаны к созданным рейсам)
- Программа в input принимает данные и выполняет следующие запросы:
1. Чтобы получить результат 2-го условия задачи необходимо нажать на кнопку "отправить запрос"
2. Чтобы получить результат 3-го условия задачи необходимо заполнить город отправления, город прибытия, выбрать дату и нажать на кнопку "отправить запрос"
3. Чтобы получить результат 3-го условия задачи необходимо заполнить город отправления, город прибытия, выбрать дату после поставить галочку в ячейке "information flight" и нажать на кнопку "отправить запрос"
- Данные для проверки можно посмотреть с помощью приложении для просмотра данных БД после запуска программы или в файле internal-->adapters-->database-->database.go-->метод(функция) "InsertDummyData"