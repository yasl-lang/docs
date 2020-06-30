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
`break` exits from a [`while` or `for` loop](https://yasl-lang.github.io/docs/control-flow/control-flow), skipping all remaining iterations.

# const
`const` is used in [variable declarations](https://yasl-lang.github.io/docs/basic-concepts/variables-and-constants) to make it impossible to reassign a variable. Note that the variable is still mutable if it is a mutable type.

# continue
`continue` skips the current iteration of a [`while` or `for` loop](https://yasl-lang.github.io/docs/control-flow/control-flow), resuming at the next iteration.

# echo
An [echo statement](https://yasl-lang.github.io/docs/statements/echo) is used to log a value to standard out.

# else
`else` is used in [`if` statements](https://yasl-lang.github.io/docs/control-flow/control-flow) to denote a block that is executed if the condition is [falsey](https://yasl-lang.github.io/docs/control-flow/truthiness).

# elseif
`elseif` is used in [`if` statements](https://yasl-lang.github.io/docs/control-flow/control-flow) to denote a block that is executed if the previous condition if falsey, and the current condition is truthy.

# false
Literal boolean `false`.

# fn
`fn` is used to [declare functions](https://yasl-lang.github.io/docs/statements/functions).

# for
`for` is used to start a [`for` loop](https://yasl-lang.github.io/docs/control-flow/control-flow), or in [list and table comprehensions](https://yasl-lang.github.io/docs/expressions/comprehensions) to introduce the iteration variable(s).

# if
`if` is used in [`if` statements](https://yasl-lang.github.io/docs/control-flow/control-flow), or in [list and table comprehensions](https://yasl-lang.github.io/docs/expressions/comprehensions) to introduce a condition to filter the list with.

# let
`let` is used for [variable declarations](https://yasl-lang.github.io/docs/basic-concepts/variables-and-constants).

# len
`len` is the [length operator](https://yasl-lang.github.io/docs/expressions/operators#length-operator).

# match
`match` is used in [match statements](https://yasl-lang.github.io/docs/control-flow/control-flow).

# return
`return` is used in [function declarations](https://yasl-lang.github.io/docs/statements/functions) to return a value.

# true
Literal boolean `true`.

# undef
Literal `undef`.

# while
`while` is used to introduce [`while` loops](https://yasl-lang.github.io/docs/control-flow/control-flow).
