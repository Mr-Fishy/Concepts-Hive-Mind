#imperative languages are abstractions of #von-Nuemann architecture
- Memory
- Processor

#variable's are characterized by #attribute's
- To design a type
- Must consider scope
- Lifetime
- Type checking
- Initialization
- Type compatibility

## #name's
Design issues for names:

### Can names be any length?
If it is too short, they can be connotative
Examples:
- C99: no limit but only the first 63 are significant

### Are names case sensitive?
Usually yes.

Disadvantage: readability (names that look alike are different)
- Names in the C-based languages are case sensitive
- Names in others are not
- Worse in C++, Java, and C# because predefined names are mixed case (e.g. IndexOutOfBoundsException)


### Are special words reserved words or keywords?
- An aid to readability; used to delimit or separate statement clauses
- A keyword is a word that is special only in certain contexts, have special meaning in the language
- A reserved word is a special word that cannot be used as a user-defined identifier
- In practice: keyword = reserved word
- Potential problem with reserved words: If there are too many, many collisions occur (e.g., COBOL has 300 reserved words)

### Special characters
- PHP: All variable names must begin with dollar signs
- Perl: All variable names begin with special characters, which specify the variable's type
- Ruby: Variable names that begin with @ are instance variables; those that begin with @@ are class variables

### "Standard Library" Names
- Once `<iostream>` is included and the name is in use, `cout` can be used as a user defined identifier / name but with potential problems
- Once `java.util.ArrayList` 
