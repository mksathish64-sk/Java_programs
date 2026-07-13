# Final Variable

## Why do we need a `final` Variable?

Let's first look at a normal variable.

```java
int age = 20;

age = 25;
```

This is valid because a normal variable allows multiple assignments.

But some values should never change once they are assigned.

Examples:

- Aadhaar Number
- PAN Number
- Employee ID
- Registration Number
- PI Value

For these kinds of values, Java provides the **`final`** keyword.

---

## How I Understood It

A normal variable allows multiple assignments.

A `final` variable allows only one assignment.

Once a value is assigned, Java will not allow another assignment to that variable.

---

## Definition

> A `final` variable can be assigned only once. Once a value is assigned, it cannot be **reassigned**.

---

## Syntax

```java
final dataType variableName = value;
```

Example:

```java
final int age = 20;
```
---

# Example 1 - Valid

```java
public class Main {

    public static void main(String[] args) {

        final int age = 20;

        System.out.println(age);

    }

}
```

### Output

```text
20
```

### Understanding

This is valid because the value is assigned only once.

---

# Example 2 - Reassignment

```java
public class Main {

    public static void main(String[] args) {

        final int age = 20;

        age = 25;

    }

}
```

### Output

```text
Compile-Time Error

cannot assign a value to final variable 'age'
```

### Understanding

Java does not allow a second assignment to a final variable.

---

# Blank `final` Variable

A final variable can also be declared without assigning a value immediately.

```java
final int age;
```

This is called a **Blank Final Variable**.

It must be assigned exactly once before it is used.

Example:

```java
public class Main {

    public static void main(String[] args) {

        final int age;

        age = 20;

        System.out.println(age);

    }

}
```

### Output

```text
20
```

---

# Reassigning a Blank Final Variable

```java
final int age;

age = 20;

age = 25;
```

### Output

```text
Compile-Time Error
```

### Understanding

Even though it is a blank final variable, once a value is assigned, another assignment is not allowed.

---

# One Important Doubt 

Suppose,

```java
int age;

System.out.println(age);
```

Will this work?

No.

This gives a Compile-Time Error.

Reason:

A local variable must be initialized before it is used.

This rule is **not only for final variables**.

It applies to all local variables.

The same happens with a final variable.

```java
final int age;

System.out.println(age);
```

Compile-Time Error.

Reason:

The variable has not been initialized.

---

# Things to Remember

- A final variable can be assigned only once.
- Reassignment is not allowed.
- Blank final variables are allowed.
- Blank final variables must be assigned before use.
- Local variables must always be initialized before they are used.

---
