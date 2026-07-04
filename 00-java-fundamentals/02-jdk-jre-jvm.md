# JDK, JRE and JVM

## What is JDK?

JDK (Java Development Kit) is a software development kit used to develop Java applications.

It includes:

- Java Compiler (`javac`)
- Java Runtime Environment (JRE)
- Debugging tools
- Development utilities

The Java compiler converts the source code (`.java`) into bytecode (`.class`).

---

## What is JRE?

JRE (Java Runtime Environment) provides everything required to run Java applications.

It contains:

- Java Virtual Machine (JVM)
- Java Standard Libraries
- Runtime support files

JRE provides the environment required for executing Java programs.

---

## What is JVM?

JVM (Java Virtual Machine) is responsible for executing Java bytecode.

Its responsibilities include:

- Loading classes
- Verifying bytecode
- Managing memory
- Executing bytecode
- Garbage Collection

The Execution Engine uses an Interpreter and a Just-In-Time (JIT) Compiler to execute bytecode efficiently.

---

## Relationship

                                +-------------------------------------------+
                                |                   JDK                     |
                                |            --> javac(compiler)            |
                                |            --> debugging tools            |
                                |  +-------------------------------------+  |
                                |  |                 JRE                 |  |
                                |  |        --> Standard Libraries       |  |
                                |  |        --> Runtime files            |  |
                                |  |  +-------------------------------+  |  |
                                |  |  |              JVM              |  |  |
                                |  |  |                               |  |  |
                                |  |  |       --> interpreter         |  |  |
                                |  |  |       --> JIT                 |  |  |
                                |  |  |                               |  |  |
                                |  |  |                               |  |  |
                                |  |  +-------------------------------+  |  |
                                |  +-------------------------------------+  |
                                +-------------------------------------------+
---

## Can JVM work without JRE?

No.

The JVM depends on the runtime libraries and supporting files provided by the JRE.

---

## Can JRE work without JVM?

No.

The JVM is an essential part of the JRE. Without the JVM, Java bytecode cannot be executed.

---

## Can we compile Java programs using only JRE?

No.

Compilation requires the Java compiler (`javac`), which is available only in the JDK.

---

## Why are JDK, JRE, and JVM separated?

Java separates these components because different users have different requirements.

- Developers need the JDK to write, compile, debug, and run Java programs.
- End users only need the JRE to run Java applications.
- The JVM focuses only on executing bytecode.

This modular design improves maintainability, security, and reduces unnecessary software installation.

## Key Takeaways

- JDK is used to develop Java applications.
- JRE provides the runtime environment.
- JVM executes Java bytecode.
- JDK includes the JRE, and the JRE includes the JVM.