# Comprehensions

YASL supports list- and table-comprehensions, for creating a new list or table from an existing one. These can be used to replace both `map` and `filter` in a more functional style of programming.
List- and table-comprehensions can iterate over anything a `for`-loop can.

## List Comprehensions
The syntax for list comprehensions is:
```
[ _expr for let i <- _list if _cond ]
```

where `_expr`, `_list` and `_cond` are arbitrary YASL expressions. The `if _cond` section is optional.

For example, the following would produce a new list with every element doubled:
```
[ 2 * x for let x <- ls ]
```

The following would make a new list with only the odd elements:
```
[ x for let x <- ls if x % 2 != 0 ]
```

These two can also be combined. The following produces a new list containing the square of every odd element:
```
[ x * x for let x <- ls if x % 2 != 0 ]
```


## Table Comprehensions:
The syntax for table comprehensions is:
```
[ _key:_value for let i <- _list if _cond ]
```

where `_key`, `_value`, `_list` and `_cond` are arbitrary YASL expressions. The `if _cond` section is optional.

