# `this()` Constructor Call

## What is `this()`?

`this()` is used to call another constructor of the **same class**.

It helps one constructor reuse the code of another constructor instead of writing the same code multiple times.

---

## Why Do We Need `this()`?

Consider the following class:

```java
class Student {

    String college;
    String name;
    int age;

    Student() {
        college = "PSNA";
    }

    Student(String name) {
        college = "PSNA";
        this.name = name;
    }

    Student(String name, int age) {
        college = "PSNA";
        this.name = name;
        this.age = age;
    }
}
```

Notice that the statement

```java
college = "PSNA";
```

is repeated in every constructor.

If the college name changes in the future, we must update every constructor.

This leads to **code duplication**.

---

## Solution

Instead of repeating the same code, we can place the common initialization inside one constructor and call it from other constructors using `this()`.

Example:

```java
class Student {

    Student() {
        System.out.println("Default Constructor");
    }

    Student(String name) {
        this();
        System.out.println("Parameterized Constructor");
    }
}
```

---

## Execution Flow

```java
Student s1 = new Student("Sathish");
```

Execution order:

1. `Student(String name)` constructor is called.
2. The first statement is `this();`.
3. `this()` calls the `Student()` constructor.
4. After the `Student()` constructor finishes, control returns to the `Student(String name)` constructor.
5. The remaining statements are executed.

Output:

```text
Default Constructor
Parameterized Constructor
```

---

# How Does `this()` Decide Which Constructor to Call?

`this()` does **not** choose a constructor automatically.

The constructor is selected based on the arguments provided.

Example:

```java
this();
```

Calls:

```java
Student()
```

Example:

```java
this("Sathish");
```

Calls:

```java
Student(String name)
```

Example:

```java
this(20);
```

Calls:

```java
Student(int age)
```

The constructor selection follows the normal **constructor overloading** rules.

---

# Rules of `this()`

### Rule 1

`this()` can only be used inside a constructor.

It cannot be used inside a method.

---

### Rule 2

`this()` must always be the **first statement** inside a constructor.

Correct:

```java
Student(String name) {
    this();
}
```

Incorrect:

```java
Student(String name) {
    System.out.println(name);
    this();
}
```

This results in a **compile-time error**.

---

## Why Must `this()` Be the First Statement?

When a constructor calls another constructor, Java first completes the constructor chaining.

Only after the called constructor finishes executing does the control return to the current constructor.

This ensures that object initialization happens in the correct order.

Because of this rule, Java requires `this()` to be the first statement inside a constructor.

---

# Constructor Chaining

When one constructor calls another constructor, and that constructor calls another constructor, the constructors execute one after another in a sequence.

This process is called **Constructor Chaining**.

Example:

```java
class Student {

    Student() {
        System.out.println("A");
    }

    Student(String name) {
        this();
        System.out.println("B");
    }

    Student(String name, int age) {
        this(name);
        System.out.println("C");
    }
}
```

Execution:

```java
new Student("Sathish", 20);
```

Flow:

```text
Student(String, int)
        ↓
Student(String)
        ↓
Student()
```

Output:

```text
A
B
C
```

Each constructor completes its execution and then returns control to the constructor that called it.

---

# Benefits of Constructor Chaining

- Avoids code duplication.
- Reuses constructor logic.
- Makes the code easier to maintain.
- Improves code readability.

---

# Key Points

- `this()` is used to call another constructor of the same class.
- The constructor is selected based on the arguments passed.
- `this()` can only be used inside a constructor.
- `this()` must always be the first statement.
- Calling constructors one after another is called **Constructor Chaining**.

---

# One-Line Memory

**`this()` is used to call another constructor of the same class, allowing constructors to reuse code through constructor chaining.**