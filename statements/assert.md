# Assert

Assert statements have the following syntax:

`"assert" expr`.

An assert statement executes the given expression. If it evaluates to a falsey value, execution of the entire program is halted. Otherwise, execution continues to the next statement.

As an example, we could implement a factorial function as follows, using a match statement:

```
fn fact(n)
    assert n >= 0
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

This will halt if `n < 0`, because of the assert.
