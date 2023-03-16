# 04 CSS Layouts

## The 3 Ways of Building Layouts

Two types of layout:

- Page Layout
- Component Layout

The 3 ways of building layouts with CSS

1. Float Layouts: The old way of building layouts of all sizes, using the float CSS property. Still used, but getting outdated fast.
2. Flexbox: Modern way of laying out elements in a 1-dimensional row without using floats. Perfect for component layouts.
3. CSS Grid: For laying out element in a fully-fledged 2-dimensional grid. Perfect for page layouts and complex components.

![The 3 ways of building layouts with CSS](/starter/04-CSS-Layouts/img-notes/CSS_Layouts_Ways.png)

## Floats

<b>Using floats</b>

```css
.author-img {
  float: left;
  margin-bottom: 20px;
}

.author {
  float: left;
  padding-top: 10px;
  margin-left: 20px;
}
```

<b>Collaping elements</b>

The reason is that all of its (container) child elements are floated. This means that it's as if these elements would not even be on the page. So as if they had been removed. And so now, the element basically has no content anymore. And so that way it makes sense that its height is actually zero.

![Collaping height](/starter/04-CSS-Layouts/img-notes/Floats_Collapsing_Elements.png)

<b>Floats vs. Absolute Positioning</b>

- Floats = Absolute Positioning:

Element is removed from the normal flow: "out of flow".

- Floats != Absolute Positioning:

Text and inline elements will wrap around the floated element.

For example

```html
<header>
  <h1></h1>
  <nav></nav>
</header>
```

```css
h1 {
  float: left;
}

nav {
  float: right;
}
```

<b>Clear Floats</b>

Use `clear` To solve the problem of collapsing height.

> The simplist way, but not the best way.

```html
<header>
  <h1></h1>
  <nav></nav>
  <div class="clear"></div>
</header>
```

```css
h1 {
  float: left;
}

nav {
  float: right;
}

.clear {
  clear: both;
}
```

![Clear Floats](/starter/04-CSS-Layouts/img-notes/Clear_Floats.png)

<b>Clearfix Hack</b>

> To avoid empty div used in the technique of `clear`.

```html
<header class="clearfix">
  <h1></h1>
  <nav></nav>
</header>
```

```css
h1 {
  float: left;
}

nav {
  float: right;
}

/* Doing this is exactly the same as adding this empty div manually */
.clearfix::after {
  clear: both;
  content: "";
  display: block;
}
```

## Box-sizing: Border-box

![Box-sizing](/starter/04-CSS-Layouts/img-notes/Box-sizing.png)

```css
/* A simple global reset like this, and then basically enabling this better behaviour of the box model on every single element */
* {
  box-sizing: border-box;
}
```

## Flexbox

Flexbox Terminology

![Flexbox Terminology](/starter/04-CSS-Layouts/img-notes/Flexbox_Terminology.png)

Flexbox Properties

![Flexbox Properties](/starter/04-CSS-Layouts/img-notes/Flexbox_Properties.png)
