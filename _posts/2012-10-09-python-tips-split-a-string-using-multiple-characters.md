---
layout: post
title: "Python tips: Split a string using multiple characters"
date: 2012-10-09
---

The split function in Python allows splitting a string using only one
character. To use multiple characters, use the re module.

```
import re
```

System Message: WARNING/2 (/Users/cgopalan/my_blog/content/2012-10-09-python-tips-split-a-string-using-multiple-characters.rst, line 25)

Literal block ends without a blank line; unexpected unindent.
re.split('_|-[|](#id1),', 'test_this-and-this,plus-that')

System Message: WARNING/2 (/Users/cgopalan/my_blog/content/2012-10-09-python-tips-split-a-string-using-multiple-characters.rst, line 25); *[backlink](#id2)*
Inline substitution_reference start-string without end-string.
Use the pipe delimiter to separate the characters that you need to split
on.