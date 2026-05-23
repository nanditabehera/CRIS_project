# CRIS_project
Spring boot and PostgreSQL Project

A complete user registration and login system built with Spring Boot, PostgreSQL, and Maven.  
This project demonstrates secure password handling, custom login/signup pages, and integration with a real database.


### Features
- User registration with password encryption (BCrypt)  
- Custom login and signup pages  
- Spring Security configuration with form-based login  
- PostgreSQL integration via Spring Data JPA  
- Custom 404 error page  
- Static assets (CSS, JS, images) served from `/static/`  
- MVC routing for login, signup, and home pages  


### Tech Stack
- Java 17+  
- Spring Boot 3+  
- Spring Security  
- Spring Data JPA  
- PostgreSQL  
- Maven  
- Thymeleaf (for templates)  


### Folder Structure
src/  
├── main/  
│   ├── java/com/example/demo/  
│   │   ├── Controller/          (ContentController, RegistrationController)  
│   │   ├── Model/               (MyAppUser, MyAppUserRepository, MyAppUserService)  
│   │   ├── security/            (SecurityConfig)  
│   │   └── DemoApplication.java  
│   ├── resources/  
│   │   ├── templates/           (login.html, signup.html, index.html)  
│   │   ├── static/              (css/, js/, img/)  
│   │   ├── public/error/        (404.html)  
│   │   └── application.yml  
└── test/  
    └── java/com/example/demo/  
        └── DemoApplicationTests.java  


### Setup Instructions

#### 1. Configure PostgreSQL
Create a database named `registration`, then update `src/main/resources/application.yml`:

```yaml
spring:
  datasource:
    url: jdbc:postgresql://localhost:5432/registration
    username: postgres
    password: yourpassword

  jpa:
    hibernate:
      ddl-auto: update
    properties:
      hibernate:
        dialect: org.hibernate.dialect.PostgreSQLDialect
        format_sql: true
    show-sql: true
```

#### 2. Build and run

```bash
mvn clean install -DskipTests
java -jar target/demo-0.0.1-SNAPSHOT.jar
```

Or during development:

```bash
mvn spring-boot:run
```

#### 3. Access the app
- Signup page: `http://localhost:8080/req/signup`  
- Login page: `http://localhost:8080/req/login`  
- Home page after login: `http://localhost:8080/index`  
- 404 error example: visit any non-existing URL like `http://localhost:8080/xyz`  

---

### Sample SQL

To view registered users in PostgreSQL:

```sql
SELECT * FROM my_app_user;
```

### License

This project is open-source and free to use for educational or personal learning purposes.

