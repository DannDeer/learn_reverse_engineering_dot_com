Start off by running the executable to see what the output is before we start debugging it.

```
Welcome to the challenges! This is challenge #1, the easiest of the bunch.
Open this binary up in GDB to find out what the flag is! If you get stuck then remember that GDB has a search function 👀
```

Use `gdb ./solution1` to start debugging the executable to see what we can find. Once started we can then set up debugging environment as well as setting a breakpoint and moving to the tui mode.

In these examples the intel assembly flavour will be used.

```
set disassembly-flavor intel
break main
layout asm
layout regs
```

And then start the executable with `run`.

Here we can see at `main+36`, there is an `lea` instruction being used to load some data into the `rax` register.
If we step through the program we can then use `x/bs $rax` to get the data referenced by this address, in this case it happens to be the flag, `{flag: EZPZ}`.
