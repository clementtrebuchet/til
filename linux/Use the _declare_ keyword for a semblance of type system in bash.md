# Use the `declare` keyword for a semblance of type system in bash

Bash only has one data type: strings. Even integers and booleans are really strings.

The `declare` keyword can be used to

You can use the `declare` keyword with a few useful options to get something resembling a type system. Some of the useful options:

*   `-r` = read-only

    Variables declared with this flag are read-only, and trying to modify or unset them will throw an error.

*   `-i` = integer

    Variables with this flag will only accept numeric values (integers, bash doesn't have floating-point numbers).  It will auto-coerce any value to a base-10 integer.  Unrecognised values are coerced to 0.

    ```text
    $ declare -i m
    $ m=16; echo $m
    $ m=x12; echo $m
    0
    $ m=0x12; echo $m
    18
    ```

    Hex numbers as well!

*   `-I`/`-u` = lowercase/uppercase

    Variables with these flags set will coerce their characters to lowercase/uppercase respectively.