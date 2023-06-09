# YP_kinopoisk
# Кинопоиск (1-й сборный проект)

В нашем распоряжении данные опубликованные на портале открытых данных Министерства культуры. Набор данных содержит информацию о прокатных удостоверениях, сборах и государственной поддержке фильмов, а также информацию с сайта КиноПоиск. 

**Цель исследования:**
Изучить рынок российского кинопроката и выявить текущие тренды. Выделить фильмы, которые получили государственную поддержку. Ответить на вопрос, насколько такие фильмы интересны зрителю. Заказчик этого исследования — Министерство культуры Российской Федерации.

- посмотрим, сколько фильмов выходило в прокат каждый год.

- изучим, как менялась динамика проката по годам. В каком году сумма сборов была минимальной? А максимальной?

- с помощью сводной таблицы посчитаем среднюю и медианную сумму сборов для каждого года. Сравним значения.

- определим, влияет ли возрастное ограничение аудитории («6+», «12+», «16+», «18+» и т. д.) на сборы фильма в прокате в период с 2015 по 2019 год? Фильмы с каким возрастным ограничением собрали больше всего денег в прокате? Меняется ли картина в зависимости от года? Если да, предположите, с чем это может быть связано.

- иссдедуем фильмы, которые уже получили государственную поддержку

**Ход исследования:**

Для исследования предоставлены 2 набора данных:

1. Таблица `mkrf_movies` содержит информацию из реестра прокатных удостоверений. У одного фильма может быть несколько прокатных удостоверений.
* `title` — название фильма;
* `puNumber` — номер прокатного удостоверения;
* `show_start_date` — дата премьеры фильма;
* `type` — тип фильма;
* `film_studio` — студия-производитель;
* `production_country` — страна-производитель;
* `director` — режиссёр;
* `producer` — продюсер;
* `age_restriction` — возрастная категория;
* `refundable_support` — объём возвратных средств государственной поддержки;
* `nonrefundable_support` — объём невозвратных средств государственной поддержки;
* `financing_source` — источник государственного финансирования;
* `budget` — общий бюджет фильма;
* `ratings` — рейтинг фильма на КиноПоиске;
* `genres` — жанр фильма.

Известно, что столбец `budget` уже включает в себя полный объём государственной поддержки. Данные в этом столбце указаны только для тех фильмов, которые получили государственную поддержку.

Таблица `mkrf_shows` содержит сведения о показах фильмов в российских кинотеатрах.
* `puNumber` — номер прокатного удостоверения;
* `box_office` — сборы в рублях.

О качестве данных ничего не известно. Поэтому перед исследованием понадобится обзор данных.

Мы проверим данные на ошибки и оценим их влияние на исследование. Затем, на этапе предобработки мы поищем возможность исправить самые критичные ошибки данных.

Таким образом, исследование пройдёт в три этапа:

1. Изучение данных из файла. 
2. Предобработка данных.
3. Исследовательнский анализ и выводы.
