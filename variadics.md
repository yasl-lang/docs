# Variadics

Certain locations in YASL allow a variable number of expressions to be used.

Locations in YASL where an arbitrary number of expressions may be used are referred to as "variadic contexts". The full list of variadic contexts is:
- Arguments to a function call
- Return values from a function
- Right side of an assignment or declaration

As an example:
```
fn f() {
  return 1, 2
}

let a, let b = f()

echo [ a, b ]   # [1, 2]
```
  
In all cases, the variadic is either expanded (by filling with `undef`) or trimmed as need.
The last value of a variadic context is always fully expanded; the rest are not.

```
# using same definition of f from above

let c = f()

# only first value is kept, further values are discarded silently.
echo c   # 1

a, b, c = f()
  
# Because we need 3 values but f only returned 2, we fill the rest with undef.
echo [ a, b, c ]  # [1, 2, undef]
```
