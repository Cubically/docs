# Syntax

 - [Home](index.html)
 - [Code page](https://cubically.github.io/docs/codepage)
 - [Commands](commands.html)
 - [Memory](memory.html)
 - [Functions](functions.html)
 - [Inner layers](layers.html)
 - [Syntax](syntax.html)

Each character in Cubically source code is either a command or an argument. For example:

    code: RL2UD23
    does: R       call command R without arguments
           L2     call command L with argument 2
             U    call command U without arguments
              D23 call command D with argument 2, then argument 3

Each argument may only be a single-digit integer; multiple arguments call the command separately. As in the example, `D23` does not call `D` with argument 23, it calls `D` with argument 2, then argument 3.

There is one exception to the above rule: the `f` command. Arguments stack up, so `f23` will call `f` with `23`. To call `f` with `2` and then `3` you would have to write `f2f3`.

For more information about arguments and commands, see [commands](commands.html).
