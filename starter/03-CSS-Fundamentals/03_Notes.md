# 03 CSS Fundamentals

## Conflicts between selectors

Priority level:
High -> Low

1. Declarations marked !important
2. Inline style
3. ID (#) selector
4. Class (.) or pseudo-class (:) selector
5. Element selector (p, div, li, etc.)
6. Universal selector (\*)
7. Inherited values

```css
#copyright {
  color: red;
}

.copyright {
  color: blue;
}

.text {
  color: yellow;
}

footer p {
  color: green !important;
} */
```

## Collapsing Margins

If the margin setting of the two elements is different, the larger one is brought into effect.

## Centering our Page

```css
.container {
  width: 800px;
  /* margin-left: auto;
  margin-right: auto; */
  margin: 0 auto;
}
```

## Types of Boxes

1. Inline element
2. Inline-block element
3. Block-level element\*/

- Anchor element is an inline element where the box model does not create any vertical space.
- An img is an inline-block element.

```css
nav a:link {
  background-color: orangered;
  margin: 20px;
  padding: 20px;
  /* change them to block-level elements*/
  display: block;

  margin-right: 30px;
  margin-top: 10px;
  /* change them to inline-block elements*/
  display: inline-block;
}
```

## Positioning Modes

1. Normal Flow: Default positioning, element is "in flow", position: relative.
2. Absolute Positioning: element is "out of flow", position: absolute.

```css
.container {
  position: relative;
}

button {
  font-size: 22px;
  padding: 20px;
  cursor: pointer;
  /* Absolute Positioning */
  position: absolute;
  /* 1. absolute position of the viewpoint */
  /* top: 50px;
  left: 50px; */

  /* 2. absolute position of the page */
  /* set the relative position of container */
  bottom: 50px;
  right: 50px;
}
```

![Positioning Modes](/starter/03-CSS-Fundamentals/img-notes/Positioning_Modes.png)

## Pseudo-classes

```css
li:first-child {
  font-weight: bold;
}

li:last-child {
  font-style: italic;
}

li:nth-child(odd) {
  /* color: aquamarine; */
}
```

## Pseudo-elements

```css
h1::first-letter {
  font-style: normal;
  margin-right: 5px;
}

h2::first-letter {
  font-size: 80px;
}

/* adjacent sibling selector */
/* only the paragraphs that are immediately after the H3 have been selected */
h3 + p::first-line {
  /* color: red; */
}
```

Using with box model

```css
h2 {
  /* background-color: orange; */
  position: relative;
}

h2::after {
  content: "TOP";
  background-color: #ffe70e;
  color: #444;
  font-size: 16px;
  font-weight: bold;
  display: inline-block;
  padding: 5px 10px;
  position: absolute;
  top: -10px;
  right: -25px;
}
```

![Pseudo elements with box model](/starter/03-CSS-Fundamentals/img-notes/Pseudo_elements_with_box_model.png)

## Developer Skill #1: Googling and Eeading Documentation

- Google
- stackoverflow
- MDN Documentation

example ->

- css property to add mouse to button.
- css how to center anchor elements.

## Developer Skill #2: Debugging and Asking Questions

- HTML Validator: Check the error of the HTML code.
- Diffchecker: Compare the original code with my code to find diffenences.
- Select for Compare in VSCode
