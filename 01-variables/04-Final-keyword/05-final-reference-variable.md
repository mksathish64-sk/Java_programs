# Final Reference Variable

## Why did we use the word **"reassigned"** instead of **"modified"**?

While learning `final` variables, we always said:

> **A final variable cannot be reassigned.**

We intentionally did **not** say:

> **A final variable cannot be modified.**

At first, this looked like a small difference.

But after understanding **Reference Variables**, the reason became clear.

---

## First, let's understand the difference.

Suppose we create an object.

```java
Student s = new Student();
```

Here,

- `s` is **not** the object.
- `s` is a **reference variable**.

The actual object is created in **Heap Memory**.

The reference variable is stored in **Stack Memory**.

The reference variable simply stores the address (reference) of the object.

---

## Memory Understanding

```
Stack Memory                 Heap Memory

+------+                +------------------+
|  s   | -------------> |   Student Object |
+------+                +------------------+
```

- `s` → Reference Variable
- `Student Object` → Actual Object

---

## Now let's make it `final`

```java
final Student s = new Student();
```

Here,

Java protects the **reference variable**.

It does **not** protect the object.

---

## Reassigning the Reference

```java
final Student s = new Student();

s = new Student();
```

### Output

```text
Compile-Time Error
```

### Understanding

Initially, `s` points to one object.

When we write:

```java
s = new Student();
```

Java has to create another object and make `s` point to that new object.

Since `s` is declared as `final`, changing its reference is not allowed.

So this is called **Reassignment**.

---

## Modifying the Object

Suppose the `Student` class contains:

```java
class Student {

    String name;

}
```

Now,

```java
final Student s = new Student();

s.name = "Sathish";
```

### Output

```text
No Error
```

### Understanding

Here,

We are **not changing the reference variable**.

`s` still points to the same object.

We are only changing the data stored inside that object.

So Java allows it.

---

## The Main Understanding

`final` protects the **reference variable**.

It does **not** protect the object.

Because of this,

- Object data can be modified.
-  Reference cannot be changed.

---

## Things to Remember

- A reference variable stores the address of an object.
- The reference variable is stored in Stack Memory.
- The object is stored in Heap Memory.
- `final` protects the reference variable.
- The object itself is still mutable unless designed otherwise.
- This is why we always say:

