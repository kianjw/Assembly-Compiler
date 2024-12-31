# Mini Compiler: AST and Code Generation

This project implements a mini compiler that parses mathematical and assignment expressions, builds an Abstract Syntax Tree (AST), performs semantic checks, and generates assembly-like code. It adheres to a specific grammar structure and supports operations such as addition, subtraction, multiplication, division, and increment/decrement.

---

## Features

- **Lexical Analysis (Lexer)**: 
  - Tokenizes the input string into a linked list of tokens based on the defined grammar.
  - Supports tokens for identifiers, constants, and arithmetic/assignment operators.

- **Syntax Analysis (Parser)**:
  - Constructs an AST from the token list using recursive parsing functions.
  - Implements grammar rules for statements, expressions, and operations.

- **Semantic Checking**:
  - Ensures the left-hand side of assignments and increment/decrement operations are valid l-values (identifiers).

- **Code Generation**:
  - Produces pseudo-assembly instructions for arithmetic and assignment operations.

- **Debugging Utilities**:
  - Prints token arrays and ASTs for debugging purposes.
  - Includes detailed error reporting for lexer, parser, and semantic errors.

---

## Supported Grammar

The compiler supports a subset of arithmetic and assignment expressions based on the following grammar rules:

### Grammar Rules
- **Statement (`STMT`)**: `<EXPR> ';'`
- **Expression (`EXPR`)**: `<ASSIGN_EXPR>`
- **Assignment Expression (`ASSIGN_EXPR`)**: `<UNARY_EXPR> '=' <ASSIGN_EXPR> | <ADD_EXPR>`
- **Addition Expression (`ADD_EXPR`)**: `<ADD_EXPR> ('+' | '-') <MUL_EXPR> | <MUL_EXPR>`
- **Multiplication Expression (`MUL_EXPR`)**: `<MUL_EXPR> ('*' | '/' | '%') <UNARY_EXPR> | <UNARY_EXPR>`
- **Unary Expression (`UNARY_EXPR`)**: ('++' | '--' | '+' | '-') <UNARY_EXPR> | <POSTFIX_EXPR>`
- **Postfix Expression (`POSTFIX_EXPR`)**: `<PRIMARY_EXPR> ('++' | '--')?`
- **Primary Expression (`PRI_EXPR`)**: `IDENTIFIER | CONSTANT | '(' <EXPR> ')'`

---

## Project Structure

- **`main()`**:
  - Reads input, tokenizes it, parses it into an AST, performs semantic checks, and generates assembly-like code.

- **Lexer**:
  - Converts input strings into a linked list of tokens.

- **Parser**:
  - Constructs the AST recursively using grammar rules.

- **Semantic Checker**:
  - Verifies the semantic validity of the AST.

- **Code Generator**:
  - Produces assembly-like instructions for arithmetic and assignment operations.

- **Debugging Utilities**:
  - Functions to print tokens and ASTs for debugging.

