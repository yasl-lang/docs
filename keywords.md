# Keywords

YASL reserves the following keywords, which may not be used as identifiers:

* assert
* break
* const
* continue
* echo
* else
* elseif
* export
* false
* fn
* for
* if
* len
* let
* match
* return
* true
* undef
* while

Additionally, the keywords `header`, `global`, `enum`, `yield`, `do`, `use`, `no`, `pure`, `consteval`, `constexpr`, `constfold`, `extern`, `struct`, `pragma`, `ifdef`, `elseifdef`, and `in` are reserved for possible future use and may not be used as identifiers.

# assert
An [assert statement](https://yasl-lang.github.io/docs/statements/assert) will check that the given expression is truthy. If it is, program execution proceeds as normal. If not, a fatal error happens and program execution is halted.

# break 
`break` exits from a `while` or `for` loop, skipping all remaining iterations.

# const
`const` is used in variable declarations to make it impossible to reassign a variable. Note that the variable is still mutable if it is a mutable type.

# continue
`continue` skips the current iteration of a `while` or `for` loop, resuming at the next iteration.

# echo
`echo` is `echo` statements, which log a value to stdout.

# else
`else` is used in `if` statements to denote a block that is executed if the condition is false.

# elseif
`elseif` is used in `if` statements to denote a block that is executed if the previous condition if false, and the current condition is true.

# false
Literal boolean `false`.

# fn
`fn` is used to declare functions.

# for
`for` is used to start a `for` loop, or in list and table comprehensions to introduce the iteration variable(s).

# if
`if` is used in `if` statements, or in list and table comprehensions to introduce a condition to filter the list with.

# let
`let` is used for variable declarations.

# len
`len` is the length operator.

# match
`match` is used in match statements.

# return
`return` is used in function declarations to return a value.

# true
Literal boolean `true`.

# undef
Literal `undef`.

# while
`while` is used to introduce `while` loops.
