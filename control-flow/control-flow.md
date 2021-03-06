# Control Flow

## If Statements
If statements take the following form: 

`"if" expr "{" { stmt } "}" { "elseif" expr "{" { stmt } "}" } [ "else" "{" { stmt } "}" ]`

The condition can be any valid expression. Whether the if statement is executed depends on the [Truthiness](/docs/control-flow/truthiness) of the expression.

example:
```
if x % 15 == 0 {
    echo 'FizzBuzz'
} elseif x % 5 == 0 {
    echo 'Buzz'
} elseif x % 3 == 0 {
    echo 'Fizz'
} else {
    echo x
}
```
## Match Statements

Match statements take the following form:

`"match" expr "{" { pattern "{" { stmt } "}" } "}"`

For example, the first pattern will match either a list of 2 elements or a table with keys `x` and `y`, while the second matches anything.

```
match p {
    [ const x, const y ] | { .x: const x, .y: const y, ... } {
        echo "x: #{x}, y: #{y}"
    }
    * {
        echo "invalid"
    }
}
```

In addition to `list` and `table` pattern shown above, we can also match on literal `undef`, `bool`, `int`, `float`, and `str`s.

For example, we could implement factorial as follows:

```
fn fact(n) {
    match n {
        0 | 1 {
            return 1
        }
        * {
            return n * fact(n-1)
        }
    }
}
```

## While Loops
While loops take the following form:

`"while" expr "{" { stmt } "}"`

As with if statements, the condition can be any valid expression. The condition is checked before every iteration of the while, and the loop continues executing as long as the condition is truthy. While loops can be exited from early using `break`, or the current iteration can be skipped using `continue`.

example:
```
while n > 0 {
    x *= n
    n -= 1
}
```

## Numeric For Loops
Numeric for loops take the following form:

`"for" ["let" ID "="] expr ";" expr ";" expr "{" { stmt } "}"`.

The first expression (or `let` statement) is executed once before the loop begins. The second expr is the condition to determine when to end the loop. The final expression is evaluated after every iteration of the loop. Note that for loops introduce their own scope, which includes the expression evaluated before starting the loop.

example:
```
for let i = 0; i < len ls; i += 1 {
    echo ls[i]
}
```

## Iterative For Loops
Iterative for loops take the following form:

`"for" ID "<-" expr "{" { stmt } "}"`.

The expression can be any valid expression, although it is a runtime error if it does not evaluate to a list, table or string. Like numeric for loops, iterative for loops introduce their own scope. The iteration variable existed only inside the body of the for loop, and will not alter a variable of the same name from an outer scope.

example:
```
for x <- ls {
     echo x
}
```
