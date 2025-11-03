#Readability is defined as the ease with which programs can be read and understood. It is one of the most important criteria for judging a programming language.

### Historical Context

- **Before 1970:**
    - Focus: Software development was seen primarily as _writing code_.

    - Primary Characteristic: [[Computational Efficiency]].

    - Design Philosophy: Languages were designed from the computer's point of view ([[Machine Orientation]]).

- **In the 1970s:**
    - Development: The [[Software Life Cycle]] concept emerged (Booch, 1987).

    - New Understanding: Coding was recognized as a small part of the cycle, while [[Software Maintenance]] was identified as a major part, especially in terms of cost.

    - **Key Insight:** Because ease of [[Software Maintenance]] is determined largely by [[Readability]], readability became a critical measure of program and language quality.

- **The Shift:** This marked a significant crossover from a focus on [[Machine Orientation]] to a focus on [[Human Orientation]].

### Context is Critical

Readability must be considered within the context of the **problem domain**.

> **For example:** A program describing a scientific computation written in a language _not_ designed for it (e.g., a business-oriented language) may be unnatural and convoluted, making it exceptionally difficult to read.

The following subsections describe the specific characteristics that contribute to the readability of a programming language.

## Overall Simplicity

The **overall simplicity** of a programming language strongly affects its readability.

- **Learning Curve:** A language with a large number of basic constructs is more difficult to learn.

- **Subset Problem:** Programmers often learn only a **subset** of a large language.

    - _Argument for large languages:_ Some argue this is fine.

    - _Counterargument:_ This argument is **not valid**. Readability problems occur when the program's author has learned a **different subset** from the one the program's reader is familiar with.

Simplicity can be compromised by several factors:

1. **Feature Multiplicity**

    - **Definition:** Having more than one way to accomplish a particular operation.

    - **Example:** In [[Java]], incrementing an integer can be done in at least four ways:

        - `count = count + 1`

        - `count += 1`

        - `count++`

        - `++count`

    - While some have different meanings in specific contexts, they are identical when used as stand-alone expressions, creating unnecessary variation.

2. **Operator Overloading**

    - **Definition:** A single operator symbol has more than one meaning.

    - **Good Overloading (Simplifies):** Using `+` for both integer and floating-point addition. This reduces the number of operators (e.g., not needing `+i` and `+f`).

    - **Bad Overloading (Reduces Readability):** Can lead to confusion if users can create their own overloading and do not do it sensibly.

    - **Example of Confusion:** A programmer defines `+` for two [[Arrays]] to mean the sum of all elements in both. This is confusing because the _usual_ meaning of vector addition is a pairwise sum, resulting in another vector. An even worse definition would be `vector1 + vector2` meaning the _difference_ of their first elements.

#### Simplicity Can Be Taken Too Far

Simplicity in languages can, however, be carried to an extreme.

- **Example:** [[Assembly Language]].

    - The form and meaning of individual assembly statements are extremely simple.

    - **The Readability Problem:** This very simplicity makes assembly programs _less_ readable.

        - **Lack of Control Structures:** Program structure is less obvious.

        - **Verbosity:** Far more statements are required to achieve the same result as a high-level language program.

- **Conclusion:** This same argument applies to high-level languages that have inadequate [[control structures]] and [[data structures]].

### Orthogonality

#Orthogonality is a language design concept where a relatively small set of primitive constructs can be combined in a relatively small number of ways to build the language's control and data structures.

> [!key] Core Principles of Orthogonality
> 
> 1. Every possible combination of primitives is **legal and meaningful**.
>     
> 2. The meaning of an orthogonal language feature is **independent of the context** of its appearance in a program. (This is analogous to orthogonal vectors in mathematics, which are independent).
>     

> **Example of Orthogonality:** If a language has 4 primitive data types (e.g., `int`, `float`, `char`) and 2 type operators (e.g., `array`, `pointer`), an orthogonal design would allow you to create an `array` of `pointers` to `int`, a `pointer` to an `array` of `float`, a `pointer` to a `pointer`, etc., all with consistent meaning.

- **Lack of Orthogonality:** A lack of orthogonality leads to **exceptions** to the language rules.

> _Example:_ If the language designers decided that `pointers` cannot point to `arrays`, this would be a non-orthogonal exception.

### Comparison: IBM vs. VAX Assembly

Below is a clear example of #orthogonal vs. #non-orthogonal design for an "add" operation.

| Machine          | Design         | Instructions                                 | Semantics                                       |
| ---------------- | -------------- | -------------------------------------------- | ----------------------------------------------- |
| IBM Mainframe    | Non-Orthogonal | `A Reg1, memory_cell`<br><br>`AR Reg1, Reg2` | `Reg1 = Reg1 + mem`<br><br>`Reg1 = Reg1 + Reg2` |
| VAX Minicomputer | Orthogonal     | `ADDL operand_1, operand_2`                  | `operand_2 = operand_1 + operand_2`             |

**Analysis:**
- The VAX design is #orthogonal. A single instruction, `ADDL`, can use registers or memory cells for either operand, allowing all 4 combinations (reg-reg, reg-mem, mem-reg, mem-mem).

- The IBM Design is #non-orthogonal. It requires two different instructions, and only 2 of the 4 combinations are possible. You cannot, for example, add two memory cells and store the result in memory. This design is more restricted, less writable, and harder to learn.

### Orthogonality and Simplicity

Orthogonality is closely related to [[Simplicity]].

- More Orthogonal = Fewer Exceptions = Higher Regularity = Easier to learn, read, and understand

### Examples of Lack of Orthogonality in C

[[C]] has several exceptions that demonstrate a lack of orthogonality:

- **Return Values:** [[Functions]] can return [[Structs]], but cannot return [[Arrays]].

- **Struct Members:** A `struct` member can be any data type _except_ `void` or a `struct` of the same type.

- **Array Elements:** An `array` element can be any data type _except_ `void` or a [[Function]].

- **Parameter Passing:** Parameters are passed by value, _except_ [[Arrays]], which are effectively [[Pass-by-Reference]] (because the array name is treated as the address of its first element).

### Example of Context Dependence in C

The meaning of an operator should not depend on context, but in C, it often does.

- **Expression:** `a + b`

- **Context 1 (Integers):** If `a` and `b` are `int`, this is simple addition.

- **Context 2 (Pointer):** If `a` is a `float*` (a pointer to a float) and `b` is an `int`, the compiler will perform [[Pointer Arithmetic]]. The value of `b` is scaled (multiplied by `sizeof(float)`) before being added to the address in `a`.

- **Conclusion:** The _type_ of `a` (the context) fundamentally changes the treatment of `b`.   

### The Problem of Too Much Orthogonality

While orthogonality is good, **too much orthogonality can also cause problems**, leading to "unnecessary complexity."

- **Example:** [[ALGOL 68]].

- **Problem:** In [[ALGOL 68]], every language construct has a type, and there are almost no restrictions on combinations. This freedom allows for a "combinatorial explosion" of constructs.

- **Extreme Example:** It allows a conditional statement (`if...then...else`) to be on the _left side_ of an assignment statement (as long as it resolves to an address). This is overly complex and harms readability.

### Final Conclusion

- **Simplicity** is a balance: it requires a relatively small number of primitive constructs _and_ a **limited use of orthogonality**.

- [[Functional Languages]] (like [[Lisp]]) are often cited as having a good combination of simplicity and orthogonality, as they are built on a single, simple construct: the [[Function Call]]. The main trade-off that has prevented their wider use is often [[Computational Efficiency]].

## Data Types

The presence of adequate facilities for defining [[Data Types]] and [[Data Structures]] in a language is another significant aid to [[Readability]].

When a language lacks an appropriate data type, programmers are forced to simulate it, often using numeric types for concepts like flags. This can obscure the program's intent and relies on the reader understanding the convention.

> [!example] Comparison: Boolean Flags
> 
> **Poor Readability:** In a language without a native [[Boolean Type]] (e.g., the original version of [[C]]), a programmer might write:
> 
> ```C
> timeout = 1;
> ```
> 
> The meaning of this statement is unclear. `1` is a "magic number" that the programmer must *know* means "true".
> 
> **Good Readability** In a language that includes a native [[Boolean Type]], the code is self-documenting:
> 
> ```C
> timeout = true;
> ```
> 
> The meaning of this statement is perfectly clear.

## Syntax Design

The [[Syntax]] (the form) of a language's elements has a significant effect on the [[Readability]] of programs.

### Special Words and Compound Statements

Program appearance is strongly influenced by the form of a language’s **special words** (e.g., `while`, `class`, `for`).

- **Compound Statements:** The method for forming statement groups (especially in [[Control Structures]]) is critical.

    - **C-style (Braces):** [[C]] and its descendants (like [[C++]] and [[Java]]) use braces (`{ ... }`) to define compound statements.

        - _Problem:_ This can diminish readability because the closing brace `}` is always the same. It is difficult to determine _which_ group (e.g., `if`, `while`, `for`) is being ended.

    - **Ada-style (Distinct Closers):** [[Ada]] and [[Fortran 95]] use a distinct closing syntax for each type of statement group.

        - _Example:_ [[Ada]] uses `end if` to terminate a selection construct and `end loop` to terminate a loop construct. This is much clearer.

- **The Readability vs. Simplicity Trade-off:**

    - **Fewer Words (e.g., Java):** This leads to a simpler language (fewer [[Reserved Words]]) but can be less readable.

    - **More Words (e.g., Ada):** This is more readable but adds complexity by increasing the number of [[Reserved Words]].

- **Special Words as Variable Names:**

    - Readability is **severely** harmed if special words ([[Keywords]]) can also be used as variable names.

    - _Example:_ In [[Fortran 95]], `Do` and `End` are legal variable names. This creates ambiguity, as the appearance of `Do` might be the start of a loop _or_ just a variable.

### Form and Meaning

A key principle of good syntax design is that **semantics (meaning) should follow directly from syntax (form)**. The appearance of a statement should at least partially indicate its purpose.

This principle is violated when two language constructs look similar or identical but have different meanings based on context.

- **Example of Context-Dependent Meaning:** The `static` keyword in [[C]].

    - **Inside a function:** `static int x;`

        - _Meaning:_ The variable is created at compile time and retains its value between function calls ([[Static Local Variable]]).

    - **Outside all functions:** `static int x;`

        - _Meaning:_ The variable is visible _only_ in the file in which it is defined (it has internal linkage).

- **Example of Opaque Form:** The [[UNIX]] shell command `grep`.

    - Its appearance connotes nothing to a beginner.

    - Its meaning comes from an obscure command in the `ed` editor: `g/regular_expression/p`, which means "**g**lobal search for **r**egular **e**xpression and **p**rint the line."

    - This is an example of syntax that does _not_ suggest its semantics.