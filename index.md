# Cubically's Documentation

 - [Home](index.html)
 - [Code page](https://cubically.github.io/docs/codepage)
 - [Commands](commands.html)
 - [Memory](memory.html)
 - [Functions](functions.html)
 - [Inner layers](layers.html)
 - [Syntax](syntax.html)

# Quick guide

This quick guide will get you started with enough to write some code, but not enough to delve into the pain and terror of the language.

### What is "Cubically"?

Cubically is an [esoteric programming language], meaning that it is intentionally difficult to program in.

Other esoteric languages may use a [stack] or a [tape] to store data. Cubically, however, uses a built-in Rubik's Cube and three more [memory locations](memory.html) with varying levels of read-write restrictions.

Cubically specializes in Rubik's Cubes, so almost all of its [commands](commands.html) and functionalities are based around the memory cube. Some, such as XOR and LSHIFT, are really completely useless, but we decided they should be in the language. `` ¯\_(ツ)_/¯ ``

### Syntax

Digits are arguments and non-digits are commands. A command can only be one letter long. (That rule, which you still need to know, is broken so many times it's not even funny.)

    code: RL2UD23
    does: R       call command R without arguments
           L2     call command L with argument 2
             U    call command U without arguments
              D23 call command D with argument 2, then argument 3 (NOT argument 23)

### Cube commands

Any algorithm, or sequence of moves, in [Singmaster's notation], is valid Cubically code.

|Command|Description|
|-|-|
|`R`|rotate the right layer of the cube 90&deg; clockwise|
|`L`|rotate the left layer of the cube 90&deg; clockwise|
|`U`|rotate the top  layer of the cube 90&deg; clockwise|
|`D`|rotate the bottom layer of the cube 90&deg; clockwise|
|`F`|rotate the front layer of the cube 90&deg; clockwise|
|`B`|rotate the back layer of the cube 90&deg; clockwise|

Call any of the above commands with the argument `2` for a 180&deg; turn, and the argument `'` or `3` for a counterclockwise turn.

### Multiple sizes

Since [v2.0][cubically-git-v2.0], Cubically has supported more than just a 3x3x3 for the memory cube. In the interpreter's command-line invocation, append an argument to specify the size: `4` for a 4x4x4 memory cube, or a `5` for a 5x5x5, etc.

**But Singmaster's notation only defines moves for a 3x3x3 D: how can I turn the inner layers of a larger cube?**

Unicode subscripts (`₀₁₂₃₄₅₆₇₈₉`), while breaking the "a command can only be one character long" rule, give you the ability to [turn the inner layers](layers.html). For example, `R` (performed on a solved 4x4x4) changes the cube's state to this:

```
    0002
    0002
    0002
    0002
1111222533330444
1111222533330444
1111222533330444
1111222533330444
    5554
    5554
    5554
    5554
```

However, performing `R₁` on a solved 4x4x4 changes the cube's state to this:

```
    0020
    0020
    0020
    0020
1111225233334044
1111225233334044
1111225233334044
1111225233334044
    5545
    5545
    5545
    5545
```

`R` means "turn the right face 90&deg; clockwise." So `R₁` means "turn the layer 1 inwards from the right face 90&deg; clockwise."

These can be pretty fun. Try [running][TIO-1] `RR₁'R₂R₃'R₄ UU₁'U₂U₃'U₄ L'L₁L₂'L₃L₄'` on a 5x5x5.

### Cubically sounds fun, but how can I actually use it?

You can download the interpreter in the [GitHub repo][cubically-git]. You need [GCC] and [Make] installed.

You can also use the [online interpreter](https://tio.run/##Sy5NykxOzMmp/P8/KOhRU6M6kGgC4mYQo0UhNBQkBiSaQkFioSAxH3UfoCAQN4EYzUDcov7//39TAA), thanks to [Dennis](https://codegolf.stackexchange.com/users/12012/dennis) of [Programming Puzzles and Code Golf](//codegolf.stackexchange.com), where you can find many [fun Cubically programs](https://codegolf.stackexchange.com/search?q=cubically+is%3Aanswer) in friendly competition.

### Who's responsible for this mess?

Most of Cubically, such as the interpreter and the documentation, was written by me, a.k.a. MD XF on the internet ([PPCG](https://codegolf.stackexchange.com/users/61563/md-xf), [GitHub](https://github.com/aaronryank)). Thanks to the members of the [Cubically team](//github.com/Cubically) - Kamil Drakari ([PPCG](https://codegolf.stackexchange.com/users/71434/kamil-drakari), [GitHub](https://github.com/drakari)) and TehPers ([PPCG](https://codegolf.stackexchange.com/users/72489/tehpers), [GitHub](https://github.com/TehPers)) for valuable contributions.

   [GCC]: https://www.gnu.org/software/gcc/
   [Make]: https://www.gnu.org/software/make/
   [cubically-git]: https://git.io/Cubically
   [cubically-git-v2.0]: https://github.com/aaronryank/Cubically/releases/tag/v2.0
   [Singmaster's notation]: https://proofwiki.org/wiki/Definition:Singmaster_Notation
   [stack]: https://en.wikipedia.org/wiki/Stack_(abstract_data_type)
   [tape]: https://esolangs.org/wiki/Tape
   [esoteric programming language]: https://en.wikipedia.org/wiki/Esoteric_programming_language
   
   [TIO-1]: https://tio.run/##Sy5NykxOzMmp/P8/KOhRU6M6kGgC4mYQo0UhNBQkBiSaQkFioSAxH3UfoCAQN4EYzUDcov7//39TAA
