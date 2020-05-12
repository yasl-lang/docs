# Operators

YASL supports a wide range of operators. A table listing them all, along with their precendence, can be found [here](/docs/expressions/operator-precedence-table). Below is a more in-depth description of each operator.

## Arithmetic Operators
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

Float division always returns a _float_. Integer division and modulo are only defined for _int_ values. All other arithmetic operators return an _int_ if both operands are _int_, otherwise it returns a _float_.

## Bitwise Operators
YASL supports the following bitwise operators:

* **\|** bitwise or
* **^** bitwise xor
* **&** bitwise and
* **&^** bitwise and-not
* **\<\<** bitshift left
* **\>\>** bitshift right
* **^** bitwise negation

All bitwise operators are only defined for _int_ operands, and return an _int_.

## Logical Operators
YASL supports the following logical operators:

* **\|\|** logical or
* **&&** logical and
* **!** logical negation

All logical operators can be used with any value, treating all falsey values as false and all truthy values as true. Logical and and logical or short circuit, and return either the left or right operand depending on [Truthiness](/docs/control-flow/truthiness).

## Comparison Operators
YASL supports the following comparison operators:

* **\<** less than
* **\>** greater than
* **\>=** greater than or equal to
* **\<=** less than or equal to
* **==** equals
* **!=** not equals
* **===** strict equals
* **!==** strict not equals

The ordering operators (**\<**, **\>**, **\>=**, **\<==**) are defined for strings and numbers.

The equality operator (**==**) compares by value. It coerces _int_s to _float_s if needed. Otherwise, no coercions are done. `undef == undef` is false.

The strict equality operator compares by identity. For scalar types, it behaves the same as **==**, except it compares `undef === undef` as `true` rather than `false`, and will not coerce between numeric types. For _list_s, _table_s, _str_s, etc, it returns true iff the two objects compared are the object in memory.

## Length Operator
The length operator **len** is defined for _str_ (returning the length), _list_ (returning the length) and _table_ (returning the number of elements).

## Concatenation Operator
The concatenation operator **~** concatenates its two operands, turning each to a string first if it is not already a string.

## Ternary Operator
The ternary operator takes 3 arguments of any type, and returns the second if the first is truthy, otherwise it returns the third.

## Undef Coalescing Operator
The undef coalescing operator **??** returns the left operand if it is not _undef_, otherwise it returns the right operand. This can be useful for setting default values or checking if a value has been defined.
