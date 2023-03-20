# Data types

## Mutability

None of the following structures are mutable. Any modification will return a new structure, it up to the caller to remember to save that if they need it.

## Booleans
Pretty self explanatory.

`true` or `false`

## Integers
There is support for all size of integer from 8 to 64 (maybe 128) in both signed and unsigned formats.

If you want to specify an integers size and if it is signed or not simply append `i` or `u` for the sign and then the size in bits, for example
`1i32` or `2u16`

We allow numbers to be decimal, hex, octal, or binary using the stanard prefixes.

## Floats

Probably 32 / 64 bit float support when I can get round to it.

## Tuples
A fixed length number of values of possibly different types.

`(a, b, c)` or `("test", 123)`

## Lists
A dynamically growable list. Think array list or vector.

`[1,2,3]` or `["test", 1]`

## Atoms
A compile time constant value that is garanteed to be unique by the VM.

`:ok` or `:apple`

## Strings
UTF-8 Strings.

`"testing"` or `""`
