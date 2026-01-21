# SNPseek Datasource

A comprehensive data management system for SNP (Single Nucleotide Polymorphism) data, providing efficient access and integration with genomic databases.

## Overview

SNPseek Datasource is a Java-based application built on the Spring Framework that provides data access layers for managing and querying SNP-related genomic information. The system integrates with CHADO database schemas and provides a robust API for genomic data operations.

## Features

- **Data Access Layer**: Comprehensive DAO (Data Access Object) implementations for genomic data
- **Spring Integration**: Built on Spring Framework for dependency injection and transaction management
- **CHADO Schema Support**: Integration with CHADO database schema for biological data
- **Modular Architecture**: Organized into logical packages for maintainability
- **Configuration Management**: Flexible XML-based Spring configuration

## Project Structure

```
snpseek-datasource/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── org/trri/tric/ds/chado/
│   │   │       ├── dao/           # Data Access Objects
│   │   │       ├── domain/        # Domain models
│   │   │       └── impl/          # DAO implementations
│   │   └── resources/
│   │       ├── META-INF/
│   │       └── *.xml              # Spring configuration files
│   └── test/
├── lib/                           # External libraries
├── pom.xml                        # Maven configuration
└── README.md
```

## Prerequisites

- Java 8 or higher
- Maven 3.x
- Spring Framework 3.2.x
- Database server (PostgreSQL recommended for CHADO)
- Eclipse IDE or similar Java IDE

## Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd snpseek-datasource
   ```

2. **Configure database connection**
   
   Edit the configuration files in `src/resources/`:
   - Update database connection properties
   - Configure data source settings
   - Set appropriate credentials

3. **Build the project**
   ```bash
   mvn clean install
   ```

4. **Run tests**
   ```bash
   mvn test
   ```

## Configuration

### Database Configuration

Update your database connection settings in the Spring configuration files:

```xml
<!-- Example configuration in incDS_prod_crud-dao-context.xml -->
<context:component-scan base-package="org.trri.tric.ds.chado.dao.impl" />
```

### Spring Context

The application uses Spring XML configuration for:
- Component scanning
- Transaction management
- Data source configuration
- DAO bean definitions

## Usage

### Basic DAO Operations

```java
// Example usage of DAO classes
@Autowired
private YourDao yourDao;

// Perform database operations
List<Entity> results = yourDao.findAll();
```

### Integration

Include SNPseek Datasource as a dependency in your project:

```xml
<dependency>
    <groupId>org.trri.tric</groupId>
    <artifactId>snpseek-datasource</artifactId>
    <version>1.0.0</version>
</dependency>
```

## Development

### Setting Up Development Environment

1. Import project into Eclipse:
   - File → Import → Maven → Existing Maven Projects
   - Select the project directory
   - Eclipse will automatically configure the build path

2. Configure application servers if needed

3. Run the application or tests from Eclipse

### Code Structure

- **DAO Layer**: `org.trri.tric.ds.chado.dao`
- **Implementation**: `org.trri.tric.ds.chado.dao.impl`
- **Domain Models**: `org.trri.tric.ds.chado.domain`
- **Configuration**: `src/resources/*.xml`

## Testing

Run the test suite:

```bash
# Run all tests
mvn test

# Run specific test class
mvn test -Dtest=YourTestClass

# Run with coverage
mvn clean test jacoco:report
```

## Troubleshooting

### Common Issues

**Issue: XML Configuration Errors**
- Ensure all Spring schema locations are correctly defined
- Verify namespace declarations in XML files
- Check that external resources can be downloaded

**Issue: Database Connection Failures**
- Verify database credentials
- Check network connectivity
- Ensure database server is running

**Issue: Maven Build Failures**
- Clear Maven cache: `mvn clean`
- Update dependencies: `mvn dependency:resolve`
- Check for conflicting library versions

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -am 'Add new feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Create a Pull Request

### Coding Standards

- Follow Java naming conventions
- Write unit tests for new features
- Document public APIs with Javadoc
- Keep commits atomic and well-described

## License

[Specify your license here - e.g., MIT, Apache 2.0, GPL]

## Contact

- **Project Lead**: [Name]
- **Email**: [email@example.com]
- **Organization**: TRRI/TRIC
- **Repository**: [GitHub/GitLab URL]

## Acknowledgments

- Built with Spring Framework
- Uses CHADO database schema
- [Other acknowledgments]

## Changelog

### Version 1.0.0 (Current)
- Initial release
- Core DAO implementations
- Spring integration
- CHADO schema support

---

**Note**: This is an active development project. Please refer to the issue tracker for known issues and planned features.
