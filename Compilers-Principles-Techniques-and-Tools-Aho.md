# [Compilers - Principles, Techniques and Tools , Aho ]()

- [1. Introduction](#introduction)
  - [1.1 Language Processors](#11-language-processors)
  - [1.2 Structure of a Compiler](#12-strucutre-of-a-compiler)

## 1. Introduction

This Chapter is a high level overview of the structure of a Compiler.

### 1.1 Language Processors

**Compiler:** A compiler is a program that can read a program in one language (the source language) and translate it into an equivalent program in another language a.k.a Target language.

**Interpreter:** An interpreter is a also a language processor that directly executes the operations in source program on inputs instead of producing a target program.

- An interpreter gives better **error diagnostics** than a compiler.

- But the machine-language produced by compiler is much **faster** than an interpreter.

**Hybrid Compilers:**
Java language processors combine both compilation and interpretation. In Java

- The source program is first compiled to an intermediate _byte code_
- Then the JVM interprets the byte code

> ##### JIT - Just In Time
> For faster processing some java compilers translate byte code immediately before they the intermediate program to process input

A source program maybe divided into modules stored in seperate files. A **Preprocessor** collects the source program and expands shorthands ( macros ) 

Assembly-language program is produced as output because its easier to produce and to debug, This is then process by an _assembler_ 

Assembler produces relocatable machine code, this code is linked together using a _Linker_. The a _Loader_ puts together all the executable objects into memory.

> Relocatable in the sense the code in one file refers to a location in another file

so the steps are as follows
- Preprocessor
- Compiler
- Assembler
- Linker/Loader

### 1.2 Strucutre of a Compiler
Compiler has 2 parts 
- Analysis
- Synthesis

Are often called the frontend and backend of a compiler

##### Analysis
This part breaks program into pieces and imposes grammatical structure. Then uses this to create intermediate source program. In the process provides messages about errors.

This parts collects and stores information about source program in _symbol table_ which is passed to the synthesis part


##### Synthesis
This part constructs the target program from the symbol table and intermediate program from analysis. 

##### Phases of a compiler
- Lexical Analyzer
- Syntax Analyzer
- Semantic Analyzer
- Intermediate Code Generator
- Machine-Independent Code Optimizer
- Code Generator
- Machine-Dependent Code Optimizer

Machine independent optimization is seen in few compilers. Both optmizations are optional.

#### 1.2.1 Lexical Analysis
Lexical analysis or scanning reads the source program and groups characters into _lexemes_. For each lexeme the lexical analyser produces an output token of the form


${\langle token-name, attribute-name \rangle}$



