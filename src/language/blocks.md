# Blocks

Blocks are the fundimental building __blocks__ (get it lol) of uranium. There are many different blocks that are provided and hopefully the user will be given the option to define their own meta-programming style.

## Functions

The first and most basic block is the function block. Its a standard function.

```
func test() {

}
```

Pretty standard like most other languages. You have a function name, you have arguments. 
Functions can be passed around as first hand values, and be rebound to different names. 
You can also define functions inside functions and return them.

## Tests

The test block is just a function block with some magic done for you for test registration and running.

Function blocks are defined as `test` followed by a string describing the test.

```
test "that 1 + 1 = 2" {
    assert_eq(1 + 1, 2);
}
```

You can have whatever you want in the string, but it must be a string.

## Process

The process block is for spawning a lightweight fiber. It is managed by the currently scoped runtime, other than that it is defined very similar to the function block.

```
proc ping() {
    println("Ping");
}
```

When called it will spawn the process and attach it to the currently scoped runtime.


## Build

The build block defines a target to build for your program.

```
build main() {
    src("*")
    |> build_exe("example")
}
```

If you invoke build at the command line it will try to find a matching target build block and invoke that.

You can manage dependency chains by composing build blocks yourself. You also have access to a runtime so can do work inside build blocks at build time.

## Protocol 

Protocol defines a polymorphic protocol.

```
protocol size(thing)
```

Currently it has no block body, this might change in the future.

## Implementation

Implement a protocol for a given type.

```
impl size for type(thing) {

}
```

Type can be any of the data types.


## Generator 

_Generator is probably not the final name for this_

Generator has the explicit ability to yield. This allows for lazy execution when it comes to generating sequences and values. _and other fun ideas_

```
generator thing() {
    yield x;
}
```



## Record

Record, otherwise known as a named tuple, or a structure, or any of the other things that match that general idea.

```
record Person {
    name,
    age
}
```

Records can be constructed with their fields, they are immutable and can be passed around like all other data.

## Constrain

_Constrain is an idea that I am playing with for exposing an SMT solver into the compiler for a language._

```
constrain list(thing) as small_list {
    assert(size(thing) <= 50 );
}
```

_The compiler will take steps to prove you never violated the conditions you provide here._
_Potentially constrain can be applied to functions as well_

```
func div(x, y) {
    return x / y;
}

constrain div(x, y) as safe_div {
    assert(x >= 1);
    assert(y >= 1);
    let result = div(x, y);
    assert(result >= 1);
}
```

_Im not entirely convinced on the design here._