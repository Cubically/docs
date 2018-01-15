# Commands

 - [Home](index.html)
 - [Code page](https://cubically.github.io/docs/codepage)
 - [Commands](commands.html)
 - [Memory](memory.html)
 - [Functions](functions.html)
 - [Inner layers](layers.html)
 - [Syntax](syntax.html)

Below you can find a table of all Cubically's commands.

 - **Name** - the short, capitalized name of the command
 - **Char** - the character(s) in the source that call the command
 - **Arg *n*** - what the command does when called with argument *n*
 - **Implicit** - what the command does when called without arguments

### Cube commands

|Char|Name|Arg *n*|Implicit|
|-|-|-|-|
|`R`|`RIGHT`|rotate the right face 90&deg; clockwise *n* times|*n* = 1|
|`L`|`LEFT`|rotate the left face 90&deg; clockwise *n* times|*n* = 1|
|`U`|`UP`|rotate the top face 90&deg; clockwise *n* times|*n* = 1|
|`D`|`DOWN`|rotate the bottom face 90&deg; clockwise *n* times|*n* = 1|
|`F`|`FRONT`|rotate the front face 90&deg; clockwise *n* times|*n* = 1|
|`B`|`BACK`|rotate the back face 90&deg; clockwise *n* times|*n* = 1|
|`M`|`MID_L`|rotate the middle layer inwards from the left face 90&deg; clockwise *n* times|*n* = 1|
|`E`|`MID_D`|rotate the middle layer inwards from the bottom face 90&deg; clockwise *n* times|*n* = 1|
|`S`|`MID_F`|rotate the middle layer inwards from the front face 90&deg; clockwise *n* times|*n* = 1|

There are two things notable about cube commands:

 - `'` is synonymous to `3` in source code.
 - Commands can have subscripts and superscripts attached to them. For more information, see [turning inner 

layers](layers.html).

### General

|Char|Name|Arg *n*|Implicit|
|-|-|-|-|
|`&`|`EXIT`|exit if the value of memory location *n* is nonzero|*n* = 6|
|`+`|`ADD`|notepad += memory location *n*|*n* = 6|
|`-`|`SUB`|notepad -= memory location *n*|*n* = 6|USELESS IMPLICITLY|
|`*`|`MUL`|notepad *= memory location *n*|*n* = 6|
|`/`|`DIV`|notepad /= memory location *n*|*n* = 6|USELESS IMPLICITLY|
|`_`|`MOD`|notepad %= memory location *n*|*n* = 6|USELESS IMPLICITLY|
|`^`|`POW`|notepad **= memory location *n*|*n* = 6|
|`=`|`EQ`|notepad = (notepad == memory location *n*)|*n* = 7|
|`<`|`LT`|notepad = (notepad < memory location *n*)|*n* = 7|PROBABLY|
|`>`|`GT`|notepad = (notepad > memory location *n*)|*n* = 7|PROBABLY
|`⊕`|`XOR`|notepad = (notepad ⊕ memory location *n*)|*n* = 6|USELESS IMPLICITLY|
|`«`|`LSHIFT`|notepad <<= memory location *n*|*n* = 6|USELESS IMPLICITLY|
|`»`|`RSHIFT`|notepad >>= memory location *n*|*n* = 6|USELESS IMPLICITLY|
|`·`|`AND`|notepad &= memory location *n*|*n* = 6|USELESS IMPLICITLY|
|`` | ``|`OR`|notepad \|= memory location *n*|*n* = 6|USELESS IMPLICITLY|
|`:`|`SET`|notepad = memory location *n*|*n* = 7|

### I/O

|Char|Name|Arg *n*|Implicit|
|-|-|-|-|
|`@`|`PUTCHAR`|print memory location *n* as an ASCII character|*n* = 6|
|`%`|`PRINT`|print memory location *n* as an integer|*n* = 6|
|`$`|`READ`|read an integer into input buffer *n* times|*n* = 1|
|`~`|`GETCHAR`|read an ASCII character into input buffer *n* times|*n* = 1|

---

Here are commands that have special behavior:

### Loops

`(` and `)` make up loops.

 - `(...)` will execute the code `...` forever.
 - `(0...)` will execute the code `...` if the memory location 0 is nonzero, and loop while that is still 

true.
 - `(...)0` will execute the code `...`, and loop while memory location 0 is nonzero.
 - `(12...)34` will execute the code `...` if either the memory location 1 or 2 is nonzero, and loop while 

(memory location 1 or memory location 2) and (memory location 3 or memory location 4) are nonzero.

### Conditionals

`?` is an `if-nonzero` conditional. `!` is an `if-zero` conditional.

 - `?6.` will execute `.` if memory location 6 is nonzero.
 - `!6.` will execute `.` if memory location 6 is zero.
 - `?6{...}` will execute `...` if memory location 6 is nonzero.
 - `!6{...}` will execute `...` if memory location 6 is zero.

Note that if `?` and `!` when called implicitly are equivalent to `?6` and `!6`, respectively.

### Functions

`f` calls a function. Unlike the rest of the commands in Cubically, `f` can be called with multiple-digit 

numbers.

See [functions](functions.html) for more information.
