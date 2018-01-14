# Commands

 - [Home](index.html)
 - [Code page](https://cubically.github.io/docs/codepage)
 - [Commands](commands.html)
 - [Memory](memory.html)
 - [Functions](functions.html)
 - [Inner layers](layers.html)
 - [Syntax](syntax.html)

## Command types

There are three types of commands:

 - Standard commands
 - Implicit commands
 - Special commands

Standard commands follow the traditional Cubically syntax - the command sets the default command, and integers call the command with the integer as the argument.

Implicit commands may be called without arguments, and are executed as soon as they are present.

Special commands may be called either implicitly or with arguments. See some commands of type `special` for examples.

If a command does not have defined behavior for being called implicitly it will be called with the notepad value - so calling `+` implicitly will call `+6` (double the notepad).

## Argument types

There are four types of arguments:

 - Standard integers
 - Subscript integers
 - Superscript integers
 - Double-struck integers

Standard integers simply call the command with its default call type - if the default call type is with face value, then the command will be called with the face sum of the face whose index is specified by the integer. If the default call type is raw integer, then the command will be called with the integer as it appears.

Subscript integers attach to the current command. When a command is called with subscripts attached, the subscripts act as a second argument, so <code>command<sub>subscript integers</sub>(arguments)</code> acts as <code>command(arguments,subscripts)</code>. Only certain commands may be called with subscript integers, and each command's behavior differs. See some commands that accept subscript integers for more info.

Superscript integers are similar to subscript integers, except they attach the face sum of the face whose index is specified by the superscript integer. So calling <code>command<sup>0</sup>(arguments)</code> where the top face's sum is 5 is like calling <code>command<sub>5</sub>(arguments)</code>.

When a double-struck integer is present, it executes the command (using default call type) with the face sum of the face whose index is specified by the double-struct integer. So <code>command&#x1d7d8;</code> where the top face sum is 1 is like calling `command` with raw integer 1.

# Commands

### Memory

|Command|Type|Description|Call type|Accepts|Arguments|
|-|-|-|-|-|-|
|`R`|Special|turn right cube face clockwise 90&deg;|Raw|standard, subscript, superscript, double-struck|number of turns, `'` for 3, implicit for 1|
|`L`|Special|turn left cube face clockwise 90&deg;|Raw|^|^|
|`U`|Special|turn top cube face clockwise 90&deg;|Raw|^|^|
|`D`|Special|turn bottom cube face clockwise 90&deg;|Raw|^|^|
|`F`|Special|turn front cube face clockwise 90&deg;|Raw|^|^|
|`B`|Special|turn back cube face clockwise 90&deg;|Raw|^|^|
|`M`|Special|turn the middle face (left-oriented) clockwise 90&deg;|Raw|^|^|
|`E`|Special|turn the middle face (down-oriented) clockwise 90&deg;|Raw|^|^|
|`S`|Special|turn the middle face (front-oriented) clockwise 90&deg;|Raw|^|^|

Subscript integers (and superscript face values) denote the layer to be turned. That is, when a face turn is called with subscript `x`, the `x`th layer inward from the face will be rotated instead of just the face.

### General/math

|Command|Type|Description|Call type|Accepts|Arguments|
|-|-|-|-|-|-|
|`&`|Special|exit if specified face sum/value is truthy|face value|standard|face index (0-8), implicit exits unconditionally|
|`+`|Standard|add all values of specified face together, add to notepad value, write result on notepad|face value|standard|face index (0-8)|
|`-`|Standard|add all values of specified face together, subtract from notepad value, write result on notepad|face value|standard|^|
|`*`|Standard|add all values of specified face together, multiply by notepad value, write result on notepad|face value|standard|^|
|`/`|Standard|add all values of specified face together, divide notepad value by, write result on notepad|face value|standard|^|
|`_`|Standard|set notepad to (notepad modulo faceval)|face value|standard|^|
|`^`|Standard|set the notepad value to (notepad ^ faceval) where ^ represents the exponent|face value|standard|^|
|`=`|Standard|compare notepad and specified face for equality, write result on notepad|face value|standard|^|
|`<`|Standard|set the notepad to (notepad < faceval)|face value|standard|^|
|`>`|Standard|set the notepad to (notepad > faceval)|face value|standard|^|
|<code>&#x2295;</code>|Standard|set the notepad to (notepad ^ faceval) where ^ represents the logical XOR|face value|standard|^|
|<code>&laquo;</code>|Standard|set the notepad to (notepad << faceval)|face value|standard|^|
|<code>&raquo;</code>|Standard|set the notepad to (notepad >> faceval)|face value|standard|^|
|<code>&#xb7;</code>|Standard|set the notepad to (notepad &#xb7; faceval) where &#xb7; represents the logical AND|face value|standard|^|
|`` | ``|Standard|set the notepad to (notepad \| faceval) where `` | `` represents the logical OR|face value|standard|^|
|`:`|Standard|set notepad to specified face index's sum|^|
|`¶`|Standard|Read a string and evaluate it|N/A|standard|None, call implicitly|

### I/O

|Command|Type|Description|Call type|Accepts|Arguments|
|-|-|-|-|-|-|
|`@`|Standard|add all values of specified face together, print as ASCII|face value|standard|face index (0-7), implicit for 6|
|`%`|Standard|add all values of specified face together, print as decimal|face value|standard|^|
|`$`|Standard|input integer, store in input buffer (index 7)|raw|standard|implicit. when called with number, perform that many times|
|`~`|Standard|input character, store in input buffer (index 7)|raw|standard|^|

### Loops

|Command|Type|Description|Call type|Accepts|Arguments|
|-|-|-|-|-|-|
|`(`|Special|create jump point with arguments. if none, create a point that can be jumped to freely. with face indexes, create a point that can be jumped to if any provided face has a truthy sum.|face value|standard|any number of face indexes (0-7)|
|`)`|Special|jump back to previous jump point with arguments. if none, jump back if previous jump point can be jumped to. with face indexes, jump to previous point if both it can be jumped to and if every provided face has a truthy sum.|face value|standard|^|

A better explanation of loops:

 - `(...)` will be an infinite loop.
 - `(0...)` loops as long as the top face has a nonzero sum.
 - `(12...)34` is a loop as long as both `1 || 2` and `3 || 4` is truthy. (numbers are face indexes)

### Conditionals

|Command|Type|Description|Call type|Accepts|Arguments|
|-|-|-|-|-|-|
|`?`|Standard|execute next command or code block if specified face is truthy|face value|standard|face index (0-7)|
|`!`|Special|execute next command or code block if specified face is falsy. also can be used as if-else statement as specified below|face value|standard|face index (0-7) or nothing|
|`{`|Implicit|open a code block|N/A|N/A|N/A|
|`}`|Implicit|close a code block|N/A|N/A|N/A|

### Functions

|Command|Type|Description|Call type|Accepts|Arguments|
|-|-|-|-|-|-|
|`f`|Standard|execute function specified in argument|raw|standard|function to call|

See [Functions](functions.html) for more information.
