---
title: "CSS Selectors || With code examples"
date: 2022-07-21T22:36:51+05:30
type:
  - posts
  - post
tags:
  - CSS
  - HTML

categories:
  - Web development
author:
  name: Aditya Kadali
---

In web world styling your website is very important to standout in the crowd. These CSS Selectors help developers to styles elements on web page.

## Selectors in CSS

CSS selectors are designed to select an element on web page and style them according to our needs. Styling means their font size, colour, spacing etc.,

These selectors are classified into 5 types they are

- Universal selector
- Type selector
- Class selector
- ID selector
- Attribute selector

### Universal selector

The CSS **universal selector** (`*`) matches elements of any type.

```css
/* Sets color of every element to green */
* {
  color: green;
}
```

These Universal selectors can also be `@name spaced` and we can use to this to select elements in that container or element.

```css
div * {
  background-color: yellow;
}
/* In this example every element inside div is selected*/
```

### Type selector

The CSS **type selector** matches elements by node name. In other words, it selects all elements of the given type within a document.

```css
/* Selects p tag in document */
p {
  font-family: sans-serif;
  font-weight: 600;
}
```

### Class selector

The  **CSS** **class selector** matches elements based on the contents of their `class` attribute.

```css
.warning {
  background-color: red;
  color: white;
}
/* sets bg red and color white to all elemments with warning class*/
```

### ID Selector

The CSS **ID selector** matches an element based on the value of the element's [`id`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/id) attribute. In order for the element to be selected, its `id` attribute must match exactly the value given in the selector.

```css
#item {
  border: 2px solid red;
}

/* Sets border red to all elements with ID item*/
```

### Attribute selector

The CSS **attribute selector** matches elements based on the presence or value of a given attribute.

```css
/* <a> elements whose class attribute contains the word "logo" */
a[class~="logo"] {
  padding: 2px;
}
```

This can be used to target specific elements like we can target all external links

```css
a[target="_blank"] {
  background-color: red;
}
/* this targets all a tags with attrib target="_blank" */
```

## Grouping of selectors

we can group two or more selectors with `,` selects all matching nodes

```css
h1,
h2,
h3 {
  font-family: Sans-serif;
}
/* this selects h1 h2 h3 and applies custom fonts to them */
```

#### Invalid grouping

when using these grouping selectors we must be very careful when one selector is invalid entire style gets ignored

**Eg:**

```css
h1,
#id::unsupported {
  font-family: sans-serif;
}
```

In the above example id selector is invalid so this style is not applied to h1 as well and entire style gets ignored

#### `:is` & `:where` to avoiding invalid grouping

A way to remedy this is to use the `:is()` or `:where()` selectors, which accept a forgiving selector list. This will ignore invalid selectors in the list but accept those which are valid.

we will discuss more about these in our next article

## Comibanators

### Desendent combinator

The **descendant combinator** — typically represented by a single space (" ") character — combines two selectors such that elements matched by the second selector are selected if they have an ancestor (parent, parent's parent, parent's parent's parent, etc) element matching the first selector. Selectors that utilize a descendant combinator are called *descendant selectors*.

```css
/* List items that are descendants of the "my-things" list */
ul.my-things li {
  margin: 2em;
}
```

### Child combinator

The **child combinator** (`>`) is placed between two CSS selectors. It matches only those elements matched by the second selector that are the direct children of elements matched by the first.

```css
/* List items that are children of the "my-things" list */
ul.my-things > li {
  margin: 2em;
}
```

### General sibling combinator

The **general sibling combinator** (`~`) separates two selectors and matches *all iterations* of the second element, that are following the first element (though not necessarily immediately), and are children of the same parent element.

```css
/* Paragraphs that are siblings of and
   subsequent to any image */
img ~ p {
  color: red;
}
```

### Adjacent sibling combinator

The **adjacent sibling combinator** (`+`) separates two selectors and matches the second element only if it *immediately* follows the first element, and both are children of the same parent element.

```css
/* Paragraphs that come immediately after any image */
img + p {
  font-weight: bold;
}
```
