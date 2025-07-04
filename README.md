# MiniJS Interpreter

MiniJS is a lightweight interpreter implemented in C that processes and executes a minimal subset of JavaScript-like syntax. It includes support for variable declarations (`let`, `var`, `const`), arithmetic expressions, constant protection, and a simple `print()` function. This project serves as a learning tool to understand the fundamentals of interpreter design, including lexical analysis, parsing, and interpretation.

---

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Directory Structure](#directory-structure)
- [How It Works](#how-it-works)
  - [1. Lexer](#1-lexer)
  - [2. Parser](#2-parser)
  - [3. Interpreter](#3-interpreter)
- [Build and Run Instructions](#build-and-run-instructions)
- [Example Usage](#example-usage)
- [Supported Syntax](#supported-syntax)
- [Limitations](#limitations)
- [Educational Goals](#educational-goals)
- [Contributing](#contributing)
- [License](#license)
- [Author](#author)

---

## Overview

The MiniJS Interpreter project demonstrates how to design and implement a minimal scripting language interpreter from scratch. It simulates core JavaScript behaviors like variable declaration, assignment, arithmetic operations, and output, using foundational compiler concepts like tokenization, recursive descent parsing, and an execution engine.

---

## Features

- Variable declarations with `let`, `var`, and `const`
- Arithmetic operations: `+`, `-`, `*`, `/`
- Parentheses-based expression grouping
- Constant variable protection (cannot reassign `const`)
- Statement termination using `;`
- Built-in `print()` function to display results
- Error handling for undefined variables and invalid assignments

---

## Directory Structure

MiniJS/
│
├── main.c # Program entry point, handles input
├── lexer.c/.h # Tokenizes the source code
├── parser.c/.h # Parses token stream and checks syntax
├── interpreter.c/.h # Symbol table and execution engine
├── README.md # Project documentation

---


---

## How It Works

### 1. Lexer

The lexer reads the raw input string and converts it into a sequence of tokens. These tokens represent syntactic elements such as numbers, operators, keywords (`let`, `const`, `print`), and identifiers.

- Skips whitespace
- Recognizes integers and decimal numbers
- Identifies keywords and symbols
- Returns token objects with type, text, and value

### 2. Parser

The parser is built using **recursive descent** parsing. It receives the stream of tokens from the lexer and enforces the syntactic rules of the language.

- Parses expressions and statements
- Enforces operator precedence
- Parses grouped expressions using parentheses
- Ensures correct structure of declarations and assignments

### 3. Interpreter

The interpreter evaluates parsed expressions and executes statements. It maintains a symbol table of declared variables and ensures immutability for constants.

- Stores variables in memory
- Handles runtime errors (e.g., undefined variables)
- Supports variable reassignment and constant protection
- Handles evaluation of arithmetic expressions

---

## Build and Run Instructions

### Requirements

- GCC or any standard C compiler
- Unix/Linux/macOS/Windows terminal

### Compile

Run the following command in the terminal:

```bash
gcc main.c lexer.c parser.c interpreter.c -o minijs
```
Execute
```bash
./minijs 
```
You will be prompted to enter your code directly into the terminal. To indicate the end of input:

On Linux/macOS: press Ctrl + D
On Windows: press Ctrl + Z and then Enter


## Example Usage

let x = 10;
var y = 5;
const z = x + y;
x = x + 2;
print(x);        // Outputs: 12
print(z);        // Outputs: 15


## Supported Syntax

| Syntax Element        | Description                                     | Example                  |
| --------------------- | ----------------------------------------------- | ------------------------ |
| Variable Declaration  | Using `let`, `var`, or `const`                  | `let a = 5;`             |
| Arithmetic Expression | Addition, subtraction, multiplication, division | `let sum = (a + b) * 2;` |
| Variable Assignment   | Assign new values (not allowed on `const`)      | `a = a + 3;`             |
| Print Function        | Outputs result to console                       | `print(a);`              |
| Semicolon             | Used to terminate every statement               | `let x = 3;`             |


## Limitations

-No support for:
    -Strings or boolean values
    -Control flow statements (e.g., if/else, loops)
    -Functions or scoping
-No expression chaining or complex grammar
-Variables are global and unscoped
-Minimal error recovery; interpreter exits on error


## Educational Goals
This interpreter is designed primarily for learning and teaching purposes. Key concepts covered include:

-Tokenization using character-level parsing
-Recursive descent parsing techniques
-Abstract Syntax Tree (AST)-free evaluation
-Managing symbol tables and runtime states
-Building a C-based interpreter from scratch

This project is suitable for students, educators, and self-learners exploring:

-Compiler and interpreter design
-Language implementation in C
-Fundamentals of programming languages

## Contributing 

Contributions are welcome. You can help by:

-Reporting bugs or edge cases
-Improving the parser or interpreter
-Adding new features (e.g., control flow, functions)
-Enhancing error handling or optimization

To contribute:

1. Fork the repository
2. Create a new branch
3. Commit your changes
4. Open a pull request with clear documentation


