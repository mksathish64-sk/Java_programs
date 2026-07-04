# Java Program Structure

A basic Java program consists of the following components:

## 1. Package Declaration (Optional)

A package is used to group related classes together. It helps organize the project and avoids naming conflicts.

```java
package com.example;
```

---

## 2. Import Statements (Optional)

The `import` statement allows a Java program to use classes from other packages without writing their fully qualified names.

```java
import java.util.Scanner;
```

---

## 3. Class Declaration

Every Java program is written inside a class.

```java
public class Student {

}
```

- `public` makes the class accessible from anywhere.
- `Student` is the class name.

---

## 4. Main Method

The `main()` method is the entry point of a Java application. Program execution starts from this method.

```java
public static void main(String[] args) {

}
```

---

## 5. Statements

The executable code of the program is written inside the `main()` method.

```java
System.out.println("Hello World");
```

---

## 6. Comments

Java supports three types of comments:

### Single-line Comment

```java
// This is a single-line comment
```

### Multi-line Comment

```java
/* This is a multi-line comment */
```

### Documentation Comment (Javadoc)

```java
/**
 * This is a Javadoc comment.
 */
```

---

## Example Program

```java
package com.example;

import java.util.Scanner;

public class Student {

    public static void main(String[] args) {
        System.out.println("Hello World");
    }
}
```