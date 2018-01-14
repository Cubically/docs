# Turning inner layers

 - [Home](index.html)
 - [Code page](https://cubically.github.io/docs/codepage)
 - [Commands](commands.html)
 - [Memory](memory.html)
 - [Functions](functions.html)
 - [Inner layers](layers.html)
 - [Syntax](syntax.html)

`RₙX`, where `n` is a subscript number, means:

 > perform X clockwise right turns on the n'th layer inward from the right face

Examples:

    Code: R₀2 (equivalent to R2)
    Cube (3x3): 
       005
       005
       005
    111224333244
    111224333244
    111224333244
       550
       550
       550

    Code: R₁2
    Cube (3x3):
       050
       050
       050
    111242333424
    111242333424
    111242333424
       505
       505
       505
    Cube (4x4):
        0050
        0050
        0050
        0050
    1111224233334244
    1111224233334244
    1111224233334244
    1111224233334244
        5505
        5505
        5505
        5505

If `n` is larger than or equal to the size of the cube, it will act as a no-op. For example, `R³2` on a 3x3x3 would be a no-op, but on a 4x4x4, it would turn the third face inward from the right face.

`RⁿX`, where `n` is a superscript number, means:

 > perform X clockwise turns on the m'th layer inward from the right face, where m is the face sum of n-indexed face
 
 So, if the notepad was 1, <code>R&#x2076;2</code> would turn the middle face on a 3x3x3 twice.
 
 Combining superscripts and subscripts will result in undefined behavior. Each version of the interpreter handles sub/superscript integration differently. You should never combine subscripts and superscripts in the same command so the behavior will never be defined.
