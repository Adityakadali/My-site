---
title: "Learn enough git to be dangerous | Git Basics"
date: 2022-07-23T22:33:46+05:30
type:
  - posts
  - post
tags:
  - github
  - git
  - coding
categories:
  - Github
series:
  - Github 101
author:
  name: Aditya Kadali
---

In the world of coding we need we write thousands of lines of code if not millions. We release different versions of software. If your project is small you can get away from saving _version 01_ files in separate backup when you release _version 02_. In large code bases you can't get away with that and you can't `ctrl+z` your way to revert your changes in code.

## What is git?

Git is verson control system which helps user to track changes in files and save snapshots of the files they want to track.

I this blog post I want to guide Individual developers who work alone to learn enough of git basics to get started using git.

## Basics of git

### git init

```bash
git init [-q | --quiet] [--bare] [--template=<template-directory>]
	  [--separate-git-dir <git-dir>] [--object-format=<format>]
	  [-b <branch-name> | --initial-branch=<branch-name>]
	  [--shared[=<permissions>]] [<directory>]
```

This command initializes a basic git repository in current folder. This means it adds a `.git` folder in the current directiory with basic default configurations.

running `git init` in a non empty folder or already existing repository is safe it won't delete any files in that folder. In case it's already a repository it will add any extra configs you have given with that.

### git log

```bash
git log [<options>] [<revision-range>] [[--] <path>…​]
```

It is self explanatory command this spits out log of that repositoty. you can pass some flags with this command to dig deep into logs like `git log -n 10` outputs last 10 commits details in that repo. there are somany flags available for this log. run helper command to know more about this.

```bash
git help log
```

### git switch & git branch

```bash
git switch [<options>] [--no-guess] <branch>
git switch [<options>] --detach [<start-point>]
git switch [<options>] (-c|-C) <new-branch> [<start-point>]
git switch [<options>] --orphan <new-branch>
```

This command is used to switch branches. and new commits will be added to this branch.

```bash
git branch [--color[=<when>] | --no-color] [--show-current]
	[-v [--abbrev=<n> | --no-abbrev]]
	[--column[=<options>] | --no-column] [--sort=<key>]
	[--merged [<commit>]] [--no-merged [<commit>]]
	[--contains [<commit>]] [--no-contains [<commit>]]
	[--points-at <object>] [--format=<format>]
	[(-r | --remotes) | (-a | --all)]
	[--list] [<pattern>…​]
git branch [--track[=(direct|inherit)] | --no-track] [-f]
	[--recurse-submodules] <branchname> [<start-point>]
git branch (--set-upstream-to=<upstream> | -u <upstream>) [<branchname>]
git branch --unset-upstream [<branchname>]
git branch (-m | -M) [<oldbranch>] <newbranch>
git branch (-c | -C) [<oldbranch>] <newbranch>
git branch (-d | -D) [-r] <branchname>…​
git branch --edit-description [<branchname>]
```

This command is used to create and delete branches. `-list` to list out all branches.

### git add

This command adds files to staging area and will be commited in next commit.

```bash
git add [--verbose | -v] [--dry-run | -n] [--force | -f] [--interactive | -i] [--patch | -p]
	  [--edit | -e] [--[no-]all | --[no-]ignore-removal | [--update | -u]] [--sparse]
	  [--intent-to-add | -N] [--refresh] [--ignore-errors] [--ignore-missing] [--renormalize]
	  [--chmod=(+|-)x] [--pathspec-from-file=<file> [--pathspec-file-nul]]
	  [--] [<pathspec>…​]
```

```bash
git add .
```

The above command adds all files to staging area in that directory.

### git status

```bash
git status [<options>…​] [--] [<pathspec>…​]
```

This command shows the status of the current working branch.

and there is a similar command `git diff`

```bash
git diff [<options>] [<commit>] [--] [<path>…​]
```

this shows difference between commands with the help of some extra flags we can also see difference between old commits also.

### git commit

```bash
git commit [-a | --interactive | --patch] [-s] [-v] [-u<mode>] [--amend]
	   [--dry-run] [(-c | -C | --squash) <commit> | --fixup [(amend|reword):]<commit>)]
	   [-F <file> | -m <msg>] [--reset-author] [--allow-empty]
	   [--allow-empty-message] [--no-verify] [-e] [--author=<author>]
	   [--date=<date>] [--cleanup=<mode>] [--[no-]status]
	   [-i | -o] [--pathspec-from-file=<file> [--pathspec-file-nul]]
	   [(--trailer <token>[(=|:)<value>])…​] [-S[<keyid>]]
	   [--] [<pathspec>…​]
```

This command records changes in the current repository.

simply we can save with message with

```bash
git commit -m "Your message"
```

### git restore

```bash
git restore [<options>] [--source=<tree>] [--staged] [--worktree] [--] <pathspec>…​
git restore [<options>] [--source=<tree>] [--staged] [--worktree] --pathspec-from-file=<file> [--pathspec-file-nul]
git restore (-p|--patch) [<options>] [--source=<tree>] [--staged] [--worktree] [--] [<pathspec>…​]
```

this command is used to restore files in your repository.

```bash
git restore main.py
```

the above command restores `main.py` file if deleted it or want to commit it to previous revision of file.

### git merge

```bash
git merge [-n] [--stat] [--no-commit] [--squash] [--[no-]edit]
	[--no-verify] [-s <strategy>] [-X <strategy-option>] [-S[<keyid>]]
	[--[no-]allow-unrelated-histories]
	[--[no-]rerere-autoupdate] [-m <msg>] [-F <file>]
	[--into-name <branch>] [<commit>…​]
git merge (--continue | --abort | --quit)
```

This command is used to merge to or more branches together

For more information about these command visit [Git - Reference](https://www.git-scm.com/docs/)
