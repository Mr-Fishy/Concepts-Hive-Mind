The total #cost of a programming language is a function of many of its characteristics. 

First, there is the cost of training to use the language, which is a function of the [[Simplicity]] and [[Orthogonality]] of the language and the experience of the programmers. Although more powerful languages are not necessarily more difficult to learn, they often are.

Second, there is the cost of writing programs in the language. This is a function of the [[Writability]] of the language, which depends in part on the closeness in purpose to the particular application. The original efforts to design and implement high-level languages were driven by the desire to lower the costs of creating software.

Both the cost of training and writing programs in a language can be significantly reduced in a good programming environment. Which are discussed in [[1.8]].

Third, the cost of executing programs written in a language is greatly influenced by that language's design. A language that requires many #runtime type checks will reduce code execution, regardless of the quality of the #compiler.  Early on, #execution-efficiency was the foremost concern in language design, now it is considered to be less important.

Fourth, there is the cost of poor [[Reliability]]. If the software fails in a critical system, such as a nuclear power plant, bad things happen and it can be very costly.

The final consideration is the cost of maintaining the programs, which includes both corrections and modifications to add new functionality. The cost of software maintenance depends on a number of languages characteristics, primarily [[Readability]].

Alternative criteria:
* #Portability: The ease with which programs can be moved from one implementation to another. 

* #Generality: The applicability to a wide range of applications.

* #Well-definedness: The completeness and precision of the languages official defining document.

Most criteria, particularly [[Readability]], [[Writability]], and [[Reliability]], are neither precisely defined nor accurately measurable. 

Language design criteria are weighed differently from different perspectives. 
- Language implementors are concerned primarily with the difficulty of implementing the #constructs and features of the language. 

- Language users are worried about [[Writability]] first and [[Readability]] later. 

- Language designers are likely to emphasize elegance and the ability to attract widespread use.

These characteristics often conflict with one another.