## IO Devices, CPU, and Memory

## Why Do We Need Programming Languages?
Computers are powerful tools capable of performing complex operations at very fast speeds. CPU relies on binary sequences (it means —strings of 0s and 1s—) because the CPU only understands machine language. Writing instructions in binary for even simple tasks would be difficult and error-prone for humans. This is where programming languages come into play, acting as a bridge between human-readable instructions and the binary sequences understood by computers.

How CPU Works with Programming Languages?
The CPU (Central Processing Unit) is the brain of a computer. It follows a series of steps to process instructions:

Fetch: Get the instructions.
Decode: Figure out what the instruction means.
Execute: Perform the action.
The CPU understands only machine code (binary). So how does it work with programming languages like Java, Python or C++?

The answer is compilers and interpreters. These tools convert the human-friendly code into machine code the CPU can process.

Compilers and Interpreters: The Translators
Programming languages, like English or any natural language, need translators for a CPU to understand them. These translators are categorized into two types:

1. Compilers
A compiler translates the entire source code of a program into machine code before execution.
Once compiled, the machine code can be executed directly by the CPU without the need for further translation.
Examples of compiled languages include C, C++, and Go.
2. Interpreters
An interpreter processes the code line by line, translating and executing each instruction sequentially.
Interpreters are more flexible but often slower compared to compilers because the translation happens during runtime.
Examples of interpreted languages include Python, Ruby, and JavaScript.
Compilers VS Interpreters
The key difference between the compiler and the interpreters are listed below:

| Aspect           | Compiler                                | Interpreter                          |
|-----------------|----------------------------------------|--------------------------------------|
| **Translation**  | Translates the entire code at once.   | Translates code line by line.       |
| **Execution Speed** | Faster, as the code is pre-compiled. | Slower, due to on-the-fly translation. |
| **Output**      | Produces a standalone executable file. | Does not produce a separate file; runs the code directly. |
| **Error Detection** | Displays all errors after compilation. | Stops immediately upon encountering an error. |
| **Examples**    | C, C++, Java                           | Python, JavaScript, Ruby            |

### Introduction to JAVA
Java is one of the most popular languages, it was introduced in 1995 by Sun Microsystems(now owned by Oracle Corporation). Its unique features like platform independence and robustness have made it the preferred choice for millions of developers globally.

Here, we are going to discuss the reasons for the popularity of the Java Programming language

1. Platform Independent
One of the key reasons for Java's popularity is platform independence. Java achieves platform independence through its unique compilation and runtime process. Before we talk about how Java is platform-independent let's discuss the concept of a platform. A platform is the combination of hardware and software environment where a program runs. For example Windows, macOS, and Linux.

2. How Java Works?
Java’s compilation process is different from programming languages like C/C++. When we write a Java program, the Java compiler compiles it into an intermediate, platform-independent code called bytecode. This bytecode can run on any platform that has JVM(Java Virtual Machine) installed.

3. Advantages of Java Over C++
- Automatic Garbage Collection: Java has an automatic garbage collector that manages memory, reducing the chances of memory leaks.
- Better Exception Handling: Java offers robust mechanisms for handling exceptions, improving program reliability.
- Enhanced Multithreading: Java provides better support for multithreading, making it easier to develop concurrent applications.
- Difficult to Write Bad Code: Java’s strict rules and default reference behavior for non-primitive types ensure better code maintainability.


### Writing First Program in Java

Java is a versatile, platform-independent programming language that can run on any device equipped with the Java Runtime Environment (JRE). Writing your first Java program is straightforward, but before diving into code, let’s set up the necessary environment.

1. Download the JDK (Java Development Kit)
JDK stands for Java Development Kit. It is a software development kit that provides tools and libraries for developing Java applications.

JDK is an essential toolkit for Java developers. It includes:

**Java Virtual Machine (JVM)**: The JVM is the engine that runs Java programs. It converts bytecode into machine code to execute your program. The JVM ensures Java's "Write Once, Run Anywhere" capability.
Java Class Libraries: These are pre-written code libraries that help simplify complex tasks.
Together, the JVM and class libraries form the Java Runtime Environment (JRE), which is required to execute Java applications.
What is JRE(Java Runtime Environment)
JRE stands for Java Runtime Environment. It is required to run the Java Program. It provides the libraries, JVM, and other components necessary to execute Java applications.

**What is JVM(Java Virtual Machine)**
JVM stands for Java Virtual Machine. JVM is called an abstract virtual machine because it does not exist physically, but it is a kind of specification that provides a secure runtime environment to execute the bytecode generated through the compiler, JVM invokes the main( ) method present in the Java program. JVM is the part of JRE.

How the JVM Works
The JVM can execute code using two primary methods:

Interpreter: Translates bytecode to machine code line by line. This approach is slower because it processes code at runtime.
JIT (Just-In-Time Compilation): Converts bytecode into native machine code in bulk during execution, significantly improving performance. JIT is the most preferred approach for its speed and efficiency.
Developer Tools in JDK
The JDK also provides essential tools for development:

Java Compiler: Converts Java source code into bytecode.
Java Debugger: Helps identify and fix issues in your code.
Java Document Generator: Creates documentation from your code comments.

2. Download an Integrated Development Environment (IDE)
An IDE simplifies coding by providing features like syntax highlighting, code suggestions, and debugging tools. Popular Java IDEs include:

IntelliJ IDEA: A powerful IDE for professional developers, offering advanced features
Eclipse: A free, open-source IDE with excellent community support
BlueJ: Ideal for beginners due to its simplicity and ease of use

3. Set the Class Path
The class path is a configuration that tells the JVM and Java compiler where to find user-defined classes and packages. You need to set it correctly for your programs to compile and run. Typically, this is done during JDK installation, but you can customize it by updating the environment variables in your operating system

First Program - "Hello World"
The below-given program is the simplest program of Java, printing "Hello World" to the screen. Let us try to understand every bit of the code step by step.

```java
// This is a simple Java Hello World program.

public class Test {
  
    // This is the main function 
    // this is where the execution of Java Programm begins

    public static void main(String args[]) {
        System.out.println("Hello, World");
    }
}
```

Output
Hello, World
Explanation: The "Hello World!" program consists of three primary components: the Test class definition, the main method, and the source code comments. The following explanation will provide you with a basic understanding of the code:

1. Class Defination
The class keyword declares a new class.

Syntax:
class Test

Test is the name of the class (an identifier). The class name must match the file name (Test.java)
Everything inside the class is enclosed within { and }
2. Main Method
The main method is the entry point for the program

Syntax:
public static void main(String[] args)

public: So that JVM can execute the method from anywhere.
static: Main method is to be called without object. The modifiers public and static can be written in either order.
void: The main method doesn't return anything.
main(): Name configured in the JVM.
String[]: The main method accepts a single argument: an array of elements of type String.
3. Printing Output
Syntax:

System.out.println("Hello, World!");

This statement prints the string "Hello, World!" to the console

System: A predefined class providing access to system resources.
out: A static variable in the System class that represents the standard output stream (console).
println: A method to print the output with a line break.
4. Comments
They can either be multi-line or single-line comments.

Multi-line Comments

Start with /* and end with */. Used for multi-line explanations.

/* This is a simple Java program. Call this file "Test.java". */

Single-line Comments

Begin with // and end at the line break. Used for brief explanations.

// This is a single-line comment.

Important Points
Class Name and File Name:
**The name of the class (Test) must match the file name (Test.java).**
This is mandatory in Java when a public class is defined.
Main Class:
A program can have only one public class with the main method.
Code Structure:
All Java code resides inside a class, and the execution starts from the main method.


