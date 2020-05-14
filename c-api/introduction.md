# Introduction to YASL's C API

YASL can be embedded into a C or C++ program through its API. All API functions and types are defined in `yasl.h`. 
Additional functions are also defined in `yasl_aux.h`; these do not add any functionality on top of those found in `yasl.h`,
they merely provide convinient functions for common patterns in order to reduce boilerplate.

As with most C libraries, the YASL API functions generally do not check their arguments for consistency or validity.

The YASL library is fully reentrant. It has no global variables; everything is kept in a dynamic structure, called the 
_YASL state_ (represented by `struct YASL_State`).

A pointer to a YASL state must be passed to most functions in the C API, except for a `YASL_newstate`, which creates and 
initializes a new YASL state.

## The Stack
A YASL_State has a stack which is used to pass values between YASL and C. Each element on the stack represents a value in 
YASL. API functions work by accessing and modifying this stack.

## Example Program
As an example, let's consider declaring a YASL value through the API (called `answer`), and assign it a value (`42`).

`example.yasl`:
```
# just print out the variable `answer`, which was declared and initialized through the API.
echo answer

```

`example.c`:
```
#include "yasl.h"

int main(void) {
    // make a new YASL state, loaded with `example.yasl`
    struct YASL_State *S = YASL_newstate("example.yasl");
    
    // declare a variable `answer`
    YASL_declglobal(S, "answer");
    
    // push `42` onto the stack
    YASL_pushint(S, 42);
    
    // init `answer` with the top of the stack (in this case, the `42` we just pushed)
    YASL_setglobal(S, "answer");
    
    // execute `example.yasl`, now that we're done setting everything up
    YASL_execute(S);
    
    // clean up
    YASL_delstate(S);
}
```

The above should print out `42`.

