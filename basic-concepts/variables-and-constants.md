# Variables and Constants

## Variables
Variables are places to store values. They can be declared with the following syntax:

`"let" ID [ "=" expr ]`,

where `ID` is any valid identifier (`[A-Za-z_$][A-Za-z0-9_$]*` i.e. alphanumerics, underscores, and dollar-signs, and not starting with a number) and `expr` is any valid expression. If an expression is not given, the variable is initialized to `undef`.

examples:
```
let x = 64  # declare new variable x, set its value to 64
let y  # declare new variable y; its value is implicitly set to undef
```

## Constants
Constants are similar to variables, but the value cannot be reassigned once it has been set. Note that if the value set is mutable, such as a list or an array, it can still be mutated. Constants can be declared and initialized with the following syntax:

`"const" ID "=" expr`.

Note that constants must be initialized, unlike variables. 

examples:
```
const pi = 3.14159  # declare new constant pi, set its value to 3.14159. trying to reassign pi is an error
const tau  # error, because tau was not initialised
```
