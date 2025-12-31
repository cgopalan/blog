---
layout: post
title: "Python tips: Use a regex to remove/substitute characters"
date: 2012-09-18
---

```
import re
```

System Message: WARNING/2 (/Users/cgopalan/my_blog/content/2012-09-18-python-tips-use-a-regex-to-remove-substitute.rst, line 16)

Literal block ends without a blank line; unexpected unindent.
re.sub('[,. ']|test*$', target_str, arg_str)

This takes an 'arg_str' and subsitutes the 'target_str' string with
the pattern specified. You can specify multiple patterns by separating
them with a pipe character as shown above.