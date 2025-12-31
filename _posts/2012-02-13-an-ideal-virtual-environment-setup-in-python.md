---
layout: post
title: "An ideal virtual environment setup in python"
date: 2012-02-13
categories: text
tags: python
---

I currently setup my virtual environment in python as prescribed in
this wonderful suggestion over at Stack Overflow.

The idea is to first create a bootstrap virtual environment. This is
possible without installing virtualenvbecause the core virtualenv
program is a python script. Then install virtualenv into this
environment. The reason is once you install it, you get the virtualenv
helper scripts to create and activate environments. And you get pip.

Now with virtualenv and pip we can start creating different environments
as we please.

Since I work a lot with Python 3, it helps to have a separate virtual
environment that's solely dedicated to Python 3 packages and programs so
that I don't mess up the system installation of Python 2.x (I work on
Ubuntu 11.10 now).

If you need any help with this, please do not hesitate to contact me
here. Will be glad to help.