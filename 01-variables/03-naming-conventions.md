## Naming Conventions

Variable naming rules and naming conventions are different.

- **Naming Rules** are enforced by the Java compiler. If a rule is violated, the program will not compile.
- **Naming Conventions** are recommended coding standards followed by Java developers. Violating a naming convention does not produce a compilation error, but following it improves code readability and maintainability.

### Variable Naming Convention

Variables should be written using **camelCase**.

In camelCase:

- The first word starts with a lowercase letter.
- Every subsequent word starts with an uppercase letter.
- No spaces or special characters are used.

Examples:

```java
studentAge
totalMarks
employeeSalary
isEligible
accountBalance
```

Incorrect examples:

```java
StudentAge
student_age
studentage
STUDENTAGE
```

Although some of these identifiers are valid according to Java's naming rules, they do not follow the standard Java naming convention.

### Class Naming Convention

Class names should follow **PascalCase**.

In PascalCase:

- Every word starts with an uppercase letter.

Examples:

```java
Student
EmployeeDetails
BankAccount
```

### Constant Naming Convention

Constants are generally written using **UPPER_CASE** with underscores separating words.

Examples:

```java
MAX_SIZE
PI
MIN_VALUE
DEFAULT_TIMEOUT
```

### Why Do We Follow Naming Conventions?

Following naming conventions makes code:

- Easier to read
- Easier to understand
- Easier to maintain
- Consistent across different Java projects

Although naming conventions are not enforced by the compiler, they are widely followed by Java developers and organizations.