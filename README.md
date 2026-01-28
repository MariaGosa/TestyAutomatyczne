**Task Manager API – Spring Boot**

Prosta aplikacja REST do zarządzania zadaniami.
Projekt zawiera automatyczne testy kontrolera i serwisu (JUnit 5 + MockMvc + Mockito).

**Technologie**

-Java 17
-Spring Boot
-Spring Web
-Spring Data JPA
-H2 Database (in-memory)
-JUnit 5
-MockMvc

🚀 Uruchomienie aplikacji
./mvnw spring-boot:run

Aplikacja będzie dostępna pod adresem:
http://localhost:8080

🔗 Endpointy API
Akcja	Metoda	Endpoint	Body
Pobierz wszystkie zadania	GET	/tasks	–
Dodaj nowe zadanie	POST	/tasks	{ "title": "Zrobić projekt", "completed": false }
🗄️ Konsola bazy H2

Adres: http://localhost:8080/h2-console

JDBC URL: jdbc:h2:mem:testdb

User: sa

Hasło: (puste)

✅ Testy automatyczne

Projekt zawiera dwa główne zestawy testów:

TaskControllerTest – testy kontrolera i endpointów z użyciem MockMvc (bez uruchamiania serwera)

TaskServiceTest – testy logiki biznesowej w serwisie z użyciem mocków repozytorium

🧪 TaskControllerTest

Cel:
Sprawdzenie, czy kontroler poprawnie obsługuje żądania HTTP.

Przykładowe testy:

GET /tasks – zwraca listę zadań i status 200

GET /tasks/{id} – zwraca zadanie po ID lub status 404

POST /tasks – tworzy nowe zadanie, status 201 i zwracany obiekt

PUT /tasks/{id} – aktualizuje zadanie, status 200 i zwracany obiekt

DELETE /tasks/{id} – usuwa zadanie, status 204

Dlaczego ważne:
Testy kontrolera chronią endpointy przed błędami i weryfikują poprawność odpowiedzi HTTP.

🧩 TaskServiceTest

Cel:
Sprawdzenie logiki biznesowej w serwisie TaskService.

Przykładowe testy:

findAllTasks() – zwraca listę wszystkich zadań

findTaskById(id) – zwraca zadanie lub wyrzuca wyjątek, jeśli nie istnieje

createTask(task) – zapisuje nowe zadanie

updateTask(id, task) – aktualizuje istniejące zadanie

deleteTask(id) – usuwa zadanie lub wyrzuca wyjątek, jeśli nie istnieje

Dlaczego ważne:
Zapewniają, że logika biznesowa działa poprawnie niezależnie od kontrolera.

⚡ Uruchamianie testów
W Visual Studio Code

Otwórz projekt w VS Code.

Otwórz Test Explorer (ikona flagi testowej).

VS Code automatycznie wykrywa testy w katalogu:

src/test/java/...


Możesz uruchomić testy:

Klikając Run przy klasie testowej (TaskControllerTest lub TaskServiceTest)

Klikając Run All Tests – uruchomi wszystkie testy w projekcie

Status testów:

Zielony = test przeszedł

Czerwony = test nie przeszedł

Przez Maven (terminal)
./mvnw test


Uruchamia wszystkie testy w katalogu src/test/java

Raporty szczegółowe znajdują się w folderze:

target/surefire-reports

✅ Podsumowanie

TaskControllerTest – testy endpointów i odpowiedzi HTTP

TaskServiceTest – testy logiki biznesowej

Testy można uruchamiać w VS Code lub przez Maven

Chronią projekt przed błędami podczas rozwoju nowych funkcjonalności
