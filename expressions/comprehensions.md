# Comprehensions

YASL supports list- and table-comprehensions, for creating a new list or table from an existing one. These can be used to replace both `map` and `filter` in a more functional style of programming.
List- and table-comprehensions can iterate over anything a `for`-loop can.

## List Comprehensions
The syntax for list comprehensions is:
```
"[" expr "for" id "<-" expr ("if" expr)? "]"
```

For example, the following would produce a new list from `ls` with every element doubled:
```
[ 2 * x for x <- ls ]
```

The following would make a new list with only the odd elements:
```
[ x for x <- ls if x % 2 != 0 ]
```

These two can also be combined. The following produces a new list containing the square of every odd element:
```
[ x * x for x <- ls if x % 2 != 0 ]
```


## Table Comprehensions:
The syntax for table comprehensions is:
```
"{" expr ":" expr "for" id "<-" expr ("if" expr)? "}"
```
Table comprehensions can use the same mapping and filtering as a list comprehension.
