# QA-diplom

#### Документы
 - [План тестирования](documentation/Plan.md)
 - [Отчет по итогам тестирования](https://github.com/
 - [Отчет по итогам автоматизации](https://github.com/
 
#### Описание приложения
Приложение представляет из себя веб-сервис "Путешествие дня".

Приложение предлагает купить тур по определённой цене с помощью двух способов:

1. Обычная оплата по дебетовой карте
2. Уникальная технология: выдача кредита по данным банковской карты

Само приложение не обрабатывает данные по картам, а пересылает их банковским сервисам:

 - сервису платежей (далее - Payment Gate)
 - кредитному сервису (далее - Credit Gate)
 
Приложение должно в собственной СУБД сохранять информацию о том, каким способом был совершён платёж и успешно ли он был совершён (при этом данные карт сохранять не допускается).
 
#### Запуск тестов

 1. склонировать репозиторий ```git clone ```
 2. необходим установленный Docker. Для запуска контейнеров с MySql, PostgreSQL использовать команду 
 ```sh
 docker-compose up -d --build 
 ```
 чтобы образ не пересобирался каждый раз необходимо убрать флаг ```--build```
 
 3. запуск приложения:
   - для запуска под MySQL использовать команду
 
 ```java "-Dspring.datasource.url=jdbc:mysql://localhost:3306/app" -jar aqa-shop.jar```
 
   - для запуска под PostgreSQL использовать команду 
   
   ```java "-Dspring.datasource.url=jdbc:postgresql://localhost:5432/app" -jar aqa-shop.jar```
   

4. запуск тестов (Allure):
  - для запуска под MySQL использовать команду 
   
   ```.\gradlew "-Ddb.url=jdbc:mysql://localhost:3306/app" clean test```
   

   - для запуска под PostgreSQL использовать команду 
    
   ```.\gradlew "-Ddb.url=jdbc:postgresql://localhost:5432/app" clean test```

*По умолчанию тесты запускаются для "http://localhost:8080/", чтобы изменить адрес, необходимо дополнительно указать -Dsut.url=...
*Чтобы использовать для подключения к БД логин и пароль отличные от указанных по умолчанию, необходимо дополнительно указать -Ddb.user=... и -Ddb.password=...

5. для получения отчета (Allure) использовать команду ```.\gradlew allureServe```
6. после окончания тестов завершить работу приложения (Ctrl+C), остановить контейнеры командой ```docker-compose down```
