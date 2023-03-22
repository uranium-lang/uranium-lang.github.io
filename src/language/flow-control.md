# Flow control

## No loops. Only recursion. 

_There is no need to get your jimmies rustled._

If you want to loop use recursion. We have TCO.

```
func loop() {
    return loop();
}
```

## If expressions and unless

You can use if as an expression. If you do all branches must evaluate to a value or a terminal state.

```
let x = if (y) { 1 } else { 2 }
// or
let y = if (z) { 1 } else { return }
```

We also offer inverted `if` called `unless`

## Matching 

Similar to if, but you can match patterns. You can also have guards. These again can be used as expressions, but they must return a value or be terminal.

More covered in the pattern matching section.

If you fail to provide a base case you will get a runtime error, unless you are using the type checker, then you will get a type error.

```
let input = (:red, 95);

match input {
    (:red, x) if x >= 90 => println("wow that is really red"),
    (color, 0) => println("Your colour is weak."),
    _ => println("Base case.")
}
```

## Early return.

You can return whenever you want.

