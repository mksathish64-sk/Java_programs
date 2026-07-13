# Static Method

## What is a Static Method?

A static method is a method that belongs to the **class**, not to individual objects.

Just like a static variable, only one copy of a static method exists, and all objects share the same method.

---

## Why do we use a Static Method?

We use a static method when the functionality is common for every object and does not depend on the data of any particular object.

Since the method belongs to the class, we can call it without creating an object.

---

## How I Understand It

Think about a method like:

- `displayCollegeName()`
- `printWelcomeMessage()`
- `showRules()`

These methods do not depend on any particular student.

The same functionality is used for everyone.

Instead of making every object own a separate method, Java keeps one common method and lets everyone use it.

That is why we make it `static`.

---

## Example

```java
class Student {

    static void welcome() {
        System.out.println("Welcome to PSNA");
    }

}
```

Call it like this:

```java
Student.welcome();
```

No object is required.

---

## Can We Call It Using an Object?

Yes.

```java
Student s1 = new Student();

s1.welcome();
```

This compiles successfully.

But internally, the compiler treats it as:

```java
Student.welcome();
```

The object is ignored because the method belongs to the class.

So, although it works, it is **not the recommended way**.

The preferred way is:

```java
Student.welcome();
```

---

## What Can a Static Method Access?

A static method can directly access:

- Static variables
- Static methods

Example:

```java
class Student {

    static String college = "PSNA";

    static void display() {
        System.out.println(college);
    }

}
```

This works because both the variable and the method belong to the class.

---

## What Can't a Static Method Access?

A static method cannot directly access:

- Instance variables
- Instance methods

Example:

```java
class Student {

    String name = "Sathish";

    static void display() {
        System.out.println(name);
    }

}
```

This gives a compile-time error.

---

## Why Does This Error Happen?

An instance variable belongs to an object.

A static method belongs to the class.

When the static method runs, the compiler does not know **which object's** `name` should be used.

There may be many objects, each with a different value.

Because there is no specific object, Java does not allow direct access.

---

## How Can We Access an Instance Variable?

By creating or using an object.

Example:

```java
class Student {

    String name = "Sathish";

    static void display() {

        Student s = new Student();

        System.out.println(s.name);

    }

}
```

Now the compiler knows exactly which object's data is being accessed.

---

## Memory

- A static method belongs to the class.
- Only one copy exists.
- Every object shares the same method.
- It is available when the class is loaded.

---

## Key Points

- A static method belongs to the class.
- No object is required to call it.
- It can directly access only static members.
- It cannot directly access instance members.
- Calling a static method using the class name is the recommended approach.

---

## Common Mistakes

### Mistake 1

Thinking a static method has its own object.

Wrong.

A static method belongs to the class.

---

### Mistake 2

Trying to access an instance variable directly inside a static method.

This results in a compile-time error.

---

### Mistake 3

Always calling a static method using an object.

It works, but it is not the recommended style.

Prefer:

```java
Student.display();
```

instead of

```java
s1.display();
```

---

## One-Line Memory

**A static method belongs to the class, so it can be called without creating an object and can directly access only static members.**