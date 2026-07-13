# Final Method

## Why do we need a `final` Method?

Normally, when a class is inherited, the child class can override the parent's methods.

Example:

```java
class Animal {

    void sound() {
        System.out.println("Animal Sound");
    }

}

class Dog extends Animal {

    @Override
    void sound() {
        System.out.println("Bark");
    }

}
```

This is called **Method Overriding**.

But what if a method's behavior should never be changed?

For that, Java provides the **`final`** keyword.

---

## How I Understood It

A `final` method is still inherited by the child class.

But the child class **cannot override it**.

So,

- Functionality is shared.
- Behavior remains the same.

---

## Definition

> A `final` method can be inherited, but it cannot be overridden.

---

## Syntax

```java
final returnType methodName() {

}
```

Example:

```java
final void display() {

}
```
---

# Example

```java
class Animal {

    final void sound() {
        System.out.println("Animal Sound");
    }

}

class Dog extends Animal {

}
```

```java
Dog d = new Dog();
d.sound();
```

### Output

```text
Animal Sound
```

### Understanding

The child class inherits the method normally.

There is no restriction on calling the method.

The only restriction is overriding.

---

# Example - Overriding a Final Method

```java
class Animal {

    final void sound() {
        System.out.println("Animal Sound");
    }

}

class Dog extends Animal {

    @Override
    void sound() {
        System.out.println("Bark");
    }

}
```

### Output

```text
Compile-Time Error

Cannot override the final method.
```

---

# One Important Understanding

At first, I thought:

> "If the method is final, can the child class still use it?"

The answer is **Yes.**

Inheritance simply shares the functionality.

It does **not** mean the child class is changing the method.

So,

- The child class can call the method.
- The child class cannot redefine (override) the method.

---

# Real-World Idea

Suppose a banking application has an authentication method.

Every account should follow the same authentication process.

Developers should not be able to change that logic.

In such cases, the method can be declared as `final`.

---

# Things to Remember

- A final method can be inherited.
- A final method cannot be overridden.
- Child classes can call the method normally.
- `final` protects the method's behavior from being changed.

---
