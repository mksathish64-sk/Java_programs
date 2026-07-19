# Why Are Methods Not Stored Inside Every Object?

Before understanding the `this` keyword, it is important to know where methods are stored in memory.

---

## Class

```java
class Student {
    String name;
    int age;

    void display() {
        System.out.println(name);
        System.out.println(age);
    }
}
```

This class contains:

- Two instance variables (`name` and `age`)
- One instance method (`display()`)

---

## What Happens When an Object Is Created?

```java
Student s1 = new Student();
Student s2 = new Student();
```

Two separate objects are created in the Heap.

### Object 1

```text
name
age
```

### Object 2

```text
name
age
```

Each object has its own copy of the instance variables.

For example:

```text
Object 1
---------
name = "Sathish"
age = 20

Object 2
---------
name = "Kumar"
age = 21
```

---

## Are Methods Also Stored Inside Every Object?

No.

Methods are **not** copied into every object.

The `display()` method is stored only **once** in the Method Area when the class is loaded.

```text
Method Area

Student Class
-------------
display()
```

No matter how many objects are created, there is still only one copy of the method.

---

## Why?

The behavior of every object is the same.

For example, the `display()` method always performs the same task:

- Print the name
- Print the age

Only the data is different for each object.

Since the functionality is the same, Java stores only one copy of the method to save memory.

---

## Then How Does `display()` Work for Different Objects?

When we call:

```java
s1.display();
```

the JVM executes the single `display()` method from the Method Area.

Before executing it, the JVM internally knows that the current object is `s1`.

Similarly,

```java
s2.display();
```

the JVM executes the same method again, but this time the current object is `s2`.

This is why the same method can work with different objects.

---

## Summary

- Every object has its own copy of the instance variables.
- Methods are not stored inside every object.
- Only one copy of each method exists in the Method Area.
- The JVM executes the same method for different objects by knowing which object called it.
- This concept is the foundation for understanding the `this` keyword.

---

## One-Line Memory

**Objects store data, while methods are stored only once and shared by all objects of the same class.**