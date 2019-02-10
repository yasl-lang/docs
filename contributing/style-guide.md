# Style Guide for contributing to YASL

## `#include` Order
In a `.c` file, first include the corresponding `.h` file, followed by a blank line. 
Then, include anything from the standard C library that is needed, followed by a blank line.
Then, include any other header files from YASL that are needed, followed by a blank line.
Each section should be alphabetical.

In a `.h` file, exclude the first section, but otherwise follow the same format as in a `.c` file.

For example, the following is the includes from `list_methods.c`:

```
#include "list_methods.h"

#include <stdio.h>

#include "list.h"
#include "VM.h"
#include "YASL_Object.h"
#include "yasl_state.h"
```

## Integral and Floating Point Values in YASL
Whenever a floating point or integral type is used that represents a int or float within the YASL language, `yasl_float` or `yasl_int` should be used to represent it.

For example:
`yasl_int val = YASL_GETINT(obj)`, rather than `int64_t val = YASL_GETINT(obj)`.

## `typedef`s
Do not add any new typedefs. You may use any existing typedefs if needed.

## Naming
Struct names should be in upper camel case (e.g. `RefCount`). Variable names should be lower case with no separator or lower snake case (e.g. `refcount` or `ref_count`). Try to match the style used in the particular file. Functions should be lower snake case (e.g. `vm_pop`). There are also other conventions for naming functions; e.g. all functions that operate on the VM start with `vm_`. This last convention must _absolutely_ be followed.

## Brace Placement
Opening brace is always at the end of the the line. Closing brace is on a line of its own, unless the next piece of code continues 
the statement (e.g. `if`-`else` or `do`-`while`).

## Indentation
Indent with _tabs_. A tab is _8_ spaces.

## Placement of Asterisks
Right-align your `*` for pointers, e.g. do `char *s`, _not_ `char* s`. In casts, leave a space between the type and the asterisk(s), as in `(char *)x` rather than `(char*)x`. If there are multiple asterisks, only a space between the type and the first is needed: `(char **)x`.

## Switch Statements
A `switch` and the matching `case`s should be indented the same amount.

## Macros & Enums
Macro names should be in ALL CAPS, unless the macro is function-like, in which case it may be named as though it were a function.

Macros containing multiple statements must be enclosed in a `do`-`while` block:

```
#define macrofun(a, b, c)                       \
        do {                                    \
                if ((a) == 5)                     \
                        do_this((b), (c));          \
        } while (0)
```

Macros that evaluate to expressions should be enclosed in parentheses. Macro arguments should be enclosed in parentheses.

Things to avoid in macros:

1. macros that affect control flow, e.g. including a return statement in a macro.
2. macros that depend on having a local variable with a special name, e.g. `#define FOO(val) bar(index, val)` is bad. You probably want
`#define FOO(index, val) bar(index, val)` instead.

Enums are preferred to macros when definining many related constants. Enums should be named in ALL CAPS. Many exisiting enums use a prefix to denote what they should be used for, for example:
- enums starting with `T_` are for token types, e.g. `T_PLUS` is the token for `+`.
- enums starting with `L_` are for lexer modes, e.g. `L_NORMAL` is the default lexer mode.
- enums starting with `N_` are for AST node types, e.g. `N_IF` is the AST node for `if`-statements.

New enums should follow this style. The one exception is the enum for opcodes, which uses no prefix currently.
