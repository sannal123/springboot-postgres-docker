Spring Boot + PostgreSQL + Docker
A simple CRUD REST API built with Spring Boot, PostgreSQL, and Docker.
This project demonstrates how to integrate Spring Boot with PostgreSQL using Docker for database containerization.

🚀 Tech Stack
Java 17 (or your installed version)
Spring Boot (Spring Web, Spring Data JPA)
PostgreSQL (via Docker)
Docker Compose
Maven

📦 Project Structure
src/
 ├── main/
 │   ├── java/com/example/demo/
 │   │   ├── SoftwareEngineer.java
 │   │   ├── SoftwareEngineerRepository.java
 │   │   ├── SoftwareEngineerService.java
 │   │   ├── SoftwareEngineerController.java
 │   └── resources/
 │       ├── application.properties
docker-compose.yml
pom.xml


🛠️ Setup & Run
1️⃣ Start PostgreSQL with Docker
docker-compose up -d
This will:
Run PostgreSQL on port 5332
Create database demodb
Create user sanal with password password

2️⃣ Configure Spring Boot
src/main/resources/application.properties:

spring.application.name=demo
spring.datasource.url=jdbc:postgresql://localhost:5332/demodb
spring.datasource.username=s****
spring.datasource.password=password
spring.datasource.driver-class-name=org.postgresql.Driver

spring.jpa.hibernate.ddl-auto=create-drop
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.PostgreSQLDialect
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.format_sql=true

3️⃣ Run the Spring Boot Application
mvn spring-boot:run


📡 API Endpoints
Get all software engineers:
GET /api/v1/software-engineers

Get software engineer by ID:
GET /api/v1/software-engineers/{id}
Add new software engineer:

POST /api/v1/software-engineers
Content-Type: application/json

{
  "name": "James",
  "techStack": "React"
}

🐳 Docker Commands
# Start containers
docker-compose up -d

# Stop containers
docker-compose down

# Connect to database inside container
docker exec -it postgres-spring-boot psql -U UserID -d demodb





