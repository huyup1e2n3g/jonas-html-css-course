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
