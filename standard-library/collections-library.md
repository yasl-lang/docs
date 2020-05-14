# Collections Library

YASL's collections library defined the following functions.

## Collections functions

| Name | Arguments | Description |
|------|-----------|-------------|
| set | args... | Returns a set containing _args_. |
| list | args... | Alternate constructor for lists. |
| table | args... | Alternate constructor for tables. |

## Set functions

| Name | Arguments | Description |
|------|-----------|-------------|
| tostr | self | Returns a string representation of _self_. |
| tolist | self | Creates a new list containing all the elements of _self_, in arbitrary order. |
| add | self, val | Updates _self_ to contain _val_. |
| remove | self, val | Removes _val_ from _self_. |
| copy | self | Creates a copy of _self_. |
| clear | self | Removes all elements from _self_. |
| contains | self, val | Returns true if _val_ is in _self_, otherwise false. |

| Operator | Operands | Description |
|----------|----------|-------------|
| & | left, right | Set intersection of _left_ and _right_. |
| \| | left, right | Set union of _left_ and _right_. |
| ^ | left, right | Symmetric set difference of _left_ and _right_. |
| &^ | left, right | Set difference of _left_ and _right_. |
| len | set | Cardinality of _set_. |
