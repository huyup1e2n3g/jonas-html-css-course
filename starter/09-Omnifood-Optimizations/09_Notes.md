# 09 Omnifood Project - Effects, Optimizations and Deployment

## Implementing Smooth Scrolling

```css
html {
  /* Does NOT work on Safari */
  scroll-behavior: smooth;
}
```

```html
<!-- Fix safari problem -->
<head>
  <script
    defer
    src="https://unpkg.com/smoothscroll-polyfill@0.4.4/dist/smoothscroll.min.js"
  ></script>
</head>
```

## Browser Support

[caniuse](caniuse.com)

## Fixing Safari flexbox gap

```javascript
///////////////////////////////////////////////////////////
// Fixing flexbox gap property missing in some Safari versions
function checkFlexGap() {
  var flex = document.createElement("div");
  flex.style.display = "flex";
  flex.style.flexDirection = "column";
  flex.style.rowGap = "1px";

  flex.appendChild(document.createElement("div"));
  flex.appendChild(document.createElement("div"));

  document.body.appendChild(flex);
  var isSupported = flex.scrollHeight === 1;
  flex.parentNode.removeChild(flex);
  console.log(isSupported);

  if (!isSupported) document.body.classList.add("no-flexbox-gap");
}
checkFlexGap();
```

```css
/**************************/
/* Fixing Safari flexbox gap */
/**************************/

.no-flexbox-gap .main-nav-list li:not(:last-child) {
  margin-right: 4.8rem;
}

.no-flexbox-gap .list-item:not(:last-child) {
  margin-bottom: 1.6rem;
}

.no-flexbox-gap .list-icon:not(:last-child) {
  margin-right: 1.6rem;
}

.no-flexbox-gap .delivered-faces {
  margin-right: 1.6rem;
}

.no-flexbox-gap .meal-attribute:not(:last-child) {
  margin-bottom: 2rem;
}

.no-flexbox-gap .meal-icon {
  margin-right: 1.6rem;
}

.no-flexbox-gap .footer-row div:not(:last-child) {
  margin-right: 6.4rem;
}

.no-flexbox-gap .social-links li:not(:last-child) {
  margin-right: 2.4rem;
}

.no-flexbox-gap .footer-nav li:not(:last-child) {
  margin-bottom: 2.4rem;
}

@media (max-width: 75em) {
  .no-flexbox-gap .main-nav-list li:not(:last-child) {
    margin-right: 3.2rem;
  }
}

@media (max-width: 59em) {
  .no-flexbox-gap .main-nav-list li:not(:last-child) {
    margin-right: 0;
    margin-bottom: 4.8rem;
  }
}
```

## Testing Performance With Lighthouse

## Adding Favicon and Meta Description

```html
<head>
  <meta
    name="description"
    content="Omnifood is an AI-powered food subscription that will make you eat healthy again, 365 days per year. It's tailored to your personal tastes and nutritional needs."
  />

  <link rel="icon" href="img/favicon.png" />
  <link rel="apple-touch-icon" href="img/apple-touch-icon.png" />
  <link rel="manifest" href="manifest.webmanifest" />

  <title>Omnifood &mdash; Never cook again!</title>
</head>
```

```webmanifest
<!-- manifest.webmanifest -->
{
  "icons": [
    { "src": "img/favicon-192.png", "type": "image/png", "sizes": "192x192" },
    { "src": "img/favicon-512.png", "type": "image/png", "sizes": "512x512" }
  ]
}
```

## Image Optimizations

Resize/Compress/Edit the images.

[squoosh](squoosh.app)

-> webp

```html
<picture>
  <source srcset="img/hero.webp" type="image/webp" />
  <source srcset="img/hero-min.png" type="image/png" />

  <img
    src="img/hero-min.png"
    class="hero-img"
    alt="Woman enjoying food, meals in storage container, and food bowls on a table"
  />
</picture>
```

## Deployment to Netlify
