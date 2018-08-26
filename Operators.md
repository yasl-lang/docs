YASL supports a wide range of operators. A table listing them all, along with their precendence, can be found [[here|Operator Precedence Table]]. Below is a more in-depth description of each operator.

# Arithmetic Operators
 YASL supports the following arithmetic operators:

* **+**  addition
* **-** subtraction
* **\*** multiplication
* **/** float division
* **//** integer division
* **%** modulo
* **\*\*** exponentiation
* **+** unary plus
* **-** unary minus

Float division always returns a _float64_. Integer division and modulo are only defined for _int64_ values. All other arithmetic operators return an _int64_ if both operands are _int64_, otherwise it returns a _float64_.

# Bitwise Operators
YASL supports the following bitwise operators:

* **|** bitwise or
* **^** bitwise xor
* **&** bitwise and
* **<<** bitshift left
* **>>** bitshift right
* **^** bitwise negation

All bitwise operators are only defined for _int64_ operands, and return an _int64_.

# Logical Operators
YASL supports the following logical operators:

* **||** logical or
* **&&** logical and
* **!** logical negation

All logical operators can be used with any value, treating all falsey values as false and all truthy values as true. Logical and and logical or short circuit, and return either the left or right operand depending on [[truthiness|Truthiness]].

# Length Operator
The length operator **#** is defined for _str_ (returning the length), _list_ (returning the length) and _table_ (returning the number of elements).

# Concatenation Operator
The concatenation operator **~** is defined for _str_ operands, returning the result of concatenating the two strings, and _list_ operands, returning the result of concatenating the two lists.

# Ternary Operator
The ternary operator takes 3 arguments of any type, and returns the second if the first is truthy, otherwise it returns the third.

# Undef Coalescing Operator
The undef coalescing operator **??** returns the left operand if it is not _undef_, otherwise it returns the right operand. This can be useful for setting default values or checking if a value has been defined.