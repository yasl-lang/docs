# Keywords

YASL reserves the following keywords, which may not be used as identifiers:

* break
* const
* continue
* do
* else
* elseif
* enum
* false
* fn
* for
* if
* in
* inf
* let
* nan
* no
* print
* require
* return
* true
* undef
* use
* while
* yield

# break 
`break` exits from a `while` or `for` loop, skipping all remaining iterations.

# const
`const` is used in variable declarations to make it impossible to reassign a variable. Note that the variable is still mutable if it is a mutable type.

# continue
`continue` skips the current iteration of a `while` or `for` loop, resuming at the next iteration.

# do
Currently unused, but reserved for future use.

# else
`else` is used in `if` statements to denote a block that is executed if the condition is false.

# elseif
`elseif` is used in `if` statements to denote a block that is executed if the previous condition if false, and the current condition is true.

# enum
Currently unused, but reserved for future use.

# false
Literal boolean `false`.

# fn
`fn` is used to declare functions.

# for
`for` is used to start a `for` loop, or in list and table comprehensions to introduce the iteration variable(s).

# if
`if` is used in `if` statements, or in list and table comprehensions to introduce a condition to filter the list with.

# in
`in` is used in `for` loops and comprehensions to separate the iteration variable from the list/table being iterated over.

# inf
Literal infinity.

# let
`let` is used in variable declarations.

# nan
Literal NaN.

# no
Currently unused, but reserved for future use.

# print
`print` is used in `print` statements.

# require
Currently unused, but reserved for future use.

# return
`return` is used in function declarations to return a value.

# true
Literal boolean `true`.

# undef
Literal `undef`.

# use
Currently unused, but reserved for future use.

# while
`while` is used to introduce `while` loops.

# yield
Currently unused, but reserved for future use.
