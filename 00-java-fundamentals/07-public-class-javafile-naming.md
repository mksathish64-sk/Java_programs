# Public Class and Java File Naming

## Why Should the Java File Name Match the Public Class Name?

In Java, if a source file contains a **public class**, the file name **must** be the same as the public class name.

Example:

```java
public class Student {

    public static void main(String[] args) {
        System.out.println("Hello");
    }

}
```

The file must be saved as:

```
Student.java
```

If it is saved with a different name, the Java compiler generates a compilation error.

---

## Why Does the Compiler Check the File Name?

The Java compiler converts the source code (`.java`) into bytecode (`.class`).

Before compilation, the compiler verifies that:

- The source file contains only one public class.
- The file name matches the public class name.

This rule helps the compiler identify the correct public class without ambiguity.

If the file name and public class name are different, the compiler stops the compilation process and reports an error.

---

## Why Was This Rule Introduced?

Imagine a project containing hundreds of Java files.

If file names and public class names were unrelated, the compiler would need to search through multiple files to locate a particular public class.

By enforcing the rule:

> **File Name = Public Class Name**

the compiler can immediately locate the required class, making compilation faster and simpler.

---

## Why Do We Use the Class Name as the File Name?

Using the class name as the file name improves readability and project organization.

For example:

```
Student.java
Employee.java
BankAccount.java
```

A developer can easily identify and open the required source file without searching through multiple files.

This makes large projects easier to navigate and maintain.

---

## How Many Public Classes Can a Java File Contain?

A Java source file can contain **only one public class**.

Example:

```java
public class Student {

}

class Employee {

}

class Teacher {

}
```

This is valid because only one class is declared as `public`.

---

## Can a Java File Contain Multiple Classes?

Yes.

A Java file can contain multiple classes, but only one of them can be declared as `public`.

All other classes should use the default (package-private) access modifier.

---

## Summary

- A Java source file can contain multiple classes.
- Only one class can be declared as `public`.
- The file name must match the public class name.
- The compiler checks this rule before compilation.
- This convention helps the compiler locate the correct class and improves project organization.