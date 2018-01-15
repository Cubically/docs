# Memory

 - [Home](index.html)
 - [Code page](https://cubically.github.io/docs/codepage)
 - [Commands](commands.html)
 - [Memory](memory.html)
 - [Functions](functions.html)
 - [Inner layers](layers.html)
 - [Syntax](syntax.html)

Cubically has a unique memory structure. The memory is a Rubik's cube. Various commands perform operations on this cube, such as turning the right face clockwise by 90 degrees. Other commands perform operations on certain faces of the cube, like adding all values on the top face together and storing them on the notepad (see below).

The six faces of the cube are initialized with the numbers 0 through 5, like this:

       000
       000
       000
    111222333444
    111222333444
    111222333444
       555
       555
       555

After performing a clockwise 90° turn on the right face, the memory cube would look like this:

       002
       002
       002
    111225333044
    111225333044
    111225333044
       554
       554
       554

To make Cubically an (almost) usable language, there is one piece of fully read-writeable memory: the "notepad", which is a single-value register. This can store one value at a time. Performing a command on the nonexistent sixth face index will perform the command on the notepad. So, for example, `+6` will add the notepad to itself.

Input is performed using the nonexistent seventh-indexed face. When input is read it is stored there and can be accessed by all commands that access face indexes. It is not changed until input is read again. It is initialized to zero.

The 8th indexed face contains a non-writeable boolean. It is always false if the cube is solved, and always true otherwise.

# Memory locations

|Memory location|Data|Visualizer color|
|-|-|-|
|0|top face sum|red|
|1|left face sum|blue|
|2|front face sum|purple|
|3|right face sum|green|
|4|back face sum|blue|
|5|bottom face sum|yellow|
|6|notepad|N/A|
|7|input buffer|N/A|
|8|cube is unsolved? (true/false)|N/A|
