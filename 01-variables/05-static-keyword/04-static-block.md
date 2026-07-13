# Static Block

## What is a Static Block?

A static block is a block of code that executes **automatically when the JVM loads a class**.

It is executed only once, no matter how many objects are created.

---

## Why Do We Use a Static Block?

A static block is used to perform tasks that should happen only once when the class is loaded.

It is commonly used for:

- Initializing static variables
- Loading configuration
- Performing one-time setup

---

## How I Understand It

A static block is like a **one-time startup process** for a class.

The moment the JVM loads a class, it first completes all the static initialization work.

Only after that does the program continue with the remaining execution.

So, a static block is not related to object creation.

It is related to **class loading**.

---

## Example

```java
class Student {

    static {
        System.out.println("Static Block Executed");
    }

    Student() {
        System.out.println("Constructor Executed");
    }

}
```

```java
public class Main {

    public static void main(String[] args) {

        Student s1 = new Student();
        Student s2 = new Student();

    }

}
```

### Output

```
Static Block Executed
Constructor Executed
Constructor Executed
```

---

## Why Does This Happen?

When the first object is created,

```java
Student s1 = new Student();
```

the JVM notices that the `Student` class has not been loaded yet.

So it:

1. Loads the `Student` class.
2. Executes the static block.
3. Creates the object.
4. Executes the constructor.

When the second object is created,

```java
Student s2 = new Student();
```

the class is already loaded.

So the static block is **not executed again**.

Only the constructor runs.

---

## Static Block vs Constructor

| Static Block                      | Constructor                           |
|-----------------------------------|-------------------------------------- |
| Executes when the class is loaded | Executes when an object is created    |
| Runs only once                    | Runs every time an object is created  |    
| Belongs to the class              | Belongs to the object                 |

---

## Class Loading

The JVM does **not** load every class when the program starts.

It loads a class only when it is needed.

For example:

```java
Student s = new Student();
```

or

```java
System.out.println(Student.college);
```

When the class is loaded for the first time, the static block executes.

If the class is never used, it is never loaded, and its static block never runs.

---

## Execution Order

Suppose we have:

```java
class Student {

    static {
        System.out.println("Student Static Block");
    }

}

public class Main {

    static {
        System.out.println("Main Static Block");
    }

    public static void main(String[] args) {

        System.out.println("Hello");

        Student s = new Student();

        System.out.println("Bye");

    }

}
```

### Execution Flow

1. JVM loads the `Main` class.
2. `Main` static block executes.
3. JVM calls the `main()` method.
4. `"Hello"` is printed.
5. `Student` class is used for the first time.
6. JVM loads the `Student` class.
7. `Student` static block executes.
8. Object is created.
9. `"Bye"` is printed.

---

## Important Points

- A static block executes only once.
- It executes when the class is loaded.
- It does not wait for object creation.
- A class is loaded only when the JVM needs it.
- If a class is never used, its static block never executes.

---

## Common Mistakes

### Mistake 1

Thinking the static block executes every time an object is created.

Wrong.

It executes only once.

---

### Mistake 2

Thinking every class is loaded when the program starts.

Wrong.

Only the required classes are loaded.

---

### Mistake 3

Thinking a static block belongs to an object.

Wrong.

It belongs to the class.

---

## One-Line Memory

**A static block executes automatically when the JVM loads a class, and it runs only once during the lifetime of that class.**