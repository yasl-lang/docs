# Values and Types

YASL is a _dynamically typed_ langauge. This means that variables don't carry any type information; only values do. YASL has the following 10 basic types:
* _undef_
* _bool_
* _int_
* _float_
* _str_
* _list_
* _table_
* _fn_
* _userdata_
* _userptr_

## undef
The _undef_ type has 1 value, **undef**, which is useful mainly because it is different from all other values. It is the default value for a variable if the variable is not given a value during declaration.

## bool
The _bool_ type has 2 values, **true** and **false**, with the expected semantics of booleans.

## int
The _int_ type represents signed, 64-bit, two's complement integers. _int_ literals can be created for base-2 (prefix _0b_ or _0B_ ), base-10 (no prefix), or base-16 (prefix _0x_ or _0X_ ). Note that _int_ literals with leading 0's are interpreted as base-10, not base-8 as in some languages.

Some example integer literals: `0b100`, `0x0A`, `42`.

## float
The _float_ type represents IEEE double precision floating point numbers. _float_ literals must have at least 1 digit both before and after the decimal point, unlike some other languages. Exponential notation is also allowed.

Some example float literals: `1.5`, `2.7`, `1.6e4`.

## str
The _str_ type represents an immutable sequence of ASCII characters. There are four syntaxes for strings in YASL. Single quoted strings allow escape sequences, such as `\n` for a newline. Back quoted strings are interpreted literally, with no escape sequences, so `\n` is interpreted as a backslash followed by an `n`. Double quoted strings allow interpolation, between `#{` and `}` pairs. A dot followed by an identifier is a string containing that identifier name. (i.e. `.x` is the same as `'x'`.)

Some example strings: 
* `"hello, #{name}"` (`#{name}` is replaced with the contents of the variable `name`);
* `'newline: \n'` (`\n` is replaced with a newline character);
* `` `raw string \n` `` (`\n` is a literal backslash followed by a literal `n`);
* `.identifier` (this is the same as `'identifier'`).

## list
The _list_ type represents a resizing array. _list_ values are declared with: `"[" [ {expr "," } expr ] "]"`. Note that no trailing commas are allowed after the last value in a list. _list_ values can be iterated over with for-loops or list/table comprehensions. 

Some example lists:
* `[]` (empty list);
* `[ 1, 2, 3, 4 ]` (simple list containing 1 through 4, inclusive);
* `[ 2*x for x <- [1, 2, 3] ]` (list comprehension; this evaluates to `[ 2, 4, 6 ]`);
* `[ x for x <- [1, 2, 3, 4, 5] if x % 2 == 0 ]` (list comprehension; this evaluates to `[ 2, 4 ]`);
* `[ -x for x <- [1, 2, 3] if x % 2 != 0 ]` (list comprehension; this evaluates to `[ -1, -3 ]`).

## table
The _table_ type represents a hashtable. Non-empty _table_ values are declared with: `"{" { expr ":" expr "," } [ expr ":" expr ] "}"`. The empty _table_ is `{}`. As with lists, no trailing commas are allowed after the last key-value pair. _table_ values can be iterated over with for-loops or list/table comprehensions. 

Some example tables (suppose `f` is some function):
* `{}` (empty table);
* `{ .x: 0, .y: 0 }` (simple table mapping `.x` and `.y` both to `0`);
* `{ x: f(x) for x <- [.a, .b, .c] }` (table comprehension; this is the same as `{ .a: f(.a), .b: f(.b), .c: f(.c) }`).

## _fn_
The _fn_ type represents a function. There are both named and anonymous functions in YASL. Functions can be nested arbitrarilty.

Some example functions:
* `fn f(a, b) { return a + b; }` (declares a function `f`);
* `const fn f(const a, const b) { return a + b; }` (same as above, but `f` cannot be reassigned, and neither can `a` or `b`);
* `fn(a, b) { return a + b; }` (anonymous version of the first example).

## _userdata_
The _userdata_ type represents values that have been implemented through the C API. In the standard library, the `io` library introduces the `file` type, and the `collections` library introduces the `set` type, both of which are represented by User-data internally. User-data memory is managed by YASL, and user-data can have a meta-table that can be used to look up methods on the user-data, and a _tag_ that can be used to differentiate different kinds of user-data.

## _userptr_
The _userptr_ type is similar to _userdata_, with a few key differences:
* The memory for a user-pointer is not managed by YASL;
* User-pointers can't have a meta-table (meaning they cannot have methods);
* User-pointers cannot have tags (meaning they cannont be differented).

The upside of user-pointers is that they are much lighter-weight than user-data, because of the above. There are no examples of user-pointers in the built-in standard libraries.






