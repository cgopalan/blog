---
layout: post
title: "Hadoop quickstart - with Python map-reduce example"
date: 2013-01-08
categories: misc
tags: map-reduce python hadoop
---

The last couple of days I have been playing around with Hadoop. Its
mainly for processing large data over clusters, which can be cheap
commodity hardware. Hadoop implements its own distributed file system
(HDFS) as an abstraction over the underlying file systems of the various
machines it interacts with.

For those interested, this is just a quick summary of how to go about
learning it.

First, read this great tutorial by Michael Noll which explains how
to setup a single-node cluster and run a Hadoop job on it. Its very
clear and you will be running it in no time. For the example, it uses
the word count program that is provided with Hadoop.
Optionally, if you have multiple machines, you can try out the
multiple cluster tutorial. I haven't tried it out but I would
imagine it would work well since its explained as clearly as the
first.
Second, if you want to write your own mappers and reducers, use the
Hadoop streaming facility provided by Hadoop. With this, you can
specify your custom mapper and reducer programs and the Hadoop job
will feed the specified data to these programs as a stream. Thus, the
advantages of the Hadoop functionality over distributed file systems
is still retained. You can look at this blog entry by the same
author to run the custom program.

Here's my own version of a python map and reduce program that takes in
lines of text of sums up the count of the different words occurring in
the text. This is the canonical map reduce example.

mapper.py

```
#!/usr/local/bin/python3
```
import sys

def run_map(f):

for line in f:
data = line.rstrip().split()
# print one word per line
for word in data:

System Message: ERROR/3 (/Users/cgopalan/my_blog/content/2013-01-08-hadoop-quickstart-with-python-map-reduce-example.rst, line 81)
Unexpected indentation.

print(word)

if __name__ == '__main__':
run_map(sys.stdin)

reducer.py

```
#!/usr/local/bin/python3
```
import sys
from collections import Counter

def run_reduce(f):
# inbuilt counter object that keeps counts
# for all words added
cnt = Counter()
for line in f:

System Message: ERROR/3 (/Users/cgopalan/my_blog/content/2013-01-08-hadoop-quickstart-with-python-map-reduce-example.rst, line 116)
Unexpected indentation.

data = line.rstrip()
cnt[data] += 1

System Message: WARNING/2 (/Users/cgopalan/my_blog/content/2013-01-08-hadoop-quickstart-with-python-map-reduce-example.rst, line 118)
Block quote ends without a blank line; unexpected unindent.
# print the word and its count
for word, count in cnt.items():

System Message: ERROR/3 (/Users/cgopalan/my_blog/content/2013-01-08-hadoop-quickstart-with-python-map-reduce-example.rst, line 120)
Unexpected indentation.

print(word,':',count)

if __name__ == '__main__':
run_reduce(sys.stdin)