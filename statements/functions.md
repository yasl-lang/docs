# Functions

Functions can be declared with the following syntax:

`fn ID "(" { ID "," } [ID] ")" "{" { stmt } "}"`

For example, the following function will add two numbers:

`fn add(a, b) { return a + b; }`

It can be called as follows:

`add(5, 6)`.

YASL includes some built-in functions as well, which can be found under [Built-in Functions](/docs/standard-library/builtin-functions).
