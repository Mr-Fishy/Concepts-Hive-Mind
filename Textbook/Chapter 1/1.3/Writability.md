#Writability is a measure of how easily a language can be used to create programs for a chosen [[Problem Domain]].

- **Relationship to Readability:** Most language characteristics that affect [[Readability]] also affect [[Writability]]. This is because the process of writing code requires the programmer to frequently re-read the parts of the program they have already written.

- **Context is Critical:** Like readability, writability _must_ be considered in the context of the language's target [[Problem Domain]].

    - **Example:**
        - [[Visual BASIC]] has high writability for [[GUI]] applications.

        - [[C]] has high writability for [[Systems Programming]].

        - It is not fair to compare them outside of their intended domains (e..g, [[C]] is poor for GUIs, and [[VB]] is poor for writing an operating system).

The following subsections describe the most important characteristics that influence a language's [[writability]].

## Simplicity and Orthogonality

These two characteristics have a complex, and sometimes conflicting, relationship with writability.

- **The Case for Simplicity:**
    - If a language has a large number of constructs, programmers may not be familiar with all of them.

    - This leads to **misuse** of some features and **disuse** of other, potentially more elegant or efficient, features.

    - As noted by [[C.A.R. Hoare]] (1973), it may even be possible to use unknown features _accidentally_, leading to bizarre results.

    - **Conclusion:** A smaller number of primitive constructs and a consistent set of combination rules ([[Orthogonality]]) is better than a large number of primitives.

- **The Problem with _Too Much_ Orthogonality:**
    - Extreme orthogonality can be a **detriment** to writability.

    - If nearly _any_ combination of primitives is legal, the [[Compiler]] cannot detect many common errors.

    - This can lead to "code absurdities" that are syntactically legal but semantically wrong, harming [[Reliability]].

## Expressivity

**Expressivity** refers to how conveniently and powerfully a language can specify computations.

There are two common meanings:

1. **Powerful Operators:** In a language like [[APL]], this means having very powerful operators that can accomplish a large amount of computation with a very small program.

2. **Convenience (More Common):** This means having relatively convenient, rather than cumbersome, ways of specifying computations.

    - **Example:** In [[C]], `count++` is a more convenient and shorter notation than `count = count + 1`.

    - **Example:** The `and then` [[Boolean Operator]] in [[Ada]] provides a convenient syntax for [[Short-Circuit Evaluation]].

    - **Example:** The `for` statement in [[Java]] makes writing counting loops easier than using a `while` statement.


All of these convenient features increase the [[Writability]] of a language.
