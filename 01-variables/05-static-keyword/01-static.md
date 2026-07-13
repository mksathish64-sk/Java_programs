# Static Keyword

## What is `static`?

The `static` keyword is used to make a member belong to the **class** instead of individual **objects**.

Normally, when we create objects, every object gets its own copy of the variables and methods it needs.

But sometimes, creating separate copies is unnecessary because the value or functionality is common for every object.

In that case, we use the `static` keyword.

---

## Why do we use `static`?

We use `static` when something should be common for all objects.

Instead of creating the same thing again and again for every object, Java creates only one copy and lets all objects share it.

This saves memory and avoids unnecessary duplication.

---

## How I Understand It

Think of a college.

Every student has their own:

- Name
- Roll Number
- Age

These are different for every student, so every object needs its own copy.

But the college name is the same for everyone.

Creating the same college name inside every object is unnecessary.

Instead, Java creates one common copy and every object uses that same copy.

That is exactly what `static` does.

---

## Memory

When the JVM loads a class,

- Static members are created only once.
- They belong to the class.
- They are available even before any object is created.

Instance members are created only when an object is created.

---

## What can be declared as `static`?

Java allows us to declare:

- Static variables
- Static methods
- Static blocks
---

## Key Points

- `static` belongs to the class, not to individual objects.
- Only one copy is created.
- All objects share that same copy.
- Static members are created when the class is loaded by the JVM.
- Objects are not required to create static members.

---

>note: A static member is shared by every object because it belongs to the class.

---

## One-Line Memory

**The `static` keyword is used when a variable or method should belong to the class and be shared by all objects instead of creating separate copies for every object.**