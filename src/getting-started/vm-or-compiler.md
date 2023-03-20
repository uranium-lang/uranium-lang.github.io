# VM or Compiler

### Why not both?

To achieve the level of compile time evaluation I want, or to do the way I want to implement builds it will need a VM to evaluate code sections. This will allow for code to be written that is then not compiled out, but evaluated by the compiler and the result inserted. 

It also provides the programmer with a repl, allowing for repl style development or if embedded in the final executable runtime debugging and information.

The plan is to provide a way to detect if the program is running under a VM or is compiled, but the goal is to make the environments so similar that the distinction becomes worthless.

Whichever way the user decides to use the language they both will carry a reasonably involved runtiem, that will manage the garbage collection, message passing and fiber scheduling.
