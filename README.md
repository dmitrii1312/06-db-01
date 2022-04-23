## Задача 1
Выберите подходящие типы СУБД для каждой сущности и объясните свой выбор.

- Электронные чеки в json виде - Документо-ориентированная БД, т.к. содержание чека не строго определено
- Склады и автомобильные дороги для логистической компании - Графовая БД, т.к. потребуется рассчитывать логистику
- Генеалогические деревья - Иерархическая БД - наиболее близка к структуре хранимых данных
- Кэш идентификаторов клиентов с ограниченным временем жизни для движка аутенфикации - БД ключ-значение, требуется хранить одно значение для какого-то ключа
- Отношения клиент-покупка для интернет-магазина - Реляционная БД, т.к. нужно хранить связи клиентов с покупками 

## Задача 2

Какой классификации по CAP-теореме соответствует ваша система, если (каждый пункт - это отдельная реализация вашей системы и для каждого пункта надо привести классификацию):

- Данные записываются на все узлы с задержкой до часа (асинхронная запись) - у системы могут быть проблемы с согласованностью данных между узлами
- При сетевых сбоях, система может разделиться на 2 раздельных кластера - система устойчива к разделению
- Система может не прислать корректный ответ или сбросить соединение - у системы могут быть проблемы с согласованностью и доступностью

А согласно PACELC-теореме, как бы вы классифицировали данные реализации?

- Данные записываются на все узлы с задержкой до часа (асинхронная запись) - PA/EC
- При сетевых сбоях, система может разделиться на 2 раздельных кластера - PC/EL
- Система может не прислать корректный ответ или сбросить соединение - PC/EC

## Задача 3
Могут ли в одной системе сочетаться принципы BASE и ACID? Почему?

Нет, не могут, т.к. имеют разные цели и противоположные принципы, такие как Consistent(ACID) не равно Evantualy Consistent. Atomic так же противоречит Soft State.


## Задача 4
Вы слышали о key-value хранилище, которое имеет механизм Pub/Sub. Что это за система? Какие минусы выбора данной системы?

Это система Publisher/subscriber, т.е. есть издатели сообщений, которые создают сообщения, и есть подписчики, которые принимают и обрабатывают сообщения. Проблема таких систем, что они построены по принципам BASE, с присущими этим принципам недостатками.
Как пример такой системы - Redis.

