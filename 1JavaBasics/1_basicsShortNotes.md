## IO Devices, CPU, and Memory

### Hardware Devices
- **Input devices**
- **Output devices**
- **Input + Output device** → Scanner and Printer

### CPU (Central Processing Unit)
- Device that performs computations.

### Memory
- Used to store data.
- Three types of memory:
  1. **Cache**
  2. **Main Memory (RAM)**
  3. **Hard Disk**

- In desktops or laptops, a **fan** is present for the CPU as it performs heavy computations.
- **Cache** is present on the CPU chip itself.
- **Main memory (RAM)** stores and executes programs temporarily.
- **Hard disk** is for **permanent storage** and can be internal or external (USB-connected). Also known as a **secondary storage device**.
- RAM is volatile: If the computer is turned off, data is lost.
- The CPU interacts with **RAM** to fetch and execute instructions.
- When software is launched, it is loaded into **RAM** for execution.

### Who Manages These Components?
- **Operating System (OS)**
  - A software that controls the computer when powered on.
  - Examples: Windows, Linux, Unix, macOS.

---

## Computer Organization and Operating System

### Device Organization in a Computer
- **CPU interacts with Cache and Main Memory**
- Cache memory is within the CPU chip itself.

### Why Do We Have Three Types of Memory?
**Desirable features of memory:**
1. **Access Time** - CPU should quickly access it (low latency).
2. **Cost**
3. **Capacity**

**Comparison of Memory Types:**
- **Cache** → Low access time, high cost, low capacity.
- **Main Memory** → Moderate in all three.
- **Hard Disk** → High capacity, low cost, high access time.

- Cache and Main Memory are **volatile**, meaning data is lost when power is off.

**Analogy:**
- **Cache** → Main counter in a shop.
- **Main Memory** → Shop itself.
- **Hard Disk** → Storage area.

- **OS** manages data movement between memory and secondary storage.

---
## Why do we need Programming Languages
- **CPU understands only binary (0,1).**
- Humans need easier ways to give instructions → **Programming Languages** were created.
- These languages use **compilers** or **interpreters** to convert code to machine instructions.

### Compiler vs Interpreter
- **Compiler** → Converts the whole code at once.
- **Interpreter** → Converts code **line by line**.

---

## Introduction to Java

### Java is Platform-Independent

**What is a Platform?**
- A combination of **OS** and **architecture**.

**Before Java:**
- Executables generated for **Platform 1** couldn’t run on **Platform 2**.
- Each platform required a separate compiler.

**With Java:**
- **Java Compiler** → Converts code to **Java Bytecode**.
- Bytecode runs on any platform with **JVM (Java Virtual Machine)**.
- JVM converts bytecode to platform-specific instructions.
- Different **JVMs** exist for Windows, Linux, etc.
- **Compilation is simple, execution is handled by JVM**.

**Other Languages Using This Approach:**
- Python, C#

### Java vs C/C++
- **C, C++** → Use pointers, complex memory management.
- **Java** → No pointers, only **pass-by-reference** for non-primitive types.
- No **operator overloading** (simplifies language).

### Java Security Features
- **C, C++** → Executables run without security checks.
- **Java** → JVM acts as a **security manager**.
- **No direct memory access** (no pointers).
- **Statically typed** → Variable types are declared before use (faster execution).
- **Automatic garbage collection**.
- **Better exception handling & multi-threading**.
- **Highly maintainable**.

---

## Writing Your First Java Code

### Java is Portable
- **Write once, run anywhere**.
- **C, C++** → Variable size varies by compiler.
- **Java** → Fixed variable size.

### Java Development Kit (JDK)
- Open-source tool by **Oracle**.
- **JDK** contains:
  - **JVM** (Java Virtual Machine)
  - **Java Class Libraries**
  - **Development Tools**

### Java Runtime Environment (JRE)
- **JRE** = JVM + Java Class Libraries
- **JDK** = JRE + Dev Tools
- Dev Tools include:
  - **Java Compiler**
  - **Java Debugger**
  - **Java Document Generator**

### Setting Up Java
- **IDE** or **text editor** to write programs.
- **Classpath** must be set manually if not using an IDE.

### Java Hello World Program
```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

### Java Execution Steps
```sh
javac HelloWorld.java   # Compiles to bytecode
java HelloWorld        # Runs bytecode in JVM
```

### Java Program Structure
- **Everything in Java is inside a class**.
- **Execution starts from the `main` method**.
- **Multi-line comments** using `/* */`.
- **Access Specifier (`public`)** → Allows execution from outside the package.
- **Static methods** → Called without creating an object.
- **Void return type** → `main` doesn’t return any value.
- **String array (`String[] args`)** → Command-line arguments.
- **`System.out.println`** → Prints output to console.

---