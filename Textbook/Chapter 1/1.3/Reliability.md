---
tags: programming-languages, reliability, Sebesta/Chapter-1
---
A program is said to be **reliable** if it performs to its specifications under all conditions. Reliability is affected by several language features.

## Type Checking

[[Type Checking]] is the process of testing for type errors in a program, either by the [[Compiler]] ([[Compile-Time Type Checking]]) or during program execution ([[Run-Time Type Checking]]).

- **Impact on Reliability:** Type checking is a major factor in language reliability.

- **Compile-Time vs. Run-Time:**
    - Run-time type checking is expensive (it adds overhead to the execution).

    - **Compile-time type checking** is more desirable.

    - The earlier errors are detected, the less expensive they are to fix.

- **Example (Good):** [[Java]] requires compile-time type checks for nearly all variables and expressions, virtually eliminating type errors at run time.

- **Example (Bad):** The original [[C]] language (K&R C).
    - **Problem:** The type of an actual parameter in a function call was _not_ checked against the type of the formal parameter in the function definition.

    - **Scenario:** A programmer could pass an `int` variable (e.g., `23`) to a function that expected a `float`.

    - **Consequence:** The bit string representing the integer `23` is completely different from the bit string representing the floating-point `23`. Any use of that parameter within the function would produce nonsense.

    - **Result:** These errors were extremely difficult to diagnose.

    - **Solution:** Modern [[C]] standards require this type checking. The [[lint]] utility was also created for UNIX to check C programs for these and other issues.

## Exception Handling

[[Exception Handling]] is a language facility that allows a program to intercept run-time errors (and other unusual conditions), take corrective measures, and then continue execution.

- **Impact on Reliability:** This is an obvious aid to reliability, as it prevents programs from simply crashing.

- **Languages with Exception Handling:** [[Ada]], [[C++]], [[Java]], [[C#]].

- **Languages without Exception Handling:** [[C]] (and other early languages).

## Aliasing

**Aliasing** is loosely defined as having two or more distinct names in a program that can be used to access the **same memory cell**.

- **Impact on Reliability:** Aliasing is now generally accepted as a **dangerous** feature.

- **Common Example:** Having two [[Pointers]] (or references) that point to the same variable. A programmer must _always_ remember that changing the value through `pointer1` also changes the value accessed through `pointer2`.

- **Trade-off:**
    - Some languages allow aliasing to overcome deficiencies in [[Data Abstraction]].

    - Other languages restrict aliasing to increase their reliability.

## Readability and Writability

Both [[Readability]] and [[Writability]] have a direct influence on [[Reliability]].

- **Writability and Reliability:**
    
    - If a language does not support natural ways to express an algorithm, the programmer must use an unnatural approach.

    - Unnatural approaches are less likely to be correct for all possible situations.

    - Therefore, the easier a program is to write, the more likely it is to be correct.

- **Readability and Reliability:**
    - Readability affects reliability during both the initial writing and the [[Software Maintenance]] phases.

    - Programs that are difficult to read are difficult to write correctly and difficult to modify correctly.
