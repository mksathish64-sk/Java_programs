# Using `this` with Instance Variables

## Why is `this` Used?

Consider the following class:

```java
class Student {

    String name;

    Student(String name) {
        this.name = name;
    }
}
```

Here, both the instance variable and the constructor parameter have the same name (`name`).

- `this.name` refers to the **instance variable** of the current object.
- `name` refers to the **constructor parameter** (local variable).

Therefore,

```java
this.name = name;
```

means:

```text
Current object's name = Parameter value
```

---

## What Happens Without `this`?

If we write:

```java
class Student {

    String name;

    Student(String name) {
        name = name;
    }
}
```

both `name`s refer to the constructor parameter because **local variables have higher priority than instance variables**.

This assignment simply assigns the parameter to itself, and the instance variable remains unchanged.

This problem is known as **Variable Shadowing**.

---

## Is `this` Always Required?

No.

If the parameter name is different from the instance variable, `this` is not required.

Example:

```java
class Student {

    String name;

    Student(String studentName) {
        name = studentName;
    }
}
```

Since the names are different, there is no ambiguity.

However, in real-world Java programming, developers usually keep the parameter name and the instance variable name the same for better readability.

In that case, `this` is used to clearly refer to the instance variable.

---

## Key Points

- `this` refers to the current object.
- `this.variable` is used to access the current object's instance variable.
- It is mainly used when a local variable or constructor parameter has the same name as the instance variable.
- Using `this` removes ambiguity and ensures the correct variable is updated.

---

## One-Line Memory

**Use `this.variable` to access the current object's instance variable when a local variable or parameter has the same name.**