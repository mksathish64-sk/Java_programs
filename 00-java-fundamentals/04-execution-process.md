# Java Program Execution Process

## Step 1 - Start the JVM

When the command below is executed,

```bash
java Student
```

the Java Launcher starts a new Java Virtual Machine (JVM).

---

## Representation

        +--------------+                                  +--------------+
        |              |            JRE + JVM             |              |
        |   Bytecode   |  ------------------------------> | Machine code |
        |   (.class)   |            interpreter           |              |
        +--------------+                                  +--------------+

---

## Step 2 - Class Loading

The JVM uses the Class Loader Subsystem to load the required classes.

- Bootstrap Class Loader → Loads core Java classes.
- Platform Class Loader → Loads Java platform libraries.
- Application Class Loader → Loads application classes.

---

## Step 3 - Bytecode Verification

The Bytecode Verifier checks whether the bytecode is valid and safe to execute.

It verifies:

- Bytecode format
- Type safety
- Stack usage
- JVM security rules

---

## Step 4 - Runtime Memory Creation

The JVM creates its runtime memory areas.

- Method Area
- Heap
- Java Stack
- Program Counter (PC) Register
- Native Method Stack

---

## Step 5 - Execution

The Execution Engine starts executing the bytecode.

It uses:

- Interpreter
- Just-In-Time (JIT) Compiler

The JIT Compiler converts frequently executed bytecode into native machine code to improve performance.

---

## Step 6 - Invoke main()

The JVM locates the `main()` method and invokes it.

Since `main()` is declared as `static`, the JVM can call it without creating an object of the class.

---

## Step 7 - Garbage Collection

During program execution, the Garbage Collector automatically removes unreachable objects from the Heap memory.

---

## Step 8 - JVM Shutdown

After the program finishes execution and all non-daemon threads terminate, the JVM shuts down and releases the allocated resources.

## Key Takeaways

- The JVM starts when the `java` command is executed.
- Classes are loaded by the Class Loader Subsystem.
- The Execution Engine executes the bytecode.
- Garbage Collector automatically manages heap memory.