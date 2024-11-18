
# PetStoreAPI - REST API Automation Framework

This project is a REST API automation testing framework for the **Swagger Petstore API**, specifically focusing on the User module. Built using **RestAssured**, the framework supports comprehensive testing of CRUD operations and offers features like data-driven testing and detailed reporting.

---

## Features
- **Test Cases with Random Data**: Includes tests that generate dynamic data using `Java Faker`.
- **Data-Driven Testing**: Reads test data from Excel files for flexibility and scalability.
- **Rich Logging and Reporting**: Integrated with Log4j2 for logging and ExtentReports for detailed HTML reports.
- **Reusable Utilities**: Modular utilities for data handling, reporting, and test execution.

---

## Framework Structure
```plaintext
PetStoreAPI/
│
├── src/test/java/
│   ├── api.endpoints/         # API endpoint methods
│   │   └── UserEndPoints.java
│   ├── api.payload/           # JSON payload structure for user operations
│   │   └── User.java
│   ├── api.test/              # Test classes
│   │   ├── UserTests.java     # Tests with random fake data
│   │   └── DDTests.java       # Data-driven tests using Excel
│   ├── api.utilities/         # Utility classes for reporting, data, and logging
│       ├── DataProviders.java
│       ├── ExtentReportManager.java
│       └── XLUtility.java
│
├── src/test/resources/
│   ├── log4j2.xml             # Log4j2 configuration
│   └── routes.properties      # API endpoint routes
│
├── testData/
│   └── Userdata.xlsx          # Test data for data-driven tests
│
├── logs/                      # Log files
│   └── automation.log
│
├── reports/                   # ExtentReports
│   ├── Test-Report-<timestamp>.html
│
├── testng.xml                 # TestNG suite configuration
├── pom.xml                    # Maven dependencies and plugins
└── README.md                  # Project documentation
```

---

## Configuration and Test Details

### API Routes
The `routes.properties` file includes the endpoints for CRUD operations:
```properties
post_url=https://petstore.swagger.io/v2/user
get_url=https://petstore.swagger.io/v2/user/{username}
update_url=https://petstore.swagger.io/v2/user/{username}
delete_url=https://petstore.swagger.io/v2/user/{username}
```

### TestNG Suite
The test cases are organized into two main classes:
1. **`UserTests.java`**: Contains test cases using randomly generated test data (via `Java Faker`).
2. **`DDTests.java`**: Contains data-driven test cases, reading input data from the `Userdata.xlsx` file in the `testData` folder.

---

## Prerequisites
1. **JDK**: Version 21 or higher.
2. **Maven**: Version 3.9+.
3. **Excel Data**: Ensure `Userdata.xlsx` is populated with valid test data.
4. **IDE**: IntelliJ IDEA, Eclipse, or similar.

---

## Setup and Execution

### Using Maven
1. Open the terminal and navigate to the project directory.
2. Run:
   ```bash
   mvn clean test
   ```
3. Logs will be saved in the `logs/automation.log` file.
4. HTML test reports will be generated in the `reports/` folder.

### Using TestNG
1. Open the `testng.xml` file in your IDE.
2. Run the suite as a **TestNG Suite**.

---

## Dependencies
The framework utilizes the following major libraries:
- **RestAssured**: For REST API testing.
- **TestNG**: For test execution and reporting.
- **Apache POI**: For handling Excel files in data-driven testing.
- **ExtentReports**: For generating detailed HTML test reports.
- **Log4j2**: For logging.
- **Java Faker**: For generating random test data.

All dependencies are managed in the `pom.xml` file.

---

## Logs and Reports
- **Logs**: Execution logs are stored in the `logs/automation.log` file.
- **Reports**: HTML reports are created in the `reports/` directory, with a timestamp indicating the test execution time.

---

## Future Enhancements
- Extend coverage to include other Swagger Petstore API modules.
- Add schema validation for API responses using JSON schema validation libraries.
- Integrate with CI/CD pipelines for automated test execution.

---

Happy Testing! 🚀
