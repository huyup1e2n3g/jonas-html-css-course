# 08 Omnifood Project - Responsive Web Design

## How Media Queries Work

![Media Queries](/starter/08-Omnifood-Responsive/img-notes/Media_Queries.png)

```css
@media (max-width: 1200px) {
  .section-hero {
    background-color: rebeccapurple;
  }
}
```

`rem` and `em` do NOT depend on html font-size in media queries!

Insted, 1rem = 1em = 16px

`rem` apparently has some bugs in some browsers when used in media queries but `em`.

## How to Select Breakpoints

Breakpoints are the viewpoint width at which we want our design to change.
Breakpoints are the pixel values that we want to put in our media queries.

![How to Select Breakpoints](/starter/08-Omnifood-Responsive/img-notes/Breakpoints.png)

## Meditech

The Meditech is actually for responsive web design in HTML structure.

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```

Without this Meditech here, responsive web design will actually not work on physical mobile devies, so not on phones and not on tablets. And the reason for that is that browsers on mobile devies will basically zoom the page out default until it fits the screen, and so that's not what we want with media queries. We simply want to make out entire layout. So our entire design smaller, so less wide. And therefore, we need this line of code here, which will make it so that the page will actually match the screen width.

## Other tricks

### [Selector] Select element based on this name attribute

```css
/* 
<ion-icon class="icon-mobile-nav" name="menu-outline"></ion-icon>
<ion-icon class="icon-mobile-nav" name="close-outline"></ion-icon> 
*/

.icon-mobile-nav[name="close-outline"] {
  display: none;
}
```

### Setting Hide or Show

```css
.main-nav {
  /* Hide navigation */
  /* Allows NO transitions at all */
  /* display: none; */

  /* 1) Hide it visually */
  opacity: 0;

  /* 2) Make it unaccessible to mouse and keyboard */
  pointer-events: none;

  /* 3) Hide it from screen readers */
  visibility: hidden;
}

/* SHOW */
.nav-open .main-nav {
  opacity: 1;
  pointer-events: auto;
  visibility: visible;
}
```

### Animation: moving navigation from right side

```css
html,
body {
  /* Only works if there is nothing abso lutely positioned in relation to body */
  overflow-x: hidden;
}

.header {
  position: relative;
}

.main-nav {
  position: absolute;
  transform: translateX(100%);

  /* Animation */
  transition: all 1s ease-in;
}

/* When .nav-open setting .main-nav */
.nav-open .main-nav {
  transform: translateX(0);
}
```
