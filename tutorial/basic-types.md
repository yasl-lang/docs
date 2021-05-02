# Basic Types

We'll use the YASL REPL in this section to introduce the user to the basic types and operations found in YASL.

## Numbers

YASL has two numeric types, `int` and `float`. YASL supports decimal, binary, and hex literals for `int`, and decimal and exponential notation for `float`:

```
yasl> 10      # int
10
yasl> 0x10    # int (hex)
16
yasl> 0b11    # int (binary)
3
yasl> 4.5     # float
4.5
yasl> 12.3e-1 # float (exponential)
1.23
```

Notably, a `float` in YASL requires a digit on either side of the decimal point, so the following are _not_ valid `float`s: `11.`, `.5`, `12e-1`.\

## Arithmetic

YASL supports all the "usual" arithmetic operations, such as `+`, `-`, and `*`.

```
yasl> 2 * 2 + 3
7
yasl> 4 - 10
-6
```

YASL expressions can use parentheses for grouping:
```
yasl> 2 * (2 + 3)
10
```

Division can be done with `/`:
```
yasl> 5 / 2
2.5
```

Note that `/` always returns a `float` in YASL. If integer division is desired, `//` can be used, and `%` can get the remainder of division:
```
yasl> 5 // 2
2
yasl> 5 % 2
1
```

YASL uses `**` for exponentiation:
```
yasl> 5 ** 2
25
yasl> 2 ** 5
32
```

## Booleans
YASL has two `bool` values, `true` and `false`.

```
yasl> true
true
yasl> false
false
```

Booleans are returned from the built-in comparison operators:
```
yasl> 4 == 5
false
yasl> 4 < 5
true
```

## Undef
`undef` is a unique value in YASL, mostly useful because it is distinct from all other YASL values.

```
yasl> undef
undef
```





