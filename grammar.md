```
(*
  YASL uses a variant of EBNF in its documentation to specify the grammar.
  - Non-terminals are specified with bare identifiers: example.
  - Terminals are specified with double-quotes: "example".
  - An asterisk [*] means the previous expression is repeated 0 or more times: "0"*
  - A comma followed by an asterisk [,*] means the previous expression is repeated 0 or more times, separated by a comma: ID,*
  - A comma followed by a plus sign [,+] means the previous expression is repeated 1 or more times, seperated by a comma: ID,+
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

(* Statements *)
stmt = expr_stmt | if_stmt | while_stmt | for_stmt | assert_stmt | echo_stmt | match_stmt | export_stmt | assn_stmt | let_stmt | const_stmt | return_stmt | "break" | "continue";
expr_stmt = expr ";";
block = "{" stmt* "}";
if_stmt = "if" expr block ("elseif" expr block)* ("else" block)?;
while_stmt = "while" expr block;
for_stmt = "for" id "<-" expr block | "for" let_stmt ";" expr ";" expr block;
assert_stmt = "assert" expr;
echo_stmt = "echo" expr;
export_stmt = "export" expr;
assn_stmt = (("let" "const")? id | expr "." id | expr "[" expr "]"),+ assn_op expr,+;
assn_op = "**=" | "+=" | "-=" | "*=" | "/=" | "//=" | "%=" | "<<=" | ">>=" | "&=" | "&^=" | "^=" | "|=" | "~=" | "||=" | "&&=" | "??=";
let_stmt = "let" id "=" expr;
const_stmt = "const" id "=" expr;
return_stmt = "return" expr;
match_stmt = "match" expr "{" (pattern block)* "}";

(* Patterns *)
pattern = alt_pattern ("|" alt_pattern)*;
alt_pattern = binding_pattern | table_pattern | list_pattern | primitive_pattern | any_pattern;
binding_pattern = "let" id | "const" id;
table_pattern = "{" (primitive_pattern ":" pattern),* "}";
list_pattern = "[" pattern,* "]";
primitive_pattern = "undef" | bool_expr | int_expr | float_expr | str_pattern - ?interpolated strings?;
any_pattern = "*";

(* Expressions *)
expr = "undef" | bool_expr | int_expr | float_expr | str_expr | list_expr | table_expr | fn_expr | op_expr | call_expr | index_expr;
bool_expr = "true" | "false";
int_expr = /0x[0-9a-fA-F_]+/ - /0x_+/ | /[0-9][0-9_]*/ | /0b[01_]+/ - /0b_+/;
float_expr = /[0-9][0-9_]*.[0-9][0-9_]/;
str_expr = "." id | /`[^`]`/ | ?single quoted strings with escapes? | ?double quoted strings with escapes and interpolation?;
list_expr = "[" expr,* "]" | "[" expr "for" id "<-" expr ("if" expr)? "]";
table_expr = "{" (expr ":" expr),* "}" | "{" expr ":" expr "for" id "<-" expr (if expr)? "}";
fn_expr = "fn" "(" ("const"? id),* ")" "{" stmt* "}";
op_expr = expr "?" expr ":" | binop_expr | unop_expr;
binop_expr = expr binop expr;
binop = "**" | "+" | "-" | "*" | "/" | "//" | "%" | "<<" | ">>" | "&" | "&^" | "^" | "|" | "~" | "<" | "<=" | ">" | ">=" | "==" | "!=" | "===" | "!==" | "||" | "&&" | "??";
unop_expr = unop expr;
unop = "len" | "+" | "-" | "!" | "^"
call_expr = expr "(" expr,* ")" | expr "->" id "(" expr,* ")";
index_expr = expr "." id | expr "[" expr "]" | expr "[" expr? ":" expr? "]";
id =  /[A-Za-z_$][A-Za-z0-9_$]*/ - ?keyword?;

```
