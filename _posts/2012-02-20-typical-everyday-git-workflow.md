---
layout: post
title: "Typical Everyday Git Workflow"
date: 2012-02-20
categories: misc
tags: git
---

This is a concise cheatsheet for someone getting into git and
wondering what the most common commands are in a developer's daily
workflow.

To check the status of the files in your working directory (ie which
files are being tracked by git and which are not):

```
git status -s
```

To add files (to staging area) that are not yet under source control:

```
git add <filename1> <filename2> ....
```

To remove files (from staging area) that were under version control but
no longer need to be:

```
git rm <filename1> <filename2> ...
```

To record the changes locally:

```
git commit -m 'Your message here'
```

To push your changes to the main repository:

```
git push origin master
```