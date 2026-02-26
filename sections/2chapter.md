# Chapter Notes – Introducing Objects in Java (TIJ pp. 23–89)

---

# Part 1: Foundations of Object-Oriented Programming

## Section Goal

Introduce objects in Java and understand core OOP principles.

---

## 1. Five Characteristics of Object-Oriented Programming

Here’s what you really need to remember:

1. **Everything is an object**
   Objects combine data and behavior.

2. **Programs are collections of objects**
   Objects interact by sending messages (method calls).

3. **Each object has its own memory**
   State is stored in fields (instance variables).

4. **Every object has a type**
   Defined by its class.

5. **All objects of a type share behavior**
   Defined by the class’s methods.

---

## 2. Controlling Access to Members

### Why control access?

Two main reasons:

1. **Protect integrity**
   Prevent invalid state changes.
2. **Encapsulation**
   Hide implementation details; expose only what’s necessary.

### How Java implements it

Using **access modifiers**:

- `private`
- `protected`
- package-private (default)
- `public`

---

## 3. Two Ways to Reuse Classes

1. **Composition**
   - Build new classes using objects of existing classes.
   - “Has-a” relationship.

2. **Inheritance**
   - Extend an existing class.
   - “Is-a” relationship.

Composition is generally preferred for flexibility.

---

# Part 2: Polymorphism and Late Binding

## How Late Binding Enables Upcasting and Polymorphism

### Upcasting

Treating a derived object as its base type.

```java
Shape s = new Circle();
```

### Late Binding (Dynamic Binding)

Method calls are resolved at runtime, not compile time.

**Why it matters:**

- Base reference (`Shape`) can call overridden methods.
- The actual method executed depends on the real object (`Circle`).

This enables **polymorphism** — one interface, multiple implementations.

---

# Part 3: Containers, Generics, and Memory

## 1. What is a Container?

A **container** stores and manages objects (e.g., lists, sets).

### Advantage:

- Automatically manages collections.
- Provides reusable data structures.

---

## 2. Parameterized Types (Generics)

Example:

```java
ArrayList<String> list = new ArrayList<>();
```

### What they do:

- Enforce type safety at compile time.
- Eliminate the need for **downcasting**.

Without generics:

```java
String s = (String) list.get(0);
```

With generics:

```java
String s = list.get(0);
```

No cast needed → fewer runtime errors.

---

## 3. Where Are Objects Created?

Objects are created on the **heap**.

References (handles) may be stored:

- On the stack
- As fields inside other objects

---

# Part 4: Exceptions and Threads

## 1. Function of Exception Handling

Purpose:

- Handle runtime errors gracefully.
- Separate normal logic from error-handling logic.

Java reinforces consistency by:

- Requiring checked exceptions to be handled or declared.

---

## 2. Threads

### Single-Processor

- Time-sliced execution.
- Creates illusion of parallelism.

### Multi-Processor

- True parallel execution.
- Improves performance and responsiveness.

---

# Part 5: Java and the Web

## 1. Primary Idea of Client/Server

- **Client** requests services.
- **Server** provides services.

---

## 2. Web Serving → Client-Side Programming

Originally:

- Server did all work.
- Browser only displayed results.

Demand for:

- Interactive pages
- Reduced server load

→ Led to client-side execution.

---

## 3. CGI Programming

**Common Gateway Interface**

- Server runs external programs per request.

### Major Shortcoming:

- Expensive: new process per request.
- Poor scalability.

---

## 4. Why Client-Side Programming Is Efficient

- Reduces server load.
- Reduces network traffic.
- Improves responsiveness.

---

## 5. Plugin

A downloadable module that extends browser functionality.

---

## 6. Scripting Language

Interpreted language embedded in web pages (e.g., JavaScript).

---

## 7. Scripting vs Java for Web

| Scripting         | Java                   |
| ----------------- | ---------------------- |
| Loosely typed     | Strongly typed         |
| Lightweight       | More robust            |
| Quick development | More scalable          |
| Less structure    | Better maintainability |

Java better for large, complex systems.

---

## 8. Intranet vs Internet Programming

- **Intranet**: Controlled environment, known users.
- **Internet**: Security, scalability, unpredictability are major concerns.

---

## 9. Java in Server-Side Programming

Java:

- Runs on server
- Handles business logic
- Manages databases
- Scales well
- Strong security model

---

# Part 6: Objects and Memory Model

## 1. Object vs Handle

- **Object**: Actual data in heap.
- **Handle (reference)**: Pointer to object.

```java
String s;   // handle
s = new String("Hi");  // object
```

---

## 2. Java Memory Areas

### Registers

- Fastest.
- Not directly accessible.

### Stack

- Stores primitives.
- Stores object references.
- Method call frames.

### Heap

- Stores all objects.

### Constant Storage

- String literals.
- Static final values.

### Non-RAM Storage

- Files.
- Persistent data.

---

## 3. Nine Primitive Types

1. boolean
2. char
3. byte
4. short
5. int
6. long
7. float
8. double
9. void

---

## 4. High-Precision Number Classes

- `BigInteger`
- `BigDecimal`

Used for arbitrary precision arithmetic.

---

## 5. Scope Differences

### Primitives

- Stored directly.
- Disappear when scope ends.

### Objects

- Reference disappears at scope end.
- Object remains until garbage collected.

---

# Part 7: Classes, Fields, and Methods

## 1. Definitions

- **Class**: Blueprint.
- **Field**: Data member.
- **Method**: Behavior.

---

## 2. Default Values

### Class Members

- Automatically initialized.

### Local Variables

- Not initialized.
- Must be explicitly assigned.

---

## 3. Fundamental Parts of a Method

1. Access modifier
2. Return type
3. Method name
4. Parameter list
5. Method body
6. Return statement (if needed)

---

# Part 8: Packages, Import, Static

## 1. Naming Convention for Public Libraries

Reverse domain name:

```
com.company.project
```

Ensures uniqueness.

---

## 2. Purpose of `import`

Allows use of classes without fully qualified names.

---

## 3. Functions of `static`

Static members:

- Belong to class, not object.
- Shared across all instances.

Used for:

- Utility methods
- Constants
- Entry point (`main`)

---

# Part 9: HelloDate.java Analysis

## How It Prints the Date

- Creates a `Date` object.
- Uses `System.out.println()`.
- Automatically calls `toString()` on the object.

---

## Explain:

### `public static void main(String[] args)`

- `public` → Accessible to JVM.
- `static` → No object required.
- `void` → Returns nothing.
- `String[] args` → Command-line arguments.

### `public static void main(String[]) {`

Older shorthand syntax. Same meaning.

---

## Why Is main Static?

JVM must call it **without creating an object**.

---

# Activity

Compile and run:

```
javac HelloDate.java
java HelloDate
```

Observe:

- Date object created.
- Printed via `println()`.

---

# Part 10: Standard Coding Style

## Java Coding Style

### Classes

- PascalCase
- One public class per file.
- File name matches class name.

### Methods & Variables

- camelCase.

### Constants

- ALL_CAPS_WITH_UNDERSCORES.

### Braces

- Opening brace on same line.

Example:

```java
public class MyClass {
    public void myMethod() {
    }
}
```

---

# Exercise 10 (p. 90)

(Conceptual Summary)

Typically involves:

- Writing a simple class
- Using fields and methods
- Compiling and executing

Key skills tested:

- Class structure
- main method
- Object creation
- Method invocation

---

# Final Takeaways

There are five core ideas you must retain:

1. Everything in Java revolves around objects.
2. References point to heap objects.
3. Encapsulation protects state.
4. Polymorphism works via late binding.
5. Memory is divided into stack and heap.

If you understand those deeply, the rest builds naturally on top.
