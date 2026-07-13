# Static Variable

## What is a Static Variable?

A static variable is a variable that belongs to the **class**, not to individual objects.

Only one copy of the variable is created when the JVM loads the class, and all objects share that same copy.

---

## Why do we use a Static Variable?

We use a static variable when the value is common for every object.

If every object stores the same value separately, memory is wasted.

Instead of creating multiple copies, Java creates only one shared copy.

---

## How I Understand It

Imagine a `Student` class.

Every student has:

- Name
- Roll Number
- Age

These values are different for every student, so they should not be static.

But every student studies in the same college.

If the college name is stored inside every object, the same value is repeated again and again.

Instead, we make the college name `static`.

Now Java creates only one copy of the college name, and every student object uses that same copy.

---

## Example

```java
class Student {

    String name;
    static String college = "PSNA";

}
```

```java
Student s1 = new Student();
Student s2 = new Student();

s1.name = "Sathish";
s2.name = "Kumar";
```

Memory:

```
s1
 ├── name = "Sathish"
 │
s2
 ├── name = "Kumar"

Method Area
 └── college = "PSNA"
```

Both `s1` and `s2` use the same `college` variable.

---

## Accessing a Static Variable

The best way is to use the class name.

```java
Student.college
```

It can also be accessed using an object.

```java
s1.college
```

This works, but it is not recommended because the variable belongs to the class, not to the object.

Using the class name makes the code easier to understand.

---

## When is a Static Variable Created?

A static variable is created when the JVM loads the class.

It is created before any object is created.

This is why we can access it without creating an object.

Example:

```java
System.out.println(Student.college);
```

No object is needed.

---

## Memory

- Static variables are stored only once.
- They are created when the class is loaded.
- Every object shares the same variable.

Instance variables are different.

Every object gets its own copy of an instance variable.

---

## Key Points

- A static variable belongs to the class.
- Only one copy exists.
- Every object shares the same copy.
- It is created when the class is loaded.
- It can be accessed using the class name.
- Using the class name is the recommended approach.

---

## Common Mistakes

### Mistake 1

Thinking every object has its own static variable.

Wrong.

There is only one shared copy.

---

### Mistake 2

Accessing a static variable using an object everywhere.

It works, but it is not the recommended way.

Always prefer:

```java
Student.college
```

instead of

```java
s1.college
```

---

## One-Line Memory

**A static variable belongs to the class. Only one copy is created, and all objects share that same copy.**