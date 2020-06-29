# Built-in Functions

YASL has to following built-in functions. Note that these are all attached to the metatables for certain types. 
So to call `int.tofloat` on something of type `int`, if `x` was an `int` value, one would type `x.tofloat(x)`.
As short-hand for this, you can also type `x->tofloat()`, which is exactly the same as `x.tofloat(x)`. 
This notation can be used for all functions listed below.

Operators for non-numeric types are also included here.

## Undef Functions

| Name       | Arguments | Description |
|------------|-----------|-------------|
| tostr      | self      | converts _self_ to a str value. |

## Float Functions

| Name       | Arguments | Description |
|------------|-----------|-------------|
| toint      | self      | converts _self_ to an int value, truncating if necessary. |
| tobool     | self      | converts _self_ to a bool value. |
| tostr      | self      | converts _self_ to a str value. |
| tofloat    | self      | return _self_. |

## Int Functions

| Name       | Arguments | Description |
|------------|-----------|-------------|
| tofloat    | self      | converts _self_ to an float value, rounding to nearest float if necessary if necessary. |
| tobool     | self      | converts _self_ to a bool value. |
| toint      | self      | return _self_. |
| tostr      | self      | converts _self_ to a str value. |

## Bool Functions

| Name       | Arguments | Description |
|------------|-----------|-------------|
| tostr      | self      | converts _self_ to a str value. |
| tobool     | self      | returns _self_. |

## Str Functions

| Name       | Arguments | Description |
|------------|-----------|-------------|
| tofloat    | self      | converts _self_ to a float value, returning nan if unable to parse a float. |
| toint      | self      | converts _self_ to an int value, returning nan if unable to parse an int. |
| isalnum    | self      | returns true if _self_ consists only of alphanumeric characters, else false. |
| isal       | self      | returns true if _self_ consists only of alphabetic characters, else false. |
| isnum      | self      | returns true if _self_ consists only of numeric characters, else false. |
| isspace    | self      | returns true if _self_ consists only of whitespace characters, else false. |
| tobool     | self      | converts _self_ to a boolean value, based on the [Truthines](/docs/control-flow/truthiness) of _self_. |
| tostr      | self      | returns _self_. |
| toupper    | self      | returns a new str that is an uppercase version of _self_. |
| tolower    | self      | returns a new str that is a lowercase version of _self_. |
| startswith | self, substr | returns true if _self_ starts with _substr_, else false. |
| endswith   | self, substr | returns true if _self_ ends with _substr_, else false. |
| replace    | self, substr, replstr | returns a copy of _self_ with all instances of _substr_ replaced with _replstr_. |
| search     | self, substr | returns the index of the first instance of _substr_ in _self_, else returns undef. |
| count      | self, substr | returns the number of times _substr_ occurs in _self_. |
| split      | self, substr | returns a list formed from splitting _self_ at every instance of _substr_. If _substr_ is not supplied, split on all white space. |
| ltrim      | self, substr | trims all _substr_ instances from left of _self_. If _substr_ is not provided, trim all white space from the left instead. |
| rtrim      | self, substr | trims all _substr_ instances from right of _self_. If _substr_ is not provided, trim all white space from the right instead. |
| trim       | self, substr | trims all _substr_ instances from both sides of _self_. If _substr_ is not provided, trim all white space from both sides instead. |
| rep        | self, n   | makes a new string that is a _n_ copies of _self_. |

| Operator | Operands | Description |
|----------|----------|-------------|
| len      | self     | returns the number of characters in _self_. |
| []       | self, index | returns the substring of _self_ of length 1 at _index_. |
| [:]      | self, start, end | returns the substring of _self_ from _start_ (inclusive) to _end_ (exclusive). |

## List Functions

| Name       | Arguments | Description |
|------------|-----------|-------------|
| push       | self, val | puts _val_ at end of _self_. |
| copy       | self      | returns a copy of _self_. |
| pop        | self      | removes last element of _self_ and returns it. |
| tostr      | self      | converts _self_ to a str value. |
| search     | self      | returns the index of the first instance of substr in _self_, else returns undef. |
| reverse    | self      | reverses _self_ in-place. |
| clear      | self      | removes all values from _self_. |
| join       | self, delim | joins all elements of _self_ together, using _delim_ to delimite them. |
| sort       | self      | sorts _self_, alphabetically for list of strings and numerically for list of numbers. |

| Operator | Operands | Description |
|----------|----------|-------------|
| len      | self     | returns the number of items in _self_. |
| []       | self, index | returns the value of _self_ at _index_. |
| []       | self, index, val | updates the value of _self_ at _index_ to _val_. |
| [:]      | self, start, end | returns a new list based on _self_ from _start_ (inclusive) to _end_ (exclusive). |
| +        | left, right | concatenates _left_ and _right_ into a new list. |
 
## Table Functions

| Name       | Arguments | Description |
|------------|-----------|-------------|
| keys       | self      | returns a list containing all the keys in _self_. |
| values     | self      | returns a list containing all the values in _self_. |
| copy       | self      | returns a copy of _self_. |
| tostr      | self      | converts _self_ to a str value. |
| clear      | self      | removes all values from _self_. |
| remove     | self, key | removes the _key_ and its associated value from _self_. Does nothing if _key_ is not present. |

| Operator | Operands | Description |
|----------|----------|-------------|
| len      | self     | returns the number of key-value pairs in _self_. |
| \|       | left, right | returns the union of _left_ and _right_ based on keys, taking the value from _right_ if any keys overlap. |
| []       | self, index | returns the value of _self_ at _index_. |
| []       | self, index, val | updates the value of _self_ at _index_ to _val_. |
