# Variables

## Assignment and let variables.

Variables are defined as such.

```uranium
let x = "Hello World";
let y = 123;
```

Normal assignment can only happen inside a block. You can have module level assignments but they must be `const` as covered later.

Variables themselves can be reassigned.
```uranium
let x = "Hey";
x = 123;
```

## Once only assignment via final.

You can stop this by changing `let` to be `final`
```uranium
final x = "hey";
```
Any attempt to assign to `x` in the current scope will cause a compile time error.

## Compile time constants.

A variable can also be made read only and compile time constant by declaring it as `const`

```uranium
const x = 123;
```

This will inline the variable at the compile phase and not allow assignment or modification at runtime.

`const` is also the only assignment allowed outside of a block. Top level `const` assignments can store the result of `const` evaluations. Or `const` data structures.

