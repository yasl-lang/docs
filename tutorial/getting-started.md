# Getting Started

## Installation
Installing YASL can be done by [following the instructions on the main repo](https://github.com/yasl-lang/yasl).

## Using the YASL Interpreter
After installation, the YASL should be located in `/usr/local/bin/yasl`. You should be able to invoke the interpreter by typing `yasl` in your terminal.

To test that your installation worked properly, try the following into your terminal:
```
$ yasl -V
YASL v0.11.5
```

### REPL

To enter into a REPL, type:
```
$ yasl
yasl> 
```

To exit from a REPL, use the `quit()` function:
```
yasl> quit()
$
```

The REPL is fairly limited; it does not include features such as interactive editing, history substitution, or code completion.

### Scripts

The other main use of the interpreter is running a script saved in a file.

To execute a script saved in `example.yasl`, use:
```
$ yasl example.yasl
```

For example, a simple "Hello World" program in YASL is as follows:
```
echo 'Hello World!';
```

Saving the above to `example.yasl` and running it:
```
$ yasl sample.yasl
Hello World!
```

### Passing Arguments to Scripts
All arguements passed to a YASL script, including the name of the script itself, are stored as a list in the `args` variable.

For example, if we have the following script (saved as `example.yasl`):
```
echo args;
```

Then, we can do the following:
```
$ yasl example.yasl 1 2 3
[example.yasl, 1, 2, 3]
```







