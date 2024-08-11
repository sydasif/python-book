## Introduction to Computer Programming

Every computer operates based on a set of instructions known as a computer program. These programs are essential as they transform computer hardware into a functional device. Think of a computer as a piano; without a skilled musician, it remains silent.

Computers excel at performing basic operations like addition and division at incredible speeds and with perfect accuracy. However, they don't intuitively understand concepts like humans do. For example, if you want to calculate your average speed on a road trip, you need to provide the computer with precise instructions:

1. **Input the distance traveled.**
2. **Input the travel time.**
3. **Calculate the average speed by dividing the distance by the time.**
4. **Display the result in a human-readable format.**

These steps, though simple, form a computer program. While these actions differ from what a computer naturally understands, they can be translated into a language that the computer can process.

### Natural Languages vs. Programming Languages

Human languages help us express our thoughts and share knowledge. Some languages use gestures or body language, while others, like our native languages, use words to convey our ideas. Computers have their own language called machine language, which is very complex and hard for humans to understand.

Even the most advanced computers aren't truly intelligent. They only follow a set of basic commands, like "take this number, divide it by another, and save the result." This set of commands is called an instruction list (IL).

> *Note*: Machine languages are also created by humans.

### The Anatomy of a Language

Every language, whether it's a natural language or a machine language, has the following key elements:

- **Alphabet**: A set of symbols used to create words.
- **Lexis (Dictionary)**: A collection of words and their meanings.
- **Syntax**: Rules that govern how sentences and phrases are structured.
- **Semantics**: Rules that determine the meaning of sentences and phrases.

In machine language, the IL serves as the alphabet (using zeros and ones). However, humans need a more expressive language to write programs that computers can execute. These high-level programming languages are similar to natural languages. They have symbols, words, and rules that humans can understand, allowing us to give commands to computers.

A program written in a high-level programming language is called source code, and the file containing this source code is known as a source file.

### Compilation vs. Interpretation

Computer programming involves using elements of a chosen programming language to achieve a desired outcome. This outcome depends on the programmer's imagination, knowledge, and experience.

There are two main methods for translating a program from a high-level programming language into machine language:

1. **Compilation**: The source program is translated once to create a file containing machine code. This file can be distributed globally, and the program responsible for this translation is called a compiler.

2. **Interpretation**: The source program is translated each time it needs to run. The program performing this transformation is an interpreter, which interprets the code every time it’s executed. This means you can’t distribute the source code as-is; the end-user also needs the interpreter to run it.

#### Compilation — Advantages and Disadvantages

- **Advantages**:
  - Executed code is typically faster.
  - Only the user needs the compiler; the end-user can use the code without it.
  - The translated code is stored in machine language, keeping it secure.

- **Disadvantages**:
  - Compilation is time-consuming; you can’t run your code immediately after making changes.
  - You need a compiler for each hardware platform you want your code to run on.

#### Interpretation — Advantages and Disadvantages

- **Advantages**:
  - You can run the code as soon as you finish writing it; no need for additional translation phases.
  - The code is stored in a programming language, not machine language, so it can run on different architectures without separate compilation.

- **Disadvantages**:
  - Interpretation doesn’t result in high-speed execution; your code shares resources with the interpreter.
  - Both you and the end-user need the interpreter to run your code.

Python is an interpreted language. To program in Python, you need a Python interpreter. Without it, you can’t execute your code. The best part is that Python is free, which is one of its biggest advantages. Languages designed for interpretation are often called scripting languages, and the source programs written in them are called scripts.

## Understanding Python Language

Python is a popular, interpreted, object-oriented, high-level programming language with dynamic semantics. It's used for general-purpose programming and is known for its versatility. The name "Python" comes from an old BBC television comedy sketch series called Monty Python’s Flying Circus.

Python was created by *Guido van Rossum*, who was born in 1956 in Haarlem, the Netherlands. Python's popularity has grown worldwide, but it all started with Guido’s vision.

In 1999, *Guido van Rossum* outlined his goals for Python:

- Create an easy, intuitive, and powerful language.
- Keep it open source.
- Make it understandable, like plain English.
- Ensure it’s suitable for everyday tasks, allowing for short development times.

Python has matured and gained trust in the programming world. It’s not just a passing trend but a significant player in the programming landscape.

### What Sets Python Apart?

There are many reasons why Python stands out:

- **Easy to Learn**: Python takes less time to learn compared to many other languages, allowing you to start programming quickly.
- **Easy to Teach**: Teaching Python is straightforward, focusing on programming techniques rather than complex language intricacies.
- **Easy to Use**: Python often lets you write code faster when creating new software.
- **Easy to Understand**: Python code is generally easier to read and maintain.
- **Easy to Obtain, Install, and Deploy**: Python is free, open-source, and cross-platform, making it accessible to everyone.

### Python’s Competitors

Python has two direct competitors with similar properties and capabilities:

- **Perl**: A scripting language that leans towards tradition and convention, with similarities to older languages derived from classic C programming.
- **Ruby**: Another scripting language that is more progressive and filled with fresh ideas. Python finds its place somewhere between these two options.

Python’s growth is evident as more development tools are implemented in Python. Many everyday applications are being written in Python, and numerous scientists have switched from expensive proprietary tools to Python.
