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
