# Why Java?

## What is Java?

Java is a high-level, object-oriented programming language designed to build secure, reliable, and platform-independent applications.

## Why was Java introduced?

Before Java, languages such as C and C++ generated platform-specific executable files. An executable created for one operating system could not run directly on another operating system because it was compiled into native machine code specific to that platform.

Java solved this limitation by introducing **platform independence**.

## How does Java achieve Platform Independence?

- The Java compiler (`javac`) converts the source code (`.java`) into **bytecode** (`.class`).
- Bytecode is an **intermediate instruction set for the Java Virtual Machine (JVM)** and is platform-independent.
- Every operating system has its own implementation of the JVM.
- The JVM translates the bytecode into native machine code for the underlying operating system at runtime.
- As a result, the same bytecode can run on any operating system that has a compatible JVM installed.

> **Note:** Bytecode is platform-independent, while the JVM is platform-dependent. Together, they make Java platform-independent.

                          **********************
                          * source file(.java) *
                          *        |           *
                          *     (javac)        *
                          *        |           *
                          *  bytecode(.class)  *
                          **********************                         

## Advantages of Java

- Platform Independent (Write Once, Run Anywhere - WORA)
- Object-Oriented Programming (OOP)
- Secure
- Robust
- Automatic Memory Management (Garbage Collection)
- Multithreading Support
- Rich Standard Library

## Key Takeaways

- Java is a high-level, object-oriented programming language.
- Java is platform-independent because it uses bytecode and the JVM.
- Bytecode can run on any operating system with a compatible JVM.
- Java provides portability, security, and strong object-oriented features.