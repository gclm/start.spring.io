```markdown
# start.spring.io Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill provides guidance on contributing to the `start.spring.io` codebase, focusing on its Java implementation. It covers coding conventions, commit patterns, dependency update workflows, and testing practices to ensure consistency and maintainability.

## Coding Conventions

### File Naming
- Use **PascalCase** for file names.
  - Example: `ApplicationConfig.java`, `DependencyManager.java`

### Import Style
- Use **relative imports** within the project.
  - Example:
    ```java
    import com.example.startsite.ApplicationConfig;
    ```

### Export Style
- Use **named exports** for classes and interfaces.
  - Example:
    ```java
    public class DependencyManager {
        // class implementation
    }
    ```

### Commit Messages
- Freeform style, no strict prefixes.
- Average commit message length: ~42 characters.
  - Example:  
    ```
    Update Spring Boot to 2.7.4 in dependencies
    ```

## Workflows

### Dependency Version Update
**Trigger:** When a dependency or library needs to be upgraded to a newer version  
**Command:** `/update-dependency`

1. Edit the relevant configuration or lock file to specify the new version.
   - For application configuration:  
     `start-site/src/main/resources/application.yml`
   - For client dependencies:  
     `start-client/yarn.lock`
2. Commit the change with a message indicating the dependency and new version.
   - Example commit message:  
     ```
     Update Spring Boot to 3.0.0 in application.yml
     ```
3. Optionally, reference a related issue or pull request for tracking.

#### Example
```yaml
# application.yml
spring:
  boot:
    version: 3.0.0
```

```bash
git add start-site/src/main/resources/application.yml
git commit -m "Update Spring Boot to 3.0.0 in application.yml"
git push
```

## Testing Patterns

- **Framework:** Unknown (not detected)
- **File Pattern:** Test files follow the `*.test.*` naming convention.
  - Example: `DependencyManager.test.java`
- Place test files alongside or near the code they test.

## Commands

| Command             | Purpose                                            |
|---------------------|----------------------------------------------------|
| /update-dependency  | Initiate the dependency version update workflow    |
```
