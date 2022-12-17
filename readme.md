# Порядок запуска Дипломного проекта профессии "Тестировщик".
1. Запустить Docker Desktop

1. Открыть тестовый проект в IntelliJ IDEA

1. В терминале IntelliJ IDEA выполнить команду docker-compose up -d , дождаться подъема контейнеров.

1. В терминале IntelliJ IDEA выполнить команду для запуска приложения:

- для MySQL: java -jar .\aqa-shop.jar --spring.datasource.url=jdbc:mysql://localhost:3306/app

- для Postgres: java -jar .\aqa-shop.jar --spring.datasource.url=jdbc:postgresql://localhost:5432/app

2. В терминале IntelliJ IDEA выполнить команду для прогона автотестов: 
- для MySQL: .\gradlew clean test -D dbUrl=jdbc:mysql://localhost:3306/app -D dbUser=app -D dbPass=pass
- для Postgres: .\gradlew clean test -D dbUrl=jdbc:postgresql://localhost:5432/app -D dbUser=app -D dbPass=pass
3. В терминале IntelliJ IDEA выполнить команду для получения отчета: .\gradlew allureServe
## После завершения прогона автотестов и получения отчета:

- Завершить обработку отчета сочетанием клавиш CTRL + C, в терминале нажать клавишу Y, нажать Enter.
- Закрыть приложение сочитанием клавиш CTRL + C в терминале запуска.
- Остановить работу контейнеров командой docker-compose down.

# Документация:
1) Дипломное задание
2) План автоматизации
3) Отчет по итогам тестрования
4) Отчет о проведенной автоматизации
