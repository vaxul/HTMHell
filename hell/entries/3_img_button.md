---
title: "#3 image-buttons"
date: 2019-10-22
author: mmatuzo
permalink: /{{ title | slug }}/index.html
badcode: '<img src="/images/edit.gif" onclick="openEditDialog(123)">
<img src="/images/delete.gif" onclick="openDeleteDialog(123)">'
goodcode1: '<button onclick="openEditDialog(123)">
  <img src="/images/edit.gif" alt="Edit product XY">
</button>

<button onclick="openDeleteDialog(123)">
  <img src="/images/delete.gif" alt="Delete product XY">
</button>'

goodcode2: '<button onclick="openEditDialog(123)">
<span class="sr-only">Edit product XY</span>
  <img src="/images/edit.gif" alt="">
</button>

<button onclick="openDeleteDialog(123)">
<span class="sr-only">Delete product XY</span>
  <img src="/images/delete.gif" alt="">
</button>'

goodcodeCSS: '.sr-only {
position: absolute;
white-space: nowrap;
width: 1px;
height: 1px;
overflow: hidden;
border: 0;
padding: 0;
clip: rect(0 0 0 0);
clip-path: inset(50%);
margin: -1px;
}'
---

<div class="section">

## Bad code

```html
{{ badcode | pretty }}
```
</div>

<div class="section">

## Issues and how to fix them

1. The purpose of the `img` element is to display images, not to execute JavaScript.
1. A click event on a `img` triggers only on click. A click event on a `button` triggers on click and if the users presses the <kbd>Enter</kbd> or <kbd>Space</kbd> key.
1. There's no text alternative for the image.
</div>

<div class="section">

## Good code

### Solution #1: Use buttons and add `alt` attribute to images

```html
{{ goodcode1 | pretty }}
```

### Solution #2: Use buttons, add text content and hide images

Unfortunately, there’s no native way of hiding content only visually.  
This class makes sure that content is visually hidden but still accessible to screen reader users.

```css
{{ goodcodeCSS | prettyCSS }}
```

An image with an empty `alt` attribute is not accessible to screen reader users, which in this case is desired, because there’s a screen reader accessible text alternative.

```html
{{ goodcode2 | pretty }}
```
</div>


