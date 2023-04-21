# Generators, coroutines, and nanoservices

Resume is a new Python opcode as of 3.11. Every normal function starts with resume 0

Using yield in function instead of return turns it into a generator function

A generator is an object that implements the iterator protocol

With a generator you have resume 1 instead of resume 0 in the bytecode

generators can be good when you want to keep from creating a giant list

when to use?

- generators are good when we have a large or infinite set of values to return
- easier to express the ideas as a function

watch again for "yield as an expression - it's interesting...

we can send a value to a generator with the send command

```python
def mygen():
    x = None
    while True:
        x = yield x
        x *+ 5

g = mygen()
next(g)
g.send(10)
```

A coroutine is a generator that waits to get intput from somewhere else with send

What happens with Walrus + Yield?

```python

def mygen():
    x = None
    while x := (yield x):
        x *= 5
```

This allows the while to end if you send something false-y

# How can I use coroutines?

You can use them as "nanoservices"

- very small, in-memory services
- no network, object, thread or process overhead
- something else I missed

See examples
- MD5 hash
- Weather forecast for many cities - but only one city at a time in memory

If we want an exception in a generator we need the throw method

Exceptions aren't just for errors, they can also be for unusual events

yield from allows for multi-level generators/coroutines

