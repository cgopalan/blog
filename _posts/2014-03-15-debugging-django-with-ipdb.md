---
layout: post
title: "Debugging Django with ipdb"
date: 2014-03-15
categories: misc
tags: python ipdb
---

If you prefer using lightweight IDEs, you will have to look for other ways
to debug, since your IDE will not provide debug functionality. IPDB (an IPython-wrapper to PDB) is a command-line
debugger that satisfies this requirement. Also, this in no way means that the debugging interface is lacking. In fact,
IPDB has an intuitive, easy to use set of commands. Add to that the syntax coloring and other functionality provided
by IPython like tab-completion, searchable history and access to the shell, IPDB is no less than a delight to use.

Install ipdb using pip. Then add this line just before the line that you want to start debugging from:

```
import ipdb; ipdb.set_trace()
```

Now when you run the program, the debugger will kick in and will wait for input or inspection at the line below the
above statement.

Here are some commands that can be used while interacting with the debugger:

s -- Step into the line. This will go into each line and execute.

n -- Step to the next line. This will jump to the next line and bypass multiple calls in the previous line.

c -- Continue execution until the next breakpoint.

r -- Continue execution until the current function returns.

l -- List the code around the current line.

b [line no] -- Set a breakpoint in the same file on the line number specified.

For a detailed list of the debugger commands, see [here.](http://docs.python.org/2.7/library/pdb.html#debugger-commands)

Note that while at the ipdb prompt, you can do almost anything that you do in an IPython prompt.