﻿# Рубежка 1 - вариант 6
Вопрос:
> Зачем в облаке предусмотрено столько регионов? Зачем там кроме регионов еще и зоны?

## Зачем в облаке предусмотрено столько регионов?

По сути, краткий ответ - для гибкости всей системы ну и для устойчивости с целостностью данных.

В целом, количество регионов влияет на положительный экспириенс пользователей. Говоря конкретней я выделил 3 основных причины:
1. Близость к регионам позволяет добиться более быстрого ответа на стороне пользователя.
2. Разделение ресурсов между ними, чтобы условно если появился баг в одном регионе, то он никак не повлиял на другой
> Говоря более подробно о втором пункте можно вспомнить сбой AWS в регионе us-east-1 в 2017. Хотя это и было вызвано больше человеческо ошибкой, но все же, был бы соблюден это пункт, то все бы обошлось. Дак вот, в чем суть, такие приложения как Slack, Trello, Quora полагались лишь на этот сервер, а из-за ошибки инженера, который что-то там натыкал и отключил несколько важных вещей для работы S3, а так как у большего числа клиентов не была настроена репликация данных в другие регионы, что сделало их приложения уязвимыми. А компания получила "застой" в работе приложений
3. Ну и третим пунктом я бы выделил локальные требования. Если у компнии есть необходимость соблюдать правительственное законодательство какой-то страны, то скорее всего это будет производится по средства регионов в облаке.

На счет зон могу сказать, что это, как по мне, лишь лишняя предосторожность, условно в регионе есть несколько зон, которые находятся на физ объектах и чтобы при условном отключении света в одном месте все не полегло разом. Ну и это все же какая-то масштабируемость, так как работать с этим будет потом куда более приятно.

## Зачем там кроме регионов еще и зоны?
При сбое одной зоны пользователь этого не заметит, так как приложение будет работать просто с другой зоной. Так же стоит учитывать, что и весь регион может выйти из строя, но тут, как по мне, при правильной настройке, это потом можно будет востановить, условная репликация данных может с этим помочь, нго это уже, другой вопрос

