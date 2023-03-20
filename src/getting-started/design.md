# Design

The design of uranium is to be a functional, concurrent and high level programming langauge.

Its goal is to be general-purpose but not specifically high performance, it should be suitable to most day to day tasks, but have the ability to FFI into higher performance code for the heavy lifting.
Currently by default it will be strongly but dynamically typed and expose a gradual type system to allow adding type checking to existing code.

Uranium will be an expression based language and allow for a simple scripting envrionment or a more structured application / library layout with exported functions or a main entry point.

It will support lazy evaluation, pattern matching and guards. It will offer a way to do function composition via piping and other similar mechanisms.
The language will provide immutable data structure and no shared state.

Another goal is to provide a lightweight fiber runtime for concurrent programming, communicating between pocesses will all be done via full copy message passing.

It will have both a VM and a compiler (covered in a later section), and potentially a macro system of some kind.

It will be garbage collected. There will be a runtime requirement.
