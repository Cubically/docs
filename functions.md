# Functions

 - [Home](index.html)
 - [Code page](https://cubically.github.io/docs/codepage)
 - [Commands](commands.html)
 - [Memory](memory.html)
 - [Functions](functions.html)
 - [Inner layers](layers.html)
 - [Syntax](syntax.html)

Cubically v3.1 has support for functions. A function definition starts with `⇒` (codepage 0x84) and ends in a newline (codepage 0x20). Functions do not have conventional names, such as `foo` or `print`. Instead they have integers for names. For example, this defines function 1 as `R2L2`:

    ⇒R2L2

This defines function 1 as `R2L2`, function 2 as `U2D2`, and function 3 as `F2B2`:

    ⇒R2L2
    ⇒U2D2
    ⇒F2B2

Functions are called with the `f` command. For example, this code executes `R2L2U2D2F2B2`:

    ⇒ R2L2
    ⇒ U2D2
    ⇒ F2B2
    f1 f2 f3

Whitespace added for clarity.
