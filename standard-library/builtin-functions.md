# Built-in Functions

YASL has to following built-in functions. Note that these are all attached to the metatables for certain types. 
So to call `int.tofloat` on something of type `int`, if `x` was an `int` value, one would type `x.tofloat(x)`.
As short-hand for this, you can also type `x->tofloat()`, which is exactly the same as `x.tofloat(x)`. 
This notation can be used for all functions listed below.

Operators for non-numeric types are also included here.

## Undef Functions

| Name       | Arguments | Description |
|------------|-----------|-------------|
| tostr      | self      | converts self to a str value |

## Float Functions

| Name       | Arguments | Description |
|------------|-----------|-------------|
| toint      | self      | converts self to an int value, truncating if necessary |
| tobool     | self      | converts self to a bool value |
| tostr      | self      | converts self to a str value |
| tofloat    | self      | return self |

## Int Functions

| Name       | Arguments | Description |
|------------|-----------|-------------|
| tofloat    | self      | converts self to an float value, rounding to nearest float if necessary if necessary |
| tobool     | self      | converts self to a bool value |
| toint      | self      | return self |
| tostr      | self      | converts self to a str value |

## Bool Functions

| Name       | Arguments | Description |
|------------|-----------|-------------|
| tostr      | self      | converts self to a str value |
| tobool     | self      | returns self |

## Str Functions

| Name       | Arguments | Description |
|------------|-----------|-------------|
| tofloat    | self      | converts self to a float value, returning nan if unable to parse a float |
| toint      | self      | converts self to an int value, returning nan if unable to parse an int |
| isalnum    | self      | returns true if self consists only of alphanumeric characters, else false |
| isal       | self      | returns true if self consists only of alphabetic characters, else false |
| isnum      | self      | returns true if self consists only of numeric characters, else false |
| isspace    | self      | returns true if self consists only of whitespace characters, else false |
| tobool     | self      | converts self to a boolean value, based on the [Truthines](/docs/control-flow/truthiness) of self |
| tostr      | self      | returns self |
| toupper    | self      | returns a new str that is an uppercase version of self |
| tolower    | self      | returns a new str that is a lowercase version of self |
| startswith | self, substr | returns true if self starts with substr, else false |
| endswith   | self, substr | returns true if self ends with substr, else false |
| replace    | self, substr, replstr | returns a copy of self with all instances of substr replaced with replstr |
| search     | self, substr | returns the index of the first instance of substr in str, else returns undef |
| count      | self, substr | returns the number of times substr occurs in self |
| split      | self, substr | returns a list formed from splitting self at every instance of substr |
| ltrim      | self, substr | trims all substr instances from left of self |
| rtrim      | self, substr | trims all substr instances from right of self |
| trim       | self, substr | trims all substr instances from both sides of self |
| rep        | self, n   | makes a new string that is a n copies of self |

| Operator | Operands | Description |
|----------|----------|-------------|
| len      |          | self        | returns the number of characters in self |
| []       | self, index | returns the substring of self of length 1 at index |
| [:]      | self, start, end | returns the substring of self from start (inclusive) to end (exclusive) |

## List Functions

| Name       | Arguments | Description |
|------------|-----------|-------------|
| push       | self, val | puts val at end of self |
| copy       | self      | returns a copy of self |
| extend     | self, ls  | extends self by adding all elements of ls to the end of self |
| pop        | self      | removes last element of self and returns it |
| tostr      | self      | converts self to a str value |
| search     | self      | returns the index of the first instance of substr in str, else returns undef |
| reverse    | self      | reverses self in-place |
| clear      | self      | removes all values from self |
| join       | self, delim | joins all elements of self together, using delim to delimite them |
| sort       | self      | sorts self, alphabetically for list of strings and numerically for list of numbers |

| Operator | Operands | Description |
|----------|----------|-------------|
| len      | self     | returns the number of items in self |
| []       | self, index | returns the value of self at index |
| []       | self, index, val | updates the value of self at index to val |
| [:]      | self, start, end | returns a new list based on self from start (inclusive) to end (exclusive) |
| +        | left, right | concatenates left and right into a new list |
 
## Table Functions

| Name       | Arguments | Description |
|------------|-----------|-------------|
| keys       | self      | returns a list containing all the keys in self |
| values     | self      | returns a list containing all the values in self |
| copy       | self      | returns a copy of self |
| tostr      | self      | converts self to a str value |
| clear      | self      | removes all values from self |
| remove     | self, key | removes the key and its associated value from self. does nothing if key is not present.

| Operator | Operands | Description |
|----------|----------|-------------|
| len      | self     | returns the number of key-value pairs in self |
| \|       | left, right | returns the union of left and right based on keys, taking the value from right if any keys overlap |
| []       | self, index | returns the value of self at index |
| []       | self, index, val | updates the value of self at index to val |
