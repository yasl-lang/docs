```
(*
  YASL uses a variant of EBNF in its documentation to specify the grammar.
  - Non-terminals are specified with bare identifiers: example.
  - Terminals are specified with double-quotes: "example".
  - An asterisk [*] means the previous expression is repeated 0 or more times: "0"*
  - A comma followed by an asterisk [,*] means the previous expression is repeated 0 or more times, separated by a comma: ID,*
  - A postfix question mark [?] means the previous expression is optional: "const"?
  - Parentheses [(...)] may be used to group expressions: ("const"? ID),*
  - A pipe [|] represents alternatives: "let" | "const"
  - Question marks on both sides [?...?] represent a special sequence, normally one that is obvious but tedious to write out: ?keyword?\
  - Front-slashes on both sides represent a regex: /[A-Za-z_$][A-Za-z0-9_$]*/
  - A minus sign [-] omits the expressions on the right from the expression on the left, even if they would normally match. The only special characters for regex are brackets for character classes, plus for 1 or more occurances, and asterisk for 0 or more occurances: /[A-Za-z_$][A-Za-z0-9_$]*/ - ?keyword?
  - Each production rule is terminated by a semicolon [;]
  - When a literal semicolon is used in a rule, it may be substituted for a newline in a YASL program
 *)


program = stmt*;
stmt = expr_stmt | if_stmt | while_stmt | for_stmt | assert_stmt | match_stmt | export_stmt | let_stmt | const_stmt;
expr_stmt = expr ";";
expr = "undef" | bool_expr | int_expr | float_expr | str_expr | list_expr | table_expr | fn_expr;
bool_expr = "true" | "false";
int_expr = /0x[0-9a-fA-F_]+/ - /0x_+/ | /[0-9][0-9_]*/ | /0b[01_]+/ - /0b_+/;
float_expr = /[0-9][0-9_]*.[0-9][0-9_]/;
str_expr = "." id | /`[^`]`/ | ?single quoted strings with escapes? | ?double quoted strings with escapes and interpolation?;
list_expr = "[" expr,* "]" | "[" expr "for" id "<-" expr ("if" expr)? "]";
table_expr = "{" (expr ":" expr),* "}" | "{" expr ":" expr "for" id "<-" expr (if expr)? "}";
fn_expr = "fn" "(" ("const"? id),* ")" "{" (stmt | "return" expr)* "}";



```
