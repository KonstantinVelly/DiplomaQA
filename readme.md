# Порядок запуска Дипломного проекта профессии "Тестировщик".
1. Запустить Virtual Docker 

2. Открыть тестовый проект в IntelliJ IDEA

3. В терминале IntelliJ IDEA выполнить команду docker-compose up -d , дождаться подъема контейнеров (около 1 минуты).

4. В терминале IntelliJ IDEA выполнить команду для запуска приложения:

для MySQL: java -jar artifacts\aqa-shop.jar --spring.datasource.url=jdbc:mysql://localhost:3306/app

для Postgres: java -jar artifacts\aqa-shop.jar --spring.datasource.url=jdbc:postgresql://localhost:5432/app

5. В терминале IntelliJ IDEA выполнить команду для прогона автотестов: (Полный прогон автотестов занимает от 20 до 24 минут.)
для MySQL: .\gradlew clean test -D dbUrl=jdbc:mysql://localhost:3306/app -D dbUser=app -D dbPass=pass
для Postgres: .\gradlew clean test -D dbUrl=jdbc:postgresql://localhost:5432/app -D dbUser=app -D dbPass=pass
6. В терминале IntelliJ IDEA выполнить команду для получения отчета: .\gradlew allureServe
7. После завершения прогона автотестов и получения отчета:

+ Завершить обработку отчета сочетанием клавиш CTRL + C, в терминале нажать клавишу Y, нажать Enter.
+ Закрыть приложение сочитанием клавиш CTRL + C в терминале запуска.
+ Остановить работу контейнеров командой docker-compose down.

## Ссылки на документацию:
1) Дипломное задание
2) План автоматизации
3) Отчет по итогам тестрования
4) Отчет о проведенной автоматизации
