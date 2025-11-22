

# Spring Boot REST APIs: Building Modern APIs with Spring Boot

Source code for the course: [Spring Boot REST APIs](https://www.udemy.com/course/spring-boot-rest-apis/)

If you have questions or need tech support, post your questions to the [classroom discussion forum](https://www.udemy.com/spring-boot-rest-apis/learn/v4/questions).

Happy coding!

[<img src="images/spring-boot-rest-apis-thumbnail-small.jpg">](https://www.udemy.com/course/spring-boot-rest-apis/)

&#8287;
## Spring Boot Road Map - Learning Path

Here is a Spring Boot Learning Path and Roadmap to help you learn more about Spring Boot. These are links to luv2code courses on Udemy. You can purchase the courses to further your studies.

I'd recommend the following road map:

### Core Courses
1. [Java Programming Introduction for Beginners](https://www.udemy.com/course/java-intro-for-beginners/?referralCode=325F0EA33466DA1D8710)
1. [Spring Boot 3, Spring 6 and Hibernate for Beginners](http://www.luv2code.com/spring-github)
1. [Spring Boot Unit Testing](https://www.udemy.com/course/spring-boot-unit-testing/?referralCode=4184DE360D78A70932EE)
1. [Deploy Spring Boot 3 Apps on AWS (Amazon Cloud)](https://www.udemy.com/course/deploy-spring-boot-3-apps-to-aws/?referralCode=DCE8981B59C70BA6BDBF)
1. [Hibernate: Advanced Development Techniques](https://www.udemy.com/course/hibernate-tutorial-advanced/?referralCode=6FB9E2BA9AF54A4C9E69)
1. [Master Java Design Patterns](https://www.luv2code.com/master-java-design-patterns-github)

### Project Course: Spring Boot, Spring MVC and Thymeleaf
For end-to-end project with Spring Boot, Spring MVC and Thymeleaf:
1. [Spring Boot 3 Project - Build a Job Portal Web Application](https://www.udemy.com/course/spring-boot-project-job-portal-web-app/?referralCode=BB9301596150194B61E2)

### REST API Project Course: Spring Boot REST APIs
This is an intermediate level course that includes four REST API projects:
1. [Spring Boot REST APIs - Building Modern APIs with Spring Boot](https://www.udemy.com/course/spring-boot-rest-apis/)

### Project Courses: Full Stack
For full stack projects, you have the choice of either Angular or React. Pick the one that you like the best.
1. [Full Stack: Angular and Spring Boot](https://www.udemy.com/course/full-stack-angular-spring-boot-tutorial/?referralCode=2264F90C65A86316BB6B)
1. [Full Stack: React and Spring Boot](https://www.udemy.com/course/full-stack-react-and-java-spring-boot-the-developer-guide/?referralCode=4325FA579FD3D313E28D)

&#8287;
## More luv2code Courses
For more courses, visit the [luv2code website](https://www.luv2code.com). 

I'm looking forward to seeing you in other luv2code courses! 

&#8287;
## Follow luv2code on Social Media
* [YouTube Channel - luv2code](https://www.youtube.com/user/luv2codetv?sub_confirmation=1)
* [Facebook Page - luv2code](https://www.facebook.com/luv2codetv)
* [X (Twitter) - luv2code](https://twitter.com/luv2codetv)
* [LinkedIn](https://www.linkedin.com/in/chaddarby/)

&#8287;
## License
This source code and all related course materials are provided for your personal learning and educational use as part of a course by [luv2code LLC](https://www.luv2code.com).

You may:
- Use and modify the source code for your own personal projects  
- Use and modify the source code in your work or professional projects, including commercial applications  
- Integrate or extend the source code to build your own applications  

No action or special requests are required to use the source code in this way.

---

You may not:
- Republish, redistribute, or upload any course materials, including but not limited to videos, slides, images, text, or PDFs  
- Use any course materials to create derivative educational content such as tutorials, blog posts, YouTube videos, online courses, training content, or social media content  
- Use any course materials in teaching, training, or commercial educational products  
- Claim any course materials as your own work  

See the [LICENSE](./LICENSE) file for full terms and restrictions. 
 
For permission requests, contact **copyright@luv2code.com**



















# Product Management CRUD API

A RESTful API built with Spring Boot that provides complete CRUD operations for product management with authentication, validation, and comprehensive error handling.

## 🚀 Features

- **Complete CRUD Operations**: Create, Read, Update, Delete products
- **Input Validation**: Bean Validation (JSR 380) with custom error messages
- **Authentication**: Basic HTTP authentication
- **API Documentation**: Interactive Swagger UI
- **Global Exception Handling**: Centralized error management
- **Database Integration**: MySQL with JPA/Hibernate
- **Custom Error Messages**: Internationalized validation messages

## 🛠️ Technology Stack

- **Java**: 17
- **Spring Boot**: 3.5.7
- **Spring Data JPA**: Database operations
- **Spring Security**: Authentication
- **Spring Validation**: Input validation
- **MySQL**: Database
- **Swagger/OpenAPI 3**: API documentation
- **Lombok**: Boilerplate code reduction
- **Maven**: Build tool

## 📋 Prerequisites

Before running this application, ensure you have:

1. **Java 17** or higher installed
2. **MySQL 8.0+** installed and running
3. **Git** for cloning the repository

**Note**: Maven installation is **NOT required** - this project includes Maven Wrapper!

### Java Installation
```bash
# Check if Java is installed
java -version

# If not installed, download from:
# https://www.oracle.com/java/technologies/javase/jdk17-archive-downloads.html
# or use OpenJDK: https://openjdk.org/projects/jdk/17/
```

### MySQL Installation
```bash
# Download MySQL from: https://dev.mysql.com/downloads/mysql/
# Or use MySQL Workbench for GUI: https://dev.mysql.com/downloads/workbench/
```

## 🏗️ Project Structure

```
productmgmnt/
├── src/
│   ├── main/
│   │   ├── java/com/fullstack/
│   │   │   ├── advice/
│   │   │   │   └── GlobalExceptionHandler.java    # Global error handling
│   │   │   ├── config/
│   │   │   │   ├── OpenApiConfig.java             # Swagger configuration
│   │   │   │   └── SecurityConfig.java            # Security configuration
│   │   │   ├── controller/
│   │   │   │   └── ProductController.java         # REST endpoints
│   │   │   ├── dto/
│   │   │   │   └── ErrorResponse.java             # Error response model
│   │   │   ├── entity/
│   │   │   │   └── Product.java                   # JPA entity
│   │   │   ├── exception/
│   │   │   │   └── RecordNotFoundException.java   # Custom exception
│   │   │   ├── repository/
│   │   │   │   └── ProductRepository.java         # Data access layer
│   │   │   ├── service/
│   │   │   │   └── ProductService.java            # Business logic
│   │   │   └── ProductmgmntApplication.java       # Main application
│   │   └── resources/
│   │       ├── application.properties             # Configuration
│   │       └── messages.properties                # Validation messages
│   └── test/
├── pom.xml                                        # Maven dependencies
└── README.md
```

## ⚙️ Configuration

### Database Setup

1. **Create MySQL Database**:
```sql
CREATE DATABASE chayandb;
```

2. **Update Database Configuration** in `application.properties`:
```properties
# Database Configuration
spring.datasource.url=jdbc:mysql://localhost:3306/chayandb?createDatabaseIfNotExist=true
spring.datasource.username=root
spring.datasource.password=your_password_here
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver

# JPA/Hibernate Configuration
spring.jpa.hibernate.ddl-auto=create-drop
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQLDialect
```

3. **Update Security Credentials**:
```properties
# Security Configuration
spring.security.user.name=admin
spring.security.user.password=password
spring.security.user.roles=USER
```

## 🚀 Getting Started

### 1. Clone the Repository
```bash
git clone <your-repository-url>
cd productmgmntcrud/productmgmnt
```

### 2. Configure Database
- Ensure MySQL is running
- Update `application.properties` with your database credentials

### 3. Build the Project
```bash
# Windows
.\mvnw.cmd clean install

# Linux/Mac
./mvnw clean install
```

### 4. Run the Application
```bash
# Windows
.\mvnw.cmd spring-boot:run

# Linux/Mac
./mvnw spring-boot:run
```

Or run the JAR file:
```bash
java -jar target/productmgmnt-0.0.1-SNAPSHOT.jar
```

### 5. Verify Installation
- Application will start on `http://localhost:8080`
- Swagger UI: `http://localhost:8080/swagger-ui.html`
- API Docs: `http://localhost:8080/v3/api-docs`

## 📚 API Endpoints

### Authentication
All endpoints require Basic Authentication:
- **Username**: `admin`
- **Password**: `password`

### Product Operations

| Method | Endpoint | Description | Request Body |
|--------|----------|-------------|--------------|
| GET | `/products` | Get all products | None |
| GET | `/products/{id}` | Get product by ID | None |
| POST | `/products` | Create new product | Product JSON |
| PUT | `/products/{id}` | Update product | Product JSON |
| DELETE | `/products/{id}` | Delete product | None |
| POST | `/addProducts` | Create multiple products | Array of Products |

### Product Model
```json
{
  "id": 1,
  "name": "Product Name",
  "description": "Product Description",
  "price": 99.99
}
```

### Validation Rules
- **Name**: Required, 2-100 characters
- **Description**: Required, 5-500 characters  
- **Price**: Required, minimum 0.01

## 🧪 Testing the API

### Using cURL

1. **Create a Product**:
```bash
curl -X POST http://localhost:8080/products \
  -u admin:password \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Laptop",
    "description": "High-performance laptop for gaming",
    "price": 1299.99
  }'
```

2. **Get All Products**:
```bash
curl -X GET http://localhost:8080/products \
  -u admin:password
```

3. **Get Product by ID**:
```bash
curl -X GET http://localhost:8080/products/1 \
  -u admin:password
```

4. **Update Product**:
```bash
curl -X PUT http://localhost:8080/products/1 \
  -u admin:password \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Gaming Laptop",
    "description": "Updated high-performance gaming laptop",
    "price": 1399.99
  }'
```

5. **Delete Product**:
```bash
curl -X DELETE http://localhost:8080/products/1 \
  -u admin:password
```

### Using Swagger UI

1. Navigate to `http://localhost:8080/swagger-ui.html`
2. Click "Authorize" and enter credentials (`admin`/`password`)
3. Test endpoints interactively

## 🔧 Development

### Running Tests
```bash
# Windows
.\mvnw.cmd test

# Linux/Mac
./mvnw test
```

### Building for Production
```bash
# Windows
.\mvnw.cmd clean package -Dmaven.test.skip=true

# Linux/Mac
./mvnw clean package -Dmaven.test.skip=true
```

### Hot Reload (Development)
The application includes Spring Boot DevTools for automatic restart during development.

## 📊 Error Handling

The API provides comprehensive error responses:

### Validation Error Example
```json
{
  "status": 400,
  "error": "Validation Failed",
  "message": "Input validation failed for one or more fields",
  "path": "/products",
  "validationErrors": {
    "name": "Product name is required and cannot be empty",
    "price": "Price must be greater than 0.01"
  }
}
```

### Not Found Error Example
```json
{
  "status": 404,
  "error": "Resource Not Found",
  "message": "Product not found with id: 999",
  "path": "/products/999"
}
```

## 🔒 Security

- **Basic Authentication**: All endpoints protected
- **Input Validation**: Prevents malicious data
- **SQL Injection Protection**: JPA/Hibernate parameterized queries
- **Error Information**: Sanitized error responses

## 📈 Monitoring & Logging

- **SQL Logging**: Enabled in development (`spring.jpa.show-sql=true`)
- **Application Logs**: Standard Spring Boot logging
- **Health Check**: Available at `/actuator/health` (if actuator is enabled)

## 🚀 Deployment

### Docker Deployment (Optional)
Create `Dockerfile`:
```dockerfile
FROM openjdk:17-jre-slim
COPY target/productmgmnt-0.0.1-SNAPSHOT.jar app.jar
EXPOSE 8080
ENTRYPOINT ["java", "-jar", "/app.jar"]
```

Build and run:
```bash
docker build -t product-management-api .
docker run -p 8080:8080 product-management-api
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 📞 Support

For support and questions:
- Create an issue in the repository
- Contact: [your-email@example.com]

## 🔄 Version History

- **v1.0.0** - Initial release with full CRUD operations
- **v1.1.0** - Added authentication and validation
- **v1.2.0** - Enhanced error handling and documentation

---

**Happy Coding! 🎉**
