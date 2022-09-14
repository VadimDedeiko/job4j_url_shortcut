# Проект URLShortCut

Сервис работает через REST API.
Функционал.

* Регистрация сайта.
Сервисом могут пользоваться разные сайты. Каждому сайту выдается пару пароль и логин.
Чтобы зарегистрировать сайт в систему нужно отправить запрос POST http://localhost:8080/registration
с телом JSON объекта
{site : "регистрируемый хост"}

* Авторизация
POST http://localhost:8080/login.
В блоке HEAD вы получите tocken

* Регистрация URL
POST http://localhost:8080/convert
C телом JSON объекта.
{url: "ссылка URL"}
В теле ответа получите УНИКАЛЬНЫЙ_КОД

* Переадресация. Выполняется без авторизации.
Запрос:
GET http://localhost:8080/redirect/УНИКАЛЬНЫЙ_КОД
В блоке HEAD ответа получите HTTP CODE - 302 REDIRECT "зарегистрированный URL"

* Статистика.
В сервисе считается количество вызовов каждого адреса.
По сайту можно получить статистку всех адресов и количество вызовов этого адреса.
Запрос:
GET http://localhost:8080/statistic