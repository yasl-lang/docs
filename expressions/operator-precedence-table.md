# Operator Precedence Table

YASL [Operators](/docs/expressions/operators) have the following precedence (from tightest bound to loosest):

| Precedence | Operators | Description | Associativity |
|------------|-----------|-------------|---------------|
| 1          | () <br> [] <br> .   | Function Calls <br> Indexing <br> Member Access | Left |
| 2          | **        | Exponentiation | Right      |
| 3          | + <br> - <br> @ <br> ! <br> ^ | Unary Plus <br> Unary Minus <br> Length <br> Logical Negation <br> Bitwise Negation | Right |
| 4          | * <br> / <br> // <br> % | Multiplication <br> Float Division <br> Integer Division <br> Modulus | Left |
| 5          | + <br> -  | Addition <br> Subtraction | Left |
| 6          | \<\< <br> \>\> | Bitshift Left <br> Bitshift Right | Left |
| 7          | & <br> &^      | Bitwise And <br> Bitwise And-Not | Left          |
| 8          | ^         | Bitwise Xor | Left          |
| 9          | \|        | Bitwise Or  | Left          |
| 10         | ~         | Concatenation | Right       |
| 11         | < <br> <= <br> > <br> >= | Comparison Operators | Left |
| 12         | == <br> != <br> === <br> !== | Comparison Operators | Left |
| 13         | &&        | Logical And | Right         |
| 14         | \|\|      | Logical Or  | Right         |
| 15         | ??        | Undef Coalescing Operator | Right |
| 16         | ? : | Ternary Operator | Right |
| 17         |  = <br> **= <br> *= <br> /= <br> //= <br> %= <br> += <br> -= <br> >>= <br> <<= <br> ~= <br> &= <br> &^= <br> ^= <br> \|= <br> &&= <br> \|\|= <br> ??=  | Assignment  | Right |


