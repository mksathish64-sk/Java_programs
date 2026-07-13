# Why is the `main()` Method Static?

## Introduction

Every Java program starts from the `main()` method.

But have you ever wondered why the `main()` method is declared as `static`?

The reason becomes simple once we understand how the JVM starts a Java program.

---

## How a Java Program Starts

When we run a Java program, the JVM first looks for the following method:

```java
public static void main(String[] args)
```

This method is called the **entry point** of a Java program.

The JVM directly calls this method to start execution.

---

## What If `main()` Was Not Static?

Suppose the `main()` method was written like this:

```java
public void main(String[] args) {

    System.out.println("Hello");

}
```

Now the JVM cannot call it directly.

Since it is an instance method, an object is required.

The JVM would first need to do something like this:

```java
Main m = new Main();
m.main(args);
```

But this creates an unnecessary problem.

Before starting the program, the JVM would first have to create an object.

Java avoids this extra step.

So, the `main()` method is declared as `static`.

---

## How I Understand It

The `main()` method is the starting point of the program.

Before any object exists, the JVM should be able to start the program.

Since a static method belongs to the class, the JVM can call it directly without creating an object.

That is why `main()` is static.

---

## Execution Flow

Suppose we have:

```java
public class Main {

    static {

        System.out.println("Static Block");

    }

    public static void main(String[] args) {

        System.out.println("Main Method");

    }

}
```

### Execution

1. JVM loads the `Main` class.
2. The static block executes.
3. The JVM calls the `main()` method.
4. The remaining code inside `main()` executes.

### Output

```
Static Block
Main Method
```

---

## Important Point

The JVM does **not** create an object of the `Main` class to call the `main()` method.

It simply calls:

```java
Main.main(args);
```

This is possible only because the method is static.

---

## Key Points

- `main()` is the entry point of every Java program.
- The JVM directly calls the `main()` method.
- Since it is static, no object is required.
- If it were not static, the JVM would first need to create an object.
- Making `main()` static makes program execution simple and efficient.

---

## Common Mistake

Some people think `main()` is static because it is the first method that executes.

This is not the real reason.

The real reason is that the JVM must be able to call it **without creating an object**.

---

## One-Line Memory

**The `main()` method is static so that the JVM can call it directly without creating an object.**