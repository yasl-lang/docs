# Built-in Functions

YASL has to following built-in functions. Note that these are all attached to the metatables for certain types. 
So to call `int.tofloat` on something of type `int`, if `x` was an `int` value, one would type `x.tofloat(x)`.
As short-hand for this, you can also type `x->tofloat()`, which is exactly the same as `x.tofloat(x)`. 
This notation can be used for all functions listed below.

## Float Functions

| Name       | Arguments | Description |
|------------|-----------|-------------|
| toint      | self      | converts self to an int value, truncating if necessary |
| tostr      | self      | converts self to a str value |

## Int Functions

| Name       | Arguments | Description |
|------------|-----------|-------------|
| tofloat    | self      | converts self to an float value, rounding to nearest float if necessary if necessary |
| tostr      | self      | converts self to a str value |

## Bool Functions

| Name       | Arguments | Description |
|------------|-----------|-------------|
| tostr      | self      | converts self to a str value |

## Str Functions

| Name       | Arguments | Description |
|------------|-----------|-------------|
| tofloat    | self      | converts self to a float value, returning nan if unable to parse a float |
| tointt     | self      | converts self to an int value, returning nan if unable to parse an int |
| isalnum    | self      | returns true if self consists only of alphanumeric characters, else false |
| isal       | self      | returns true if self consists only of alphabetic characters, else false |
| isnum      | self      | returns true if self consists only of numeric characters, else false |
| isspace    | self      | returns true if self consists only of whitespace characters, else false |
| tobool     | self      | converts self to a boolean value, based on the [Truthines](/docs/control-flow/truthiness) of self |
| tostr      | self      | returns self |
| startswith | self, substr | returns true if self starts with substr, else false |
| endswith   | self, substr | returns true if self ends with substr, else false |
| replace    | self, substr, replstr | returns a copy of self with all instances of substr replaced with replstr |
| search     | self, substr | returns the index of the first instance of substr in str, else returns undef |
| split      | self, substr | returns a list formed from splitting self at every instance of substr |
| ltrim      | self, substr | trims all substr instances from left of self |
| rtrim      | self, substr | trims all substr instances from right of self |
| trim       | self, substr | trims all substr instances from both sides of self |
| slice      | self, start, end | makes a new string that is a substring of self from start to end |
| repeat     | self, n   | makes a new string that is a n copies of self |

## List Functions

| Name       | Arguments | Description |
|------------|-----------|-------------|
| push       | self, val | puts val at end of self |
| copy       | self      | returns a copy of self |
| extend     | self, ls  | extends self by adding all elements of ls to the end of self |
| pop        | self      | removes last element of self and returns it |
| search     | self      | returns the index of the first instance of substr in str, else returns undef |
| reverse    | self      | reverses self in-place |
| slice      | self, start, end | makes a new list containing the elements in self from start to end |

## Table Functions


| Name       | Arguments | Description |
|------------|-----------|-------------|
| keys       | self      | returns a list containing all the keys in self |
| values     | self      | returns a list containing all the values in self |
| copy       | self      | returns a copy of self |


