# Control Flow

## If Statements
If statements take the following form: 

`"if" expr "{" { stmt } "}" { "elseif" expr "{" { stmt } "}" } [ "else" "{" { stmt } "}" ]`

The condition can be any valid expression. Whether the if statement is executed depends on the [[Truthiness|Truthiness]] of the expression.

## While Loops
While loops take the following form:

`"while" expr "{" { stmt } "}"`

As with if statements, the condition can be any valid expression. The condition is checked before every iteration of the while, and the loop continues executing as long as the condition is truthy. While loops can be exited from early using `break`, or the current iteration can be skipped using `continue`.
