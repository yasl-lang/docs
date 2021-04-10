# IO Library

YASL's IO library has the following functions and constants.

## IO constants

| Name | Description |
|------|-------------|
| stdin | standard input |
| stdout | standard output |
| stderr | standard error |

## IO functions

| Name       | Arguments | Description |
|------------|-----------|-------------|
| open       | name, mode? | Returns the file from opening _name_ in mode _mode_. Valid modes are `'r'`, `'w'`, `'a'`, `'r+'`, `'w+'`, `'a+'`. _mode_ defaults to `'r'` if not supplied. |

## File functions

| Name       | Arguments | Description |
|------------|-----------|-------------|
| read       | self, mode | Valid modes are `'l'` and `'a'`. If _mode_ is `'l'`, returns the next line from _self_. If _mode_ is `'a'`, reads and returns the entire file. |
| write      | self, val | Writes _val_ to _self_. |
| flush      | self | Flushes _self_. |
