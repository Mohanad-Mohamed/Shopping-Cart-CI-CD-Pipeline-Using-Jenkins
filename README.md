# 🛒 Spring Boot Shopping Cart

![Project Architecture](project-architecture.png)

A full-featured shopping cart web application built with Spring Boot and Thymeleaf. This application demonstrates modern web development practices including user authentication, session management, and database operations.

## ✨ Features

- User authentication (login/registration)
- Role-based access control (Admin/User)
- Product catalog management
- Shopping cart functionality
- Checkout process
- Order history
- Responsive design with Thymeleaf
- In-memory H2 database
- Docker support

## 🚀 Technologies Used

- **Backend**: Spring Boot, Spring Security, Spring Data JPA, Spring Data REST
- **Frontend**: Thymeleaf, Bootstrap, JavaScript
- **Database**: H2 (in-memory)
- **Build Tool**: Maven
- **Containerization**: Docker

## 🛠️ Prerequisites

- Java 11 or higher
- Maven 3.6.3 or higher
- Docker (optional)
- Your favorite IDE (IntelliJ IDEA, Eclipse, etc.)

## 🚀 Getting Started

### Running with Maven Wrapper

1. **Using Maven Plugin**:
   ```bash
   # Make the wrapper executable
   chmod +x mvnw
   
   # Run the application
   ./mvnw spring-boot:run
   ```

2. **Build and Run JAR**:
   ```bash
   # Build the application
   ./mvnw clean package
   
   # Run the JAR file
   java -jar target/shopping-cart-0.0.1-SNAPSHOT.jar
   ```

### Running with Docker

1. Build the Docker image:
   ```bash
   docker build -t shopping-cart .
   ```

2. Run the container:
   ```bash
   docker run -p 8070:8070 shopping-cart
   ```

## 🔑 Default Credentials

- **Admin Panel**
  - URL: http://localhost:8070/admin
  - Username: `admin`
  - Password: `admin`

- **User Account**
  - URL: http://localhost:8070/login
  - Username: `user`
  - Password: `password`

## 🏗️ Project Structure

```
src/main/
├── java/
│   └── com/shoppingcart/
│       ├── config/         # Configuration classes
│       ├── controller/     # MVC Controllers
│       ├── model/          # Entity classes
│       ├── repository/     # Data access layer
│       ├── security/       # Security configuration
│       ├── service/        # Business logic
│       └── ShoppingCartApplication.java
├── resources/
│   ├── static/            # Static resources
│   ├── templates/         # Thymeleaf templates
│   └── application.properties
```

## 📂 Configuration

Main configuration file: `src/main/resources/application.properties`

Key configurations:
- Server port
- Database connection
- Security settings
- Logging levels

## 🧪 Testing

Run tests using Maven:
```bash
./mvnw test
```

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Built with ❤️ using Spring Boot
- Bootstrap for responsive design
- All contributors who have helped improve this project

First, verify that Java and Maven are properly installed:

$ java -version
java version "1.8.0_102"
Java(TM) SE Runtime Environment (build 1.8.0_102-b14)
Java HotSpot(TM) 64-Bit Server VM (build 25.102-b14, mixed mode)

$ mvn -v
Apache Maven 3.3.9 (...)
Maven home: /usr/local/Cellar/maven/3.3.9/libexec
Java version: 1.8.0_102, vendor: Oracle Corporation

1. Using the Maven Plugin
$ mvn spring-boot:run

2. Building & Running Executable JAR
$ mvn clean package
$ java -jar target/shopping-cart-0.0.1-SNAPSHOT.jar


To stop the application, press CTRL + C.

Running with Docker
----------------------

You can also build and run the application inside a Docker container.

Build Docker Image
$ mvn clean package
$ docker build -t shopping-cart:dev -f docker/Dockerfile .

Run Docker Container
$ docker run --rm -i -p 8070:8070 \
      --name shopping-cart \
      shopping-cart:dev

Using Helper Script
$ chmod +x scripts/run_docker.sh
$ scripts/run_docker.sh

Project Structure
----------------------
Docker
----------------------
The docker/ folder contains:
----------------------
docker/shopping-cart/Dockerfile – Defines how the Docker image is built and how the application is started inside the container.

Utility Scripts
----------------------
scripts/run_docker.sh – Script for building and running the Docker container.

Running Tests
----------------------
From the project root, run:

$ mvn test

Tools & Interfaces
----------------------
HAL REST Browser
----------------------

Visit: http://localhost:8070/ (requires authentication).

H2 Database Console
----------------------

Visit: http://localhost:8070/h2-console

JDBC URL:
----------------------

jdbc:h2:mem:shopping_cart_db


Both the H2 console path and datasource URL can be modified in /src/main/resources/application.properties.
