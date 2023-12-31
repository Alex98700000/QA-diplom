# Отчёт о проведённой автоматизации
## Запланировано:

1. Планирование автоматизации тестирования.
    
2. Автоматизация:
   * Автоматизация позитивных и негативных UI сценариев, тестирования сервисов покупки туров ("Оплата по карте" и "Кредит по данным карты");
   * Автоматизация API сценариев;
   * Реализация поддержки БД MySQL и PostgeSQL;
   * Интеграция с системой репортов (Gradle/Allure);
   
3. Подготовке отчётных документов по итогам автоматизированного тестирования.
   
## Выполнено:

1. В соответствии с планом автоматизации, в проекте была реализована автоматизация тестирования всех запланированных сценариев:
   * Позитивные сценарии покупки тура по карте;
   * Позитивные сценарии покупки тура по карте в кредит;
   * Сценарии позитивного и негативного тестирования всех полей формы (Номер карты, Месяц, Год, Владелец, CVC/CVV).

2. Подключено и настроено для интеграции с системой репортов Gradle.
   
3. В результате проведения тестирования сформирован отчет по итогам тестирования 
   * В отчете указано количество тест кейсов;
   * Статистика в % успешных/неуспешных кейсов;
   * Общие рекомендации по устранению багов.
   
## Сработавшие риски
* Потрачено много времени при настройке запуска симулятора банковских карт;
* Сложности при настройке двух СУБД ("MySQL" и "PostgreSQL");

## Общий итог по времени
1. Разработка плана тестирования:
    * Запланировано - 20 часов, фактически потрачено - 25 часов.
2. Автоматизация тестирования: 
    * Запланировано - 45 часов, фактически потрачено - 50 часов.
3. Подготовка отчетной документации по итогам автоматизации тестирования: 
    * Запланировано - 8 часов, фактически потрачено - 8 часов.
4.  * Дополнительно на устранение последствий непредвиденных обстоятельств для реализации проекта 10 часов.
      




