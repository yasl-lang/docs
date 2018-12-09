# Style Guide for contributing to YASL

## `#include` order
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

## integral and floating point values in YASL
Whenever a floating point or integral type is used that represents a int or float within the YASL language, `yasl_float` or `yasl_int` should be used to represent it.

For example:
`yasl_int val = YASL_GETINT(obj)`, rather than `int64_t val = YASL_GETINT(obj)`.

## typedefs
Do not add any new typedefs. You may use any existing typedefs if needed.