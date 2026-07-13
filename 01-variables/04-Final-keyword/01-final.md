# Final Keyword

## Why did Java introduce the `final` keyword?

Before learning `final`, let's think about a normal variable.

```java
int age = 20;

age = 25;
```

This is perfectly valid because a normal variable allows its value to be reassigned.

But Java designers thought:

> "Some values should never change once they are assigned."

### Real-world Examples

- Aadhaar Number
- PAN Number
- Employee ID
- College Registration Number
- PI Value

These values are assigned once and should remain the same throughout the program.

To solve this problem, Java introduced the **`final`** keyword.

---

## Definition

> The `final` keyword is used to restrict modification in Java.

It can be applied to:

- Variable
- Method
- Class

Each one has a different purpose.

| Applied To |          Purpose           |
|------------|----------------------------|
| Variable   | Prevents reassignment      |
| Method     | Prevents method overriding |
| Class      | Prevents inheritance       |

---

## Key Understanding

`final` does **not** have only one meaning.

Its behavior depends on where it is used.

- **`final` Variable** → Cannot be reassigned.
- **`final` Method** → Cannot be overridden.
- **`final` Class** → Cannot be inherited.

---

## Things to Remember

- Java introduced `final` to prevent unwanted changes.
- Normal variables can be assigned multiple times.
- `final` variables can be assigned only once.
- `final` can be used with Variables, Methods and Classes.
- Each usage has a different purpose.

---
