---
description: 'Test automation code documentation guidelines for Java. Works with GitHub Copilot, Cursor, and other AI coding assistants.'
applyTo: '**'
---

# Test Automation Documentation Standards

## Target Audience
• **QA Engineers, SDETs, and Automation Specialists** - Test framework development, CI/CD integration, and quality assurance workflows

## Core Philosophy
**Write self-documenting test code. Add documentation only when it provides genuine value for test maintenance and understanding.**

## Java Documentation Requirements

### Required Documentation
- **Test classes** - Document test suite purpose and scope
- **Page Object classes** - Document page functionality and usage
- **Utility methods** - Document complex test logic and business rules
- **Configuration classes** - Document setup and environment dependencies

### Javadoc Standards

**Test Method Documentation**
```java
/**
 * Validates user login workflow with valid credentials.
 * 
 * @param username Valid test user account
 * @param password Corresponding password
 * @throws TimeoutException if page load exceeds expected time
 */
@Test
@ParameterizedTest
public void validateSuccessfulLogin(String username, String password) {
    // Test implementation
}
```

**Page Object Documentation**
```java
/**
 * Login page object for user authentication workflow.
 * 
 * @since 1.0
 * @author QA Team
 */
public class LoginPage {
    
    /**
     * Performs login with retry logic for service instability.
     * 
     * @param credentials User login details
     * @return true if login successful, false otherwise
     * @throws ElementNotFoundException if login form not found
     */
    public boolean login(UserCredentials credentials) {
        // Implementation
    }
}
```

**Utility Class Documentation**
```java
/**
 * Test data generation utilities for automation suites.
 * 
 * @version 2.1
 * @since 1.0
 */
public class TestDataGenerator {
    
    /**
     * Generates unique test user data to prevent conflicts.
     * 
     * @param userType Type of user profile needed
     * @return {@code TestUser} with generated data
     * @see TestUser
     */
    public static TestUser generateUser(UserType userType) {
        // Implementation
    }
}
```

### Documentation Guidelines

**Essential Tags**
- `@param` - Method parameters (start lowercase, no period)
- `@return` - Return value description
- `@throws` - Exceptions that may be thrown
- `@since` - Version when feature was added
- `@see` - References to related classes/methods

**Code Examples**
- Use `{@code}` for inline code: `{@code driver.findElement()}`
- Use code blocks for examples:
```java
/**
 * <pre>{@code
 * LoginPage loginPage = new LoginPage(driver);
 * boolean success = loginPage.login(testCredentials);
 * }</pre>
 */
```

**Test-Specific Tags**
```java
/**
 * @apiNote Requires test database to be running
 * @implNote Uses Selenium WebDriver for browser automation
 * @deprecated Use {@link #loginWithOAuth()} instead - removal in v3.0
 */
```

## Documentation Decision Framework

Before adding Javadoc, ask:
1. **Is the method name and signature self-explanatory?** → Minimal documentation needed
2. **Does this explain test strategy or business logic?** → Good documentation
3. **Will this help with test maintenance?** → Good documentation
4. **Is this a public API for other test classes?** → Required documentation

## Quality Standards

Ensure documentation:
- [ ] First sentence is concise summary ending with period
- [ ] Parameters described clearly without obvious details
- [ ] Return values explained when not obvious
- [ ] Exceptions documented with scenarios when thrown
- [ ] Uses proper grammar and professional language
- [ ] Remains accurate as code evolves

## Summary

**Focus on documenting test strategy, complex business logic, and APIs used by other automation engineers. Keep documentation concise and valuable for test suite