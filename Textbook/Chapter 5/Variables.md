- A #variable is an an abstraction of a memory cell
- Variables can be characterized as a sextuple of attributes:
	- #name - Not all variables have them
	- #address - The memory address with which it is associated
		- A variable may have different addresses at different times during execution
			`For example during recursive functions, variables of the same name can have different instances. `
		- If two variable names can be used to access the same memory location, they are called #aliases
		- Aliases are created via pointers, reference variables, C and C++ unions (see union-test.cpp, ref #CH6)
		- Aliases are harmful to readability (program readers must remember all of them)
	- #value
		- The contents of the location with which the variable is associated.
			- The `I-Value` of a variable is its address
			- The `R-Value` of a variable is its value
	- #type
		- Determines the range of values of variables and the set of operations that are defined for values of that type; in the case of floating point, type also determines the precision.
		- The type can be used to "constrain" how that memory can be used. Such as limits, value types, and other forms of how the data can be used.
	- #lifetime
	- #scope

*`Abstract Memory Cell`* - The physical cell or collection of cells associated with a variable (i.e., the `int` type in C++, its abstract memory cell has 4 bytes)

A #binding is an **association between an entity and an attribute**, such as between a variable and its type or value, or between an operation and a symbol.
* *Binding time* is the time at which a binding takes place.

Possible Binding Times
- Language design time -- bind operator symbols to operations
- Language implementation time -- bind floating point type to a representation (IEEE 754)
- Compile time -- bind a variable to a type in C or Java
- Load time -- bind a C or C++ static variable to a memory cell
- Runtime -- bind a non-static local variable to a memory cell

