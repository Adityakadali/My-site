---
title: "Markdown Cheatsheet"
date: 2022-07-23T23:09:07+05:30
type:
  - posts
  - post
tags:
  - Markdown
  - Cheatsheet
series:
  - Github 101
author:
  name: Aditya Kadali
---

## Headers

h1, h2, h3, h4, h5, h6

```markdown
# h1

## h2

### h3

#### h4

##### h5

###### h6
```

## code and syntax highlighting

```markdown
Printing hello world => `print("hello world");`
```

we can use single ```` single back ticks to write inline code.

````markdown
```
for i in range(1,10):
    print(i)
```
````

triple backticks are used to create a code block

## Text styling

```markdown
**This is bold text**
_This is italics_
**_This is bold italics_**
~~This is stikethrough~~
```

## Lists

Ordered lists

```markdown
1. This is ordered list
1. next item in ordered list
1. antother item
```

Unorderd list

```markdown
- item 1
- item 2
  - sub-item1
  - sub-item2
```

## Links

Normal links

```markdown
[link text](https://example.com "title")
```

Arbitrary links

```markdown
[reference][case insensitive reference text]
```

Links with reference numbers mostly used in journals

```markdown
[reference text][1]

In this number should be defined like
[1]:https://example.com
```

## Images

```markdown
![alt text](https://example.com/funnycatpic.png "Title of picture")
```

## Blockquotes

```markdown
> This is block quote
```
