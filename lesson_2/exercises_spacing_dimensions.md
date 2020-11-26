##### LS202 HTML and CSS > Lesson 2: The Box Model

---

### Practice Problems: Spacing and Dimensions

---

In these practice problems, we'll work with heights, widths, padding, margins, and a variety of dimensional units.

Some of the problems use an image. You may use it in your html like this:

```html
<img src="https://d3jtzah944tvom.cloudfront.net/lesson_2/exercises_dimension_and_spacing/H%C3%B4tel_des_Invalides_-_20150801_16h09_%2810630%29.jpg"
    alt="Demonstration of image sizing" />
```

1. Use CSS to set a fixed width on the image of 800 pixels, and center it in the window horizontally.

###### Solution:

`auto` margins work for `block` elements, but not `inline` or `inline-block`, so you must also set the `display` style when trying to center an `img`.

```css
img {
  display: block;
  margin: 0 auto; /* 0: top and bottom margin, auto: left and right */
  width: 800px;
}
```

`margin: XXX auto;` is a common way to center block content; learn it and use it, where `XXX` is the size of the top and bottom margins, while `auto` applies to the left and right margins. An XXX value of 0 means no top and bottom margins.

---

2. Using the code from the previous problem, change the `width` property for `img` to `100%`, and set the `max-width` property to `800px`. The image should expand to fit any container width up to 800 pixels. Resize your browser width and watch how that affects the photograph.

###### Solution:

```css
img {
  display: block;
  margin: 0 auto;
  max-width: 800px;
  width: 100%;
}
```

---

3. Using the code from the previous problem, set a fixed height on the image of 533 pixels. Resize the browser window and watch how the image dimensions change.

###### Solution:

```css
img {
  display: block;
  height: 533px;
  margin: 0 auto;
  max-width: 800px;
  width: 100%;
}
```

---

4. As you can see, having a variable size for one dimension and fixed for the other makes for a container with strange behavior: this one stretches horizontally but remains fixed vertically. Remove the height and update the CSS to ensure the width does not get smaller than 500 pixels.

###### Solution:

```css
img {
  display: block;
  margin: 0 auto;
  width: 100%;
  max-width: 800px;
  min-width: 500px;
}
```

---

5. Create a new HTML page with two consecutive `div` elements. Make each a fixed width and height of 300 pixels. Set the background color on the first `div` to `"#fcc"` (red) and the second to `"#ccf"` (blue).

###### Solution:

```html
<div class="red"></div>
<div class="blue"></div>
```

```css
div {
  height: 300px;
  width: 300px;
}

.red {
  background-color: #fcc;
}

.blue {
  background-color: #ccf;
}
```

---

6. Add a 5-pixel solid black border to the blue `div`. Compare the widths of the two boxes. Why is the blue box a different size?

###### Solution:

```css
.blue {
  background-color: #ccf;
  border: 5px solid black;
}
```

By default, the CSS box model uses a value of `content-box` on all elements which means the browser doesn't include the padding or border in the `width` and `height`. Instead, it adds the padding and border sizes to calculate the dimensions of the element.

---

7. Add 20 pixels padding to all four sides of the red `div`. Notice the different widths again. Add a CSS property to both elements to ensure the total width for each is `300px` rather than `300px` and then some.

###### Solution:

```css
div {
  box-sizing: border-box;
  height: 300px;
  width: 300px;
}

.red {
  background-color: #fcc;
  padding: 20px;
}
```

Use the `box-sizing` property to change how the box model treats padding and borders. When set to `border-box`, the browser includes both padding and borders as part of the total dimensions.

---

8. Change both boxes to place them side-by-side instead of stacked vertically. If necessary, increase the width of your browser window.

###### Solution:

```css
div {
  display: inline-block;
  box-sizing: border-box;
  height: 300px;
  width: 300px;
}
```

---

9. Add 20px of space between the red and blue boxes.

###### Solution:

```css
.red {
  background-color: #fcc;
  margin-right: 20px;
  padding: 20px;
}
```

---

10. Create a new HTML file with the following CSS and HTML:

```html
<body>
  <ul>
    <li>Item 1</li><!--
    --><li>Item 2</li><!--
    --><li>Item 3</li><!--
    --><li>Item 4</li>
  </ul>
</body>
```

```css
 body {
  margin: 50px;
}

ul {
  background-color: #a7ceff;
  border: 10px solid blue;
  list-style: none;
  padding: 0;
}

li {
  background-color: #ffc;
  border: 10px solid red;
  box-sizing: border-box;
  line-height: 120px;
  min-height: 120px;
  text-align: center;
}
```

###### Solution:

```css
li {
  background-color: #ffc;
  border: 10px solid red;
  box-sizing: border-box;
  display: inline-block; /* added */
  line-height: 120px;
  min-height: 120px;
  text-align: center;
  width: 25%; /* added */
}
```

To understand the comments, review the challenge exercise at the end of the practice problems for the box model. In that example, we ensured that there was no space between consecutive items by making their tags adjacent. The comments here are a variation on this theme: the browser ignores them entirely, so we end up with adjacent elements.

Annoying, right? Yes, but a necessary evil you must learn to manage. Breaking this behavior would cause other problems, so we're stuck with it for now. Try removing the comments from the above code temporarily to see for yourself how that extra whitespace makes a difference.

---

11. Using the code from the previous problem solution, set the left and right margin on each `li` element to 1%, but do not let the inner boxes wrap around - they must all continue to fit on the same line with no change in the outer box's size.

###### Solution:

We need to remove 2% from each element's width to account for the 1% margin. (`100% - 4 * ( 1% + 1% ) ==> 92%, 92% / 4 => 23%`)

```css
li {
  background-color: #ffc;
  border: 10px solid red;
  box-sizing: border-box;
  display: inline-block;
  line-height: 120px;
  margin: 0 1%; /* added */
  min-height: 120px;
  text-align: center;
  width: 23%; /* altered */
}
```
