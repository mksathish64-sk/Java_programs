# Identifiers and Variable Naming Rules

## What is an Identifier?

An **identifier** is a name given to program elements such as variables, methods, classes, interfaces, packages, and objects.

Identifiers help developers uniquely identify and access program elements within a Java program.

Example:

```java
int age = 20;
```

Here, `age` is an identifier.

---

## Why Do We Need Identifiers?

A program may contain many variables, methods, and classes.

Without identifiers, it would be impossible to refer to or access these program elements.

Identifiers provide meaningful names that make programs easier to write, read, and maintain.

---

## Variable Naming Rules

Java identifiers must follow the following rules:

### Rule 1

An identifier must begin with:

- A letter (`A-Z` or `a-z`)
- An underscore (`_`)
- A dollar sign (`$`)

Valid examples:

```java
int age;
int _count;
int $salary;
```

Invalid example:

```java
int 1age;
```

---

### Rule 2

After the first character, an identifier may contain:

- Letters
- Digits (`0-9`)
- Underscore (`_`)
- Dollar sign (`$`)

Example:

```java
student1
totalMarks2025
employee_salary
```

---

### Rule 3

Spaces are not allowed in identifiers.

Invalid:

```java
int student age;
```

Valid:

```java
int studentAge;
```

---

### Rule 4

Java keywords cannot be used as identifiers.

Invalid:

```java
int class;
int public;
int static;
```

---

### Rule 5

Java is **case-sensitive**.

The following identifiers are different:

```java
age
Age
AGE
```

---

## Special Note About the Dollar Sign (`$`)

The dollar sign (`$`) is a valid character in Java identifiers.

Example:

```java
int $salary = 50000;
```

Although this is accepted by the Java compiler, it is **not recommended** for user-defined identifiers.

According to the Java Language Specification, the dollar sign is primarily intended for compiler-generated code or legacy systems.

Therefore, developers should avoid using `$` in variable names.

---

## Summary

- An identifier is the name of a program element.
- Identifiers help uniquely identify variables, methods, classes, and other program elements.
- An identifier must begin with a letter, underscore (`_`), or dollar sign (`$`).
- Digits are allowed only after the first character.
- Spaces and Java keywords cannot be used as identifiers.
- Java is case-sensitive.
- Although `$` is allowed, it is not recommended for user-defined identifiers.
