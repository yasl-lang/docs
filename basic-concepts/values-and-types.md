# Values and Types

YASL is a _dynamically typed_ langauge. This means that variables don't carry any type information; only values do. YASL has the following 7 basic types:
* _undef_
* _bool_
* _int_
* _float_
* _str_
* _list_
* _table_

## undef
The _undef_ type has 1 value, **undef**, which is useful mainly because it is different from all other values. It is the default value for a variable if the variable is not given a value during declaration.

## bool
The _bool_ type has 2 values, **true** and **false**, with the expected semantics of booleans.

## int
The _int_ type represents signed, 64-bit, two's complement integers. _int_ literals can be created for base-2 (prefix _0b_ or _0B_ ), base-10 (no prefix), or base-16 (prefix _0x_ or _0X_ ). Note that _int_ literals with leading 0's are interpreted as base-10, not base-8 as in some languages. 

## float
The _float_ type represents IEEE double precision floating point numbers. _float_ literals must have at least 1 digit both before and after the decimal point, unlike some other languages.

## str
The _str_ type represents an immutable sequence of ASCII characters. _str_ values are delimited on either side with single quotes.

## list
The _list_ type represents a resizing array. _list_ values are declared with: `"[" [ {expr "," } expr ] "]"`. Note that no trailing commas are allowed after the last value in a list. _list_ values can be iterated over with for-loops or list/table comprehensions.

## tables
The _table_ type represents a hashtable. Non-empty _table_ values are declared with: `"{" { expr ":" expr "," } [ expr ":" expr ] "}"`. The empty _table_ is `{}`. As with lists, no trailing commas are allowed after the last key-value pair. _table_ values can be iterated over with for-loops or list/table comprehensions. 
