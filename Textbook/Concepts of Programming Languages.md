## #Chapter-1

- [[1.1]]
- [[1.2]]
- [[1.3]]
	- [[Intro]]
	- [[Readability]]
	- [[Writability]]
	- [[Reliability]]
	- [[Cost]]
- [[1.4]]
- [[1.5]]
- [[1.6]]
- [[1.7]]
- [[1.8]]

This chapter establishes the **rationale for studying programming languages** and introduces the criteria used for their critical evaluation.

|Key Concept|Summary|
|---|---|
|**Evaluation Criteria**|The primary benchmarks for language design: **Readability** (ease of understanding), **Writability** (ease of creation), and **Reliability** (conformance to specifications).|
|**Design Trade-offs**|The inevitable conflicts between the criteria, e.g., features that increase **Writability** (like pointers in C) often decrease **Reliability**.|
|**Implementation Methods**|How languages are executed: **Compilation** (translation to machine code), **Interpretation** (direct execution), and **Hybrid** (translation to an intermediate **Byte Code** for a **Virtual Machine**, often utilizing **JIT Compilation**).|
|**Imperative Paradigm**|The most common programming style, based on the **Von Neumann Architecture** and characterized by explicit memory state changes via the **assignment statement**.|

## #Chapter-2

This chapter provides the historical context, highlighting how specific needs drove the design of major language families.

|Key Concept|Summary|
|---|---|
|**Early Scientific**|**FORTRAN** (1950s) focused on **execution efficiency** for numeric computing—the first widely used high-level language.|
|**Early Functional**|**LISP** (1950s) introduced **functional programming**, **dynamic memory allocation**, and **garbage collection** for AI.|
|**Business/Readability**|**COBOL** (1950s) emphasized **readability** and **data description** for business applications.|
|**Algol Family**|**Algol 60** (1960s) introduced modern **structured programming** concepts like **block structure** (scope) and the formal syntax description method, **BNF**.|
|**Systems Programming**|**C** (1970s) blended low-level access (pointers) with high-level control structures, prioritizing **efficiency** and programmer control for OS development (UNIX).|
|**Object-Oriented (OOP)**|**Simula** (1960s) and **Smalltalk** (1980s) pioneered core OOP concepts (**classes, inheritance**), leading to the development of **C++** and later, **Java**.|

## #Chapter-3 

- [[3.1]]
- [[3.2]]
- [[3.3]]
- [[3.4]]
- [[3.5]]

This chapter formalizes how the form and meaning of a language are defined, which is essential for compiler construction.

|Key Concept|Summary|
|---|---|
|**Syntax vs. Semantics**|**Syntax** is the form (grammar); **Semantics** is the meaning (action) of the program units.|
|**Formal Syntax**|**Backus-Naur Form (BNF)**, which is equivalent to a **Context-Free Grammar (CFG)**, is used to formally describe syntax via **Rules** (or Productions) involving **Terminals** (lexemes) and **Nonterminals**.|
|**Parse Tree & Ambiguity**|A **Parse Tree** is the hierarchical representation of a valid statement's derivation. **Ambiguity** occurs when a single statement can generate two or more distinct parse trees, which is unacceptable for a language design.|
|**Formal Semantics**|Methods to define meaning: **Operational** (how state changes), **Denotational** (mathematical functions), and **Axiomatic** (using logic to prove correctness via **Preconditions** and **Postconditions**).|

## #Chapter-4

This chapter details the fundamental concepts regarding identifiers and the runtime environment.

| Key Concept             | Summary                                                                                                                                                                                                                                   |
| ----------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Bindings & Times**    | A **Binding** is an association between an entity (name, type) and an attribute (address, value). **Static Binding** occurs before runtime; **Dynamic Binding** occurs during runtime.                                                    |
| **Variable Attributes** | Variables are abstractions of memory defined by their **Name, Address, Value, Type, Lifetime, and Scope**.                                                                                                                                |
| **Lifetime & Storage**  | The duration of memory allocation: **Static** (entire program execution), **Stack-Dynamic** (allocated on subprogram entry/exit, common for locals), and **Heap-Dynamic** (explicitly or implicitly allocated/deallocated from the heap). |
| **Scope Rules**         | The range of visibility for a name: **Static Scope** (determined by the program's textual structure at compile time, used by most languages) versus **Dynamic Scope** (determined by the calling sequence at runtime).                    |
| **Type Checking**       | Ensuring operand compatibility. **Static Type Checking** (at compile time) leads to higher efficiency; **Dynamic Type Checking** (at runtime) leads to higher flexibility. A **Strongly Typed** language catches all type errors.         |

## #Chapter-5

