# Functions

Functions can be declared with the following syntax:

`"const"? "fn" ID "(" ("const"? ID),* ")" "{" stmt* "}"`

For example, the following function will add two numbers:

`fn add(a, b) { return a + b; }`

It can be called as follows:

`add(5, 6)`.

You can also write:

`const fn add(a, b) { return a + b; }`

which means `add` cannot be reassinged another value later, and


`fn add(const a, const b) { return a + b; }`

which means that `a` and `b` cannot be reassigned inside `add`.

YASL includes some built-in functions as well, which can be found under [Built-in Functions](/docs/standard-library/builtin-functions).
