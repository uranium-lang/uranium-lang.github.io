# Exceptions

_panic / rescue / throw / catch / etc - I am not sure what word I prefer_

## There if you need them

Exceptions are there if you need them, but by name they are exceptional. Treat them as such. 
They are considered fail states for programs if uncaught. 

You can panic anything as an exception using the `panic` expression.

```
panic 1;
panic "oh fuck";
panic :its_broken;
```

You can recover from a panic by using the builtin function rescue.

```
value = rescue(() => {
    panic "oh fuck";
});
```

If a process panic's the scheduler will try to rescue it, but its not garanteed. 

## Runtime rescue handler.

If you are running outside of a rescue block you will be caught by the global rescue handler which by default will just panic again.

_I might let you swap the global rescue handler. Idk_

## Please avoid using them

For the most part you don't need to use exceptions, panic or rescue.

They should be reserved for critical fail states. 