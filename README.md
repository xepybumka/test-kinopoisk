# Тестовое задание для веб-разработчика

Необходимо написать скрипт, собирающий данные с рейтинга Кинопоиска (http://www.kinopoisk.ru/top/) и сохраняющего 
позицию, рейтинг, оригинальное название, год и кол-во проголосовавших людей в БД (любой на выбор). Также нужно 
добавить соответствующие поля в БД для выборки рейтинга на определенную дату. Скрипт должен быть написан с учетом 
возможности постановки в cron.

Cоздать базовую веб-страницу, выводящую топ-10 фильмов на указанную дату. На ней должно присутствовать поле, где 
пользователь может указать дату выборки. При выгрузке данных из СУБД должен быть использован кэширующий слой, 
чтобы избежать запросов к базе, каждый раз, когда рейтинг должен быть показан.

Критерии оценки:

*	Symfony
*	чистый, читаемый, структурируемый php код, объектное ориентированный дизайн
*	схема базы данных
*	чистота верстки

---
План разработки:
1. Подготовить окружение: Docker + PHP + nginx + PosgtgreSQL.
Добавить установку symfony-cli в контейнер. Развернуть новый проект symfony в папке app.
2. Создать миграцию на таблицу для кинопоиска со следующими полями: 
id, Позиция, рейтинг, название, год, кол-во голосов.
3. Написать cron-скрипт, который будет обновлять рейтинг с кинопоиска.
4. Создать страницу, на которой будут выводиться Топ-10 фильмов кинопоиска на указанную дату.
5. Добавить фильтр по дате выборки.
6. Добавить кэширование для базы данных.
