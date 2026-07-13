# Final Class

## Why do we need a `final` Class?

We already learned that a `final` method cannot be overridden.

So, a question came to my mind:

> "If we can simply make every important method `final`, why do we need to make the entire class `final`?"
---

## How I Understood It

Suppose we have a class.

```java
class Bank {

    final void authenticate() {
        System.out.println("Authentication Successful");
    }

    void displayBalance() {
        System.out.println("Balance: ₹10,000");
    }

}
```

Here,

- `authenticate()` is `final`.
- `displayBalance()` is **not** `final`.

A child class can still override `displayBalance()`.

```java
class SBI extends Bank {

    @Override
    void displayBalance() {
        System.out.println("Fake Balance");
    }

}
```

This changes the behavior of the original class.

---

## Another Doubt

Then I thought,

> "Why don't we simply make `displayBalance()` also `final`?"

Yes, we can.

In fact,

A class can have:

- One final method.
- Two final methods.
- Ten final methods.
- Even all methods can be `final`.

There is no restriction.

---

## Then why make the entire class `final`?

Imagine a class has 50 methods.

The developer has to remember to declare every important method as `final`.

What if one method is forgotten?

That method can be overridden.

This creates a risk.

Instead,

Java allows us to make the **entire class** `final`.

Once the class itself is `final`,

Nobody can inherit it.

If nobody can inherit it,

Nobody can override any method.

Everything inside the class automatically becomes safe from overriding.

---

## Definition

> A `final` class cannot be inherited.

---

## Syntax

```java
final class ClassName {

}
```

---

# Example

```java
final class Bank {

}
```

Creating an object is perfectly valid.

```java
Bank b = new Bank();
```

---

# Example

```java
final class Bank {

}

class SBI extends Bank {

}
```

### Output

```text
Compile-Time Error

Cannot inherit from final class 'Bank'
```

---

# Real-World Example - `String` Class

One of the best examples is the `String` class.

```java
public final class String
```

Why?

Because Java wants every program to see the same behavior of a `String`.

If developers were allowed to inherit and change the behavior of `String`,

Different programs could behave differently.

That would make Java unreliable.

Making `String` final ensures that its behavior remains consistent and reliable.

---

# Things to Remember

- A final class cannot be inherited.
- If a class cannot be inherited, none of its methods can be overridden.
- A class can contain any number of final methods.
- Declaring the entire class as final is safer when the complete behavior should remain unchanged.
- `String` is one of the best examples of a final class.

---
