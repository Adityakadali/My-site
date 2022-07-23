---
title: "Positioning Elements"
date: 2022-07-20T22:39:58+05:30
type:
  - posts
  - post
tags:
  - HTML
  - CSS

categories:
  - Web Development
author:
  name: Aditya Kadali
---

Using CSS you can position you HTML elements on webpage where ever you want. You can position an element using the top, bottom, left and right properties. These properties can be used only after position property is set first.

There are 4 ways to position an element

- Static
- Fixed
- Stickey
- Relative
- Absolute

## Static positioning

This is default property for every element. Elements of this property are positioned from top to bottom like in HTML Document. CSS properties like top, bottom, left, right doesn't effect on these elements

## Fixed positioning

This property helps us to position an element fixed relative to the browser window. It doesn't gets effected even when we scroll the page.

**Eg:**

```css
.logo {
  position: fixed;
  top: 20px;
  left: 20px;
}
```

In this example the element with logo class is fixed at 20px from and 20px from left with respective to your browser window.

## Stickey positioning

There will some times you want an element fixed positon even when you scroll through pages with respective to their parent element. For example you need sticky headers in a table you can use this property instead of fixed.

**Eg:**

```css
table th {
  position: stickey;
}
```

In this example table headers are sticky positioned when the data overflows the page and we need to scroll the page. we will be able to see the stickey headers even when scrolling.

## Relative positioning

When we have given an element relative property it will be relative to its natural position. This is very useful when we want to adjust an element from its natural postion in viewport.

**Eg:**

```css
.myList {
  position: relative;
  top: 20px;
}
```

In this example the element with class myList will move 20px above from its orginal position.

## Absolute positioning

Even tough its name is absolute when we apply this property to an element with property absolute element is positioned with its nearest parent with relative property. when there is no element with property relative out absolute element will be positioned with relative to body of the html.

**Eg:**

```css
.content {
  display: relative;
}
.fig-1 {
  display: absolute;
  top: 20px;
  right: 20px;
}
```

In this example in content class fig-1 class is positioned relative to its parent i.e; content form top 20px and right 20px.
