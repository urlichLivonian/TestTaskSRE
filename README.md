﻿# SRE test task

Необходимо написать скрипт для установки этого приложения внутри виртуальной машины с ОС Windows 2012R2 и поддержания его работоспособности в будущем. Образ необходимо брать https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2012-r2

**Не должно быть ручных действий, все действия осуществляются скриптом.**

Сценарий использования:
Запускаем образ -> Запускаем скрипт -> Магия об окончании которой нам сигнализирует сработавший вебхук -> Приложение работает

Скрипт должен:
* проверить наличие необходимых ролей, развернуть при необходимости
* создать отдельный пул, сайт
* скачать приложение с гита либо получить в архиве
* положить всё в папочку, настроить верные права
* убедиться что всё работает
* отписать в slack при помощи webhook http://bit.ly/devopstask что выполнен успешно
* логировать в файл на уровне достаточном для понимания возникших проблем
* при повторном прогоне выполнять только необходимые действия

Вы должны:
* понимать полностью что и зачем делает ваш скрипт

Идеальный вариант:
* проверять состояние сервера по расписанию
  * куда-то сбежал iis - скрипт должен вернуть
  * обновилось приложение в гите - перевыложить

ps. В случае успешной отправки сообщения в slack, сервер возвращает текст **ok** и статус **200**
