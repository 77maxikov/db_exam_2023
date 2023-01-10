# Тестовая база данных для реляционных запросов

1. db_diagram.svg - схема БД
2. db_create_maria.sql - скрипт для создания таблиц и начального заполнения таблиц в MariaDB
3. db_create_postgre.sql - скрипт для создания таблиц и начального заполнения таблиц в PostgreSQL
4. db_populate_maria.sql - скрипт для заполнения таблиц в MariaDB
5. db_populate_postgre.sql - скрипт для заполнения таблиц в PostgreSQL


## Предметная область:
Векторное рисование с ограничениями

Рисунки можно создавать, формируя их из отдельных слоев, на которых размещаются примитивы - точки, отрезки, окружности и др. Каждый нетривиальный примитив или объект (не точка) определяется упорядоченным набором точек и, возможно, дополнительными параметрами (например, радиус для окружности). Для каждого из типов объектов известно количество степеней свободы - как общее количество параметров, с помощью которых можно однозначно задать данный примитив. Относительно примитивов, составляющих рисунок, могут быть рассмотрены ограничения (например, отрезок доложен быть вертикальным, окружности могут быть концентрическими и т.д.). Кроме простых ограничений, можно рассматривать параметрические ограничения (например, отрезок должен иметь указанную длину).
Поддерживаются следующие типы примитивов:

- Точка
- Отрезок
- Окружность
- Дуга окружности

Поддерживаются следующие типы ограничений:
- Неподвижность
- Равенство
- Вертикальность
- Горизонтальность
- Расстояние
- Угол
- Параллельность
- Перпендикулярность
- Касание
- Принадлежность
- Середина
- Коллинеарность
- Размер
- Симметричность
- Концентричность
- Равноудаленность от точки

## Данные:

- Сущность Слой (layer) идентифицируется целым числом и содержит информацию о времени последнего обновления.

- Сущность Параметр (param) идентифицируется целым числом и содержит информацию о величине параметра, характеризующего (возможно частично) некоторый примитив.

- Сущность Примитив (entity) идентифицируется целым числом. Примитивами являются как объекты, так и ограничения.

- Сущность Объект (object) идентифицируется целым числом и содержит информацию о типе объекта. Для точек, с помощью которых задаются более сложные объекты, должен быть указан родительский объект. Точки могут быть и вполне обособленными. 

- Сущность Ограничение (constraint) идентифицируется целым числом и содержит информацию о примитивах, связываемых данным ограничением, а также, в зависимости от типа ограничения, о значении параметра, его характеризующего.



## Общие ограничения целостности:
Каждый примитив должен располагаться на каком либо одном слое.
Точки, определяющие объект, должны располагаться на том же слое, что и сам объект.
Объекты могут быть связаны произвольным количеством ограничений.
Каждое ограничение обязательно связано с каким либо объектом.
