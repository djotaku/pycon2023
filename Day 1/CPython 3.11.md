# Inside Cypthon 3.11's new specializing, adaptive interpreter 

import dis and call dis.dis(function) (where function is the function name) and you can see the bytecode that it produces

in 3.11, after your code is "warm" (has run a few times) it will quicken your code

To see the quickened bytecode, dis.dis(function, adaptive=True)

Inline caches are used to achieve a lot of the benefits. To see those:

dis.dis(function, adaptive=True, show_caches=True)

Starting with 3.12 your program will no longer need to "warm up" to get byte code speed-ups.

3.12 will also have smaller caches

