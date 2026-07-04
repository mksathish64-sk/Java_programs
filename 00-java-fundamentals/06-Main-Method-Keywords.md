# Main Method Keywords

The `main()` method is the entry point of every Java application.

```java
public static void main(String[] args)
```

## public

The `main()` method is declared as `public` so that the JVM can access it from outside the class.

---

## static

The `main()` method is declared as `static` because the JVM calls it before creating any object of the class.

---

## void

The `void` return type indicates that the `main()` method does not return any value to the JVM.

---

## main

`main` is the predefined method name recognized by the JVM as the starting point of program execution.

---

## String[] args

`String[] args` is an array of strings used to receive command-line arguments passed to the program.

Example:

```bash
java Student Sathish 20
```

```java
public class Student {
    public static void main(String[] args) {
        System.out.println(args[0]); // Sathish
        System.out.println(args[1]); // 20
    }
}
```

---

## Method Signature

The complete method signature recognized by the JVM is:

```java
public static void main(String[] args)
```

Any change to this signature means the JVM will not recognize it as the program's entry point.