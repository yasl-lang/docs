# Built-in Functions

YASL has to following built-in functions. Note that these are all attached to the metatables for certain types. 
So to call `int64.tofloat64` on something of type `int64`, if `x` was an `int64` value, one would type `x.tofloat64(x)`.
As short-hand for this, you can also type `x::tofloat64()`, which is exactly the same as `x.tofloat64(x)`. 
This notation can be used for all functions listed below.

## Float64 Functions
| Name       | Arguments | Description |
|------------|-----------|-------------|
| toint64    | self      | converts self to an int64 value, truncating if necessary |
| tostr      | self      | converts self to a str value |

## Int64 Functions
| Name       | Arguments | Description |
|------------|-----------|-------------|
| tofloat64  | self      | converts self to an float64 value, rounding to nearest float if necessary if necessary |
| tostr      | self      | converts self to a str value |

