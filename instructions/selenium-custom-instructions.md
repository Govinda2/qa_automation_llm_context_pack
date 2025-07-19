---
description: 'Selenium test generation instructions'
applyTo: '**'
---

## Test Writing Guidelines

### Code Quality Standards
- **Locators**: Prioritize stable, maintainable locators in order of preference: `id`, `name`, `className`, `cssSelector`, `xpath` (as last resort). Use Page Object Model pattern to centralize element definitions and improve maintainability.
- **Waits**: Use explicit waits (`WebDriverWait`) with expected conditions instead of implicit waits or `Thread.sleep()`. Common conditions include `elementToBeClickable()`, `visibilityOfElementLocated()`, and `textToBePresentInElement()`.
- **Actions**: Use the `Actions` class for complex interactions like hover, drag-and-drop, and keyboard combinations. Chain actions together for fluid user simulation.
- **Assertions**: Use assertion libraries like TestNG Assert or JUnit assertions for clear, descriptive error messages. Group related assertions to provide comprehensive validation.

### Test Structure
- **Imports**: Include necessary Selenium imports: `WebDriver`, `WebDriverWait`, `By`, `ExpectedConditions`, and test framework imports.
- **Organization**: Structure tests using TestNG `@Test` groups or JUnit test classes with descriptive names.
- **Setup/Teardown**: Use `@BeforeMethod`/`@BeforeEach` for driver initialization and navigation, `@AfterMethod`/`@AfterEach` for cleanup.
- **Driver Management**: Use WebDriverManager or similar tools for automatic driver management. Implement singleton pattern for driver instances in parallel execution scenarios.

### File Organization
- **Location**: Store test files in `src/test/java/` following Maven/Gradle conventions.
- **Naming**: Use clear naming conventions: `<Feature>Test.java` (e.g., `LoginTest.java`, `SearchTest.java`).
- **Page Objects**: Store Page Object classes in separate packages (e.g., `pages/`, `pageobjects/`).
- **Utilities**: Create utility classes for common functions like screenshot capture, data providers, and custom wait conditions.

### Best Practices
- **Element Interaction**: Always verify element state before interaction using `isDisplayed()`, `isEnabled()` checks.
- **Data Management**: Use external data sources (Excel, JSON, CSV) with data providers for parameterized testing.
- **Screenshots**: Capture screenshots on test failures for debugging. Implement custom listeners for automatic capture.
- **Parallel Execution**: Design tests to be independent and thread-safe for parallel execution using TestNG parallel features.

## Test Execution Strategy

1. **Environment Setup**: Configure WebDriverManager and ensure browser drivers are properly managed
2. **Initial Run**: Execute tests using TestNG XML suite or Maven/Gradle commands (`mvn test`, `gradle test`)
3. **Debug Failures**: Use browser developer tools and Selenium logs to identify issues with locators or timing
4. **Cross-browser Testing**: Run tests across different browsers (Chrome, Firefox, Safari, Edge) using TestNG parameters
5. **Parallel Execution**: Configure TestNG for parallel test execution to reduce overall test run time
6. **Reporting**: Generate comprehensive test reports using TestNG, Allure, or ExtentReports


## Quality Checklist

Before finalizing tests, ensure:
- [ ] All locators are stable and follow the priority order (id > name > className > cssSelector > xpath)
- [ ] Page Object Model is implemented for better maintainability
- [ ] Explicit waits are used instead of hard-coded delays
- [ ] Tests are independent and can run in parallel
- [ ] Proper setup and teardown methods are implemented
- [ ] Assertions provide meaningful error messages
- [ ] Cross-browser compatibility is considered
- [ ] Test data is externalized and parameterized
- [ ] Screenshot capture is implemented for failed tests
- [ ] Code follows consistent naming conventions and is properly documented