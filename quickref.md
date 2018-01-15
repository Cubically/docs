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
|`&`|`EXIT`|exit if the value of memory location *n* is nonzero|*n* = 6|
|`+`|`ADD`|notepad `+=` memory location *n*|*n* = 6|
|`-`|`SUB`|notepad `-=` memory location *n*|*n* = 6|USELESS IMPLICITLY|
|`*`|`MUL`|notepad `*=` memory location *n*|*n* = 6|
|`/`|`DIV`|notepad `/=` memory location *n*|*n* = 6|USELESS IMPLICITLY|
|`_`|`MOD`|notepad `%=` memory location *n*|*n* = 6|USELESS IMPLICITLY|
|`^`|`POW`|notepad `**=` memory location *n*|*n* = 6|
|`=`|`EQ`|notepad = (notepad == memory location *n*)|*n* = 7|
|`<`|`LT`|notepad = (notepad < memory location *n*)|*n* = 7|PROBABLY|
|`>`|`GT`|notepad = (notepad > memory location *n*)|*n* = 7|PROBABLY
|`⊕`|`XOR`|notepad = (notepad ⊕ memory location *n*)|*n* = 6|USELESS IMPLICITLY|
|`«`|`LSHIFT`|notepad `<<=` memory location *n*|*n* = 6|USELESS IMPLICITLY|
|`»`|`RSHIFT`|notepad `>>=` memory location *n*|*n* = 6|USELESS IMPLICITLY|
|`·`|`AND`|notepad `&=` memory location *n*|*n* = 6|USELESS IMPLICITLY|
|`` | ``|`OR`|notepad `` |= `` memory location *n*|*n* = 6|USELESS IMPLICITLY|
|`:`|`SET`|notepad = memory location *n*|*n* = 7|
|`@`|`PUTCHAR`|print memory location *n* as an ASCII character|*n* = 6|
|`%`|`PRINT`|print memory location *n* as an integer|*n* = 6|
|`$`|`READ`|read an integer into input buffer *n* times|*n* = 1|
|`~`|`GETCHAR`|read an ASCII character into input buffer *n* times|*n* = 1|
