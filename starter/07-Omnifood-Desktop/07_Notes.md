# Omnifood Project - Setup and Desktop Version

## Responsive Design

### Responsive Design Ingredients

![Responsive Design Ingredients](/starter/07-Omnifood-Desktop/img-notes/Responsive_Design.png)

## Use max-width and rem instead of px

```css
.test-1 {
  max-width: 1000px;
  /* If the container width is larger than the specified max-width, then the width of element is equal the value that was specified for max-width. However, if the container width is less than the specified max-width, then the width of the element will be 100% of the container element width. */
}

.test-2 {
  max-width: 50rem;
  font-size: 2rem;
  /* Default: 1 rem = 16px */
}

html {
  font-size: 10px;
  /* Change the 1 rem => 10px */
}

html {
  /* Correct Way: 
  Change the fixed value of font-size => A percentage of the default font-size 
  */
  font-size: 62.5%;
  /* 10 px /16 px = 0.625 = 62.5% */
  /* Percentage of user's browser font-size setting */
}
```

## Setting Up a Reusable Grid

Create a file named "general.css"

```css
.container {
  /* 1140px */
  max-width: 120rem;
  padding: 0 3.2rem;
  margin: 0 auto;
}

.grid {
  display: grid;
  gap: 9.6rem;
}

.grid--2-cols {
  grid-template-columns: repeat(2, 1fr);
}
.grid--3-cols {
  grid-template-columns: repeat(3, 1fr);
}
.grid--4-cols {
  grid-template-columns: repeat(4, 1fr);
}
```

## Other Tricks

### Add inside border

```css
.btn {
  border: 3px solid #fff;
  /* outside border => inside */
  /* Trick to add border inside */
  box-shadow: inset 0 0 0 3px #fff;
}
```

### Add elements to images

```css
.step-img-box::before {
  content: "";
  display: block;
  width: 60%;
  /* height: 60%; */

  /* 60% of parent's width */
  padding-bottom: 60%;

  background-color: #fae5d3;
  border-radius: 50%;

  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);

  z-index: -1;
  /* elements that have higher value of the index will appear first, so will appear on top */
}
```

### Add grayscale to images

```css
.logos img {
  filter: brightness(0);
  opacity: 50%;
}
```

### Set images unflow

```css
.meal {
  overflow: hidden;
}
```

### Link two elements together

When we click on this label, then you see it automatically selected.

```html
<!-- for & id -->
<div>
  <label for="full-name">Full Name</label>
  <input
    id="full-name"
    type="text"
    placeholder="John Smith"
    name="full-name"
    required=""
  />
</div>
```

### Set focus state

```css
*:focus {
  outline: none;
  /* outline: 4px dotted #e67e22;
  outline-offset: 8px; */
  box-shadow: 0 0 0 0.8rem rgba(230, 125, 34, 0.5);
}
```
