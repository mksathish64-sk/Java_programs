# Why Do We Need the `this` Keyword?

A class contains only one copy of each instance method.

When multiple objects are created, all of them share the same method.

For example,

```java
Student s1 = new Student();
Student s2 = new Student();

s1.display();
s2.display();
```

Both `s1` and `s2` use the same `display()` method.

Now consider the following method:

```java
void display() {
    System.out.println(name);
}
```

When the method is executed, the JVM must determine which object's `name` should be accessed.

For example:

- `s1.name`
- `s2.name`

Since the same method is shared by all objects, the JVM needs a way to identify the object that invoked the method.

To solve this problem, the JVM automatically provides a reference to the current object whenever an instance method is executed.

This reference is called **`this`**.

When:

```java
s1.display();
```

the JVM internally associates:

```text
this → s1
```

When:

```java
s2.display();
```

the JVM internally associates:

```text
this → s2
```

Because of this, the same method can correctly access the data of the object that invoked it.

---

## Key Points

- All objects share a single copy of an instance method.
- The JVM must know which object invoked the method.
- The `this` keyword represents the current object.
- `this` allows the shared method to access the correct object's instance variables.

---

## One-Line Memory

**The `this` keyword helps the JVM identify the current object so that a shared method can access the correct object's data.**