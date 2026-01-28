# Task Manager API – Spring Boot

Prosta aplikacja REST do zarządzania zadaniami, napisana w Spring Boot.
Projekt zawiera automatyczne testy kontrolera (JUnit + MockMvc).

## Technologie
- Java 17
- Spring Boot
- Spring Web
- Spring Data JPA
- H2 Database (in-memory)
- JUnit 5
- MockMvc

## Uruchomienie aplikacji

./mvnw spring-boot:run

Aplikacja będzie dostępna na:
http://localhost:8080

## Endpointy API

### Pobierz wszystkie zadania
GET /tasks

### Dodaj nowe zadanie
POST /tasks
Body (JSON):
{
  "title": "Zrobić projekt",
  "completed": false
}

## Konsola bazy H2
http://localhost:8080/h2-console

JDBC URL: jdbc:h2:mem:testdb
User: sa
Hasło: (puste)

## Testy automatyczne

Uruchomienie testów:
./mvnw test

Testy sprawdzają:
✔ pobieranie listy zadań  
✔ dodawanie nowego zadania  
z użyciem MockMvc (bez uruchamiania serwera)
