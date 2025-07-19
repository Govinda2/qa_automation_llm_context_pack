---
description: 'Rest Assured API Test Generation Instructions'
applyTo: '**'
---

## Test Writing Guidelines

### Code Quality Standards

-   **Structure**: Organize tests into logical blocks (Given-When-Then).
-   **Readability**: Use descriptive names for methods and variables.  Keep methods short and focused.
-   **Reusability**:  Create reusable components for common tasks (e.g., authentication, header creation).
-   **Configuration**: Externalize configuration (URLs, API keys) for different environments.
-   **Error Handling**: Implement proper error handling and logging.

### Assertion Best Practices

-   **Specificity**: Use specific assertions to validate the exact response you expect.
-   **Clarity**:  Write assertions that are easy to understand and explain the expected outcome.
-   **Completeness**: Validate all relevant aspects of the response (status code, headers, body).
-   **JSON Path**: Use JSON Path or XML Path for targeted data extraction and validation within the response body.
-   **Schema Validation**: Validate the response against a predefined schema (JSON Schema, XML Schema).
-   **Data Type Validation**: Verify the data types of the response fields.

### Test Structure

-   **Imports**: Include necessary Rest Assured imports.
-   **Organization**: Structure tests using JUnit or TestNG with descriptive names.
-   **Setup/Teardown**: Use `@BeforeEach` / `@BeforeAll` and `@AfterEach` / `@AfterAll` for setup and cleanup.

### Data Management
-   **External Data**: Use external data sources (CSV, JSON, YAML) for parameterized tests.
-   **Data Generation**: Use libraries like Faker to generate realistic test data.

## Test Execution Strategy

1.  **Environment Setup**: Configure base URLs and authentication.
2.  **Initial Run**: Execute tests using Maven/Gradle commands (`mvn test`, `gradle test`).
3.  **Debug Failures**: Inspect request and response logs to identify issues.
4.  **Contract Testing**: Implement contract testing using tools like Pact to ensure compatibility between API provider and consumer.
5.  **Continuous Integration**: Integrate tests into a CI/CD pipeline for automated execution.

## Quality Checklist

Before finalizing tests, ensure:

-   [ ] Tests are grouped logically and follow a clear structure (Given-When-Then).
-   [ ] Assertions are meaningful and reflect user expectations.
-   [ ] Tests follow consistent naming conventions.
-   [ ] Code is properly formatted and commented.
-   [ ] Response data types are validated.
-   [ ] Tests handle different response scenarios (success, failure, edge cases).
-   [ ] Tests are independent and can be executed in any order.
-   [ ] Configuration is externalized for different environments.
-   [ ] Tests include negative test cases to validate error handling.
-   [ ] Tests validate