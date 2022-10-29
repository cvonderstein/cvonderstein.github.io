---
layout: default
title: GDB
has_children: false
permalink: software/gdb
parent: Software
---

# GDB

GDB is a debugger (much information, I know, but I'm just writing this down quickly for me to remember).

## Using GDB

Start the debugger:

```zsh
gdb
```

This opens a CLI.
In this CLI, you can then `attach` to a process:

```zsh
(gdb) attach <pid>
```

and let the process execution continue using `c`:

```zsh
(gdb) c
```

Afterwards, it will execute the program.
If some error occurs, e.g. a SegFault, you can use `bt` to get a backtrace:

```zsh
(gdb) bt
```

If debug-symbols are enabled at compile time, you will also get line numbers of the code.

You can also run many commands, like `p` to print out variables:

```zsh
(gdb) p <var>
```

This uses the C syntax, so you can also derefernce pointers, access some array element etc., just like you would in C.
According to my supervisors of my bachelor's thesis, executing C functions doesn't work well though (although that might be a limitation of old legacy software on our cluster).

Oh, and btw, you can quit it with `q`:

```zsh
(gdb) q
```
