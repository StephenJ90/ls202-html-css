##### LS202 HTML and CSS > Lesson 2: The Box Model

---

### Practice Problems: The Box Model

---

1. Given the code below, what is the minimum width and height (in pixels) that the `div` needs to entirely contain the `img` element (including its margins)?

   ```html
   <div>
     <img src="#" alt="test" />
   </div>
   ```

   ```css
   div {
     background-color: lightgray;
     border: 1px solid black;
     box-sizing: border-box;
     display: inline-block;
     margin: 0;
     padding: 0;
   }
   
   img {
     border: 4px solid red;
     box-sizing: content-box;
     display: inline-block;
     height: 300px;
     margin: 20px 19px 10px 11px;
     padding: 10px 20px;
     width: 500px;
   }
   ```

###### Solution:

Since the `img` has `display: inline-block`, we can compute the dimensions directly from the CSS properties. The element needs 580 pixels horizontally:

   - 500 pixels for the width
   - 8 pixels for the left and right borders
   - 40 pixels for the left and right padding
   - 11 pixels for the left margin
   - 19 pixels for the right margin
   - 2 pixels for the left and right borders of the `div`

   It needs 360 pixels vertically:

   - 300 pixels for the height
   - 8 pixels for the top and bottom borders
   - 20 pixels for the top and bottom padding
   - 20 pixels for the top margin
   - 10 pixels for the bottom margin
   - 2 pixels for the top and bottom borders of the `div`

   Since the `div` uses `border-box` box-sizing, it must have a width and height of at least 580px and 360px, respectively.

   While we don't typically count margins in determining an element's height and width, we need to include them here when calculating how much space we need in the `div`.

---

2. Given the code below, what is the minimum width and height (in pixels) that the `div` needs to entirely contain the `section` element (including its margins)? How does this differ from the result of the previous practice problem?

   ```html
   <div>
     <section>content</section>
   </div>
   ```

   ```css
   div {
     background-color: lightgray;
     border: 1px solid black;
     box-sizing: border-box;
     display: inline-block;
     margin: 0;
     padding: 0;
   }
   
   section {
     border: 4px solid red;
     box-sizing: content-box;
     display: block;
     height: 300px;
     margin: 20px 19px 10px 11px;
     padding: 10px 20px;
     width: 500px;
   }
   ```

###### Solution:

Since the `section` element is a `block` element, we can compute the dimensions directly from the CSS properties, same as the previous solution. Since the `div` uses `border-box` box-sizing, it must have a width and height of at least 580px and 360px, respectively. These values are identical to the answer from the previous practice problem. The chief difference is that other elements may appear adjacent to the `img` in problem 1, while the `section` in this problem will always be on a line by itself within the `div` no matter its width.

---

3. Given the code below, what is the minimum width and height (in pixels) that the `div` needs to entirely contain the `em` element (including its margins)?

   ```html
   <div>
     <em>content</em>
   </div>
   ```

   ```css
   div {
     background-color: lightgray;
     border: 1px solid black;
     box-sizing: border-box;
     display: inline-block;
     margin: 0;
     padding: 0;
   }
   
   em {
     border: 4px solid red;
     box-sizing: content-box;
     display: inline;
     height: 300px;
     margin: 20px 19px 10px 11px;
     padding: 10px 20px;
     width: 500px;
   }
   ```

###### Solution:

This code is a bit tricky. Since the `em` element is `inline`, the browser will ignore the width, height, and top and bottom margins specified in the CSS. For this reason, we cannot calculate the amount of space that any given `em` will take unless we know the actual width and height of the content.

   If we assume the `em` requires a 50px width, then the element needs 130 pixels horizontally:

   - 50 pixels for the assumed width
   - 8 pixels for the left and right borders
   - 40 pixels for the left and right padding
   - 11 pixels for the left margin
   - 19 pixels for the right margin
   - 2 pixels for the left and right borders of the `div`

   If we assume the `em` requires a 20px height, then it needs 50 pixels vertically:

   - 20 pixels for the assumed height
   - 8 pixels for the top and bottom borders
   - 20 pixels for the top and bottom padding
   - 0 pixels for the top and bottom margins
   - 2 pixels for the top and bottom borders of the `div`

   Since the `div` uses `box-sizing`, it must have a `width` of at least 130px and a height of at least 50px.

   Keep in mind that the top and bottom padding and borders may intersect with content above and below the `em` element.

---

4. Given the code below, what is the minimum width and height (in pixels) that the `div` needs to be to entirely contain the `article` element (including its margins)?

   ```html
   <div>
     <article>content</article>
   </div>
   ```

   ```css
   div {
     background-color: lightgray;
     border: 1px solid black;
     box-sizing: border-box;
     display: inline-block;
     margin: 0;
     padding: 0;
   }
   
   article {
     border: 4px solid red;
     box-sizing: border-box;
     display: inline-block;
     height: 300px;
     margin: 20px 19px 10px 11px;
     padding: 10px 20px;
     width: 500px;
   }
   ```

###### Solution:

Since the `article` is `inline-block`, we can compute the dimensions directly from the CSS properties. Since we also set the `box-sizing` property to `border-box`, we must ignore the padding and border to calculate the actual dimensions. The element needs 532 pixels horizontally:

   - 500 pixels for the width
   - 0 pixels for the left and right borders
   - 0 pixels for the left and right padding
   - 11 pixels for the left margin
   - 19 pixels for the right margin
   - 2 pixels for the left and right borders of the `div`

   It needs 332 pixels vertically:

   - 300 pixels for the height
   - 0 pixels for the top and bottom borders
   - 0 pixels for the top and bottom padding
   - 20 pixels for the top margin
   - 10 pixels for the bottom margin
   - 2 pixels for the top and bottom borders of the `div`

   Since the `div` uses `box-sizing`, it must have a `width` of at least 532px and a height of at least 332px.

---

5. Given the code below:

   ```html
   <div>
     <tag1>content</tag1><tag2>content</tag2>
   </div>
   ```

   ```css
   div {
     background-color: lightgray;
     border: 1px solid black;
     box-sizing: content-box;
     display: inline-block;
     margin: 0;
     padding: 0;
     width: 720px;
   }
   
   tag1, tag2 {
     box-sizing: border-box;
     height: 240px;
     margin: 0;
     padding: 0;
     width: 360px;
   }
   
   tag1 {
     background-color: yellow;
   }
   
   tag2 {
     background-color: lime;
   }
   ```

  Which of the following element pairs will display side-by-side in the `<div>`? Select all that apply:

   1. Both elements are `block` elements.
   2. Both elements are `inline` elements.
   3. Both elements are `inline-block` elements.
   4. One element is a `block` element, and one is an `inline` element.
   5. One element is a `block` element, and one is an `inline-block` element.
   6. One element is an `inline` element, and one is an `inline-block` element.

###### Solution:

Combinations (2), (3), and (6) will all appear side-by-side. The other three combinations have `block` elements which never appear side-by-side with anything.

---

6. Will the following code display the two article boxes side-by-side? If not, why not? How would you fix it so that it places the boxes side-by-side?

   ```html
   <section>
    <article>content</article><article>more content</article>
   </section>
   ```

   ```css
   section {
     background-color: yellow;
     border: 1px solid red;
     box-sizing: content-box;
     display: inline-block;
     height: 400px;
     margin: 0px;
     padding: 20px;
     width: 900px;
   }
   
   article {
     background-color: lime;
     border: 1px solid blue;
     height: 100%;
     margin: 0;
     padding: 10px;
     width: 50%;
   }
   ```

###### Solution:

The browser won't display the article boxes side-by-side since they are `block` elements. Even if we could place the `block` elements side-by-side, they won't fit inside the section because the total width of each article is 50% of the width plus 22 pixels for its padding and border.

The first change we must make is to add `display: inline-block;` to the CSS `article` selector, which lets us position two or more articles side-by-side, provided there is room. To make them fit, we must set the actual width (including padding and the border) to 50% of the available space, so we also add `box-sizing: border-box;` to the `article` selector.  

   ```css
   article {
     background-color: lime;
     border: 1px solid blue;
     box-sizing: border-box;
     display: inline-block;
     height: 100%;
     margin: 0;
     padding: 10px;
     width: 50%;
   }
   ```

---

7. **Challenge.** Given our solution to the previous question, what will happen if we put the `article` tags on separate lines?

   ```html
   <section>
     <article>content</article>
     <article>more content</article>
   </section>
   ```

   Try to figure out the answer without peeking. Why do you think this is?

###### Solution:

  When you put the `article` elements on separate lines in the HTML, the browser sees the whitespace (a newline and several spaces in this case) between the two articles. It then collapses that whitespace into a single space character and uses the result as content between the elements. Thus, the two articles require 900 pixels total plus a few more pixels to account for the space character. Since that exceeds the 900-pixel width of the `section`, the two `article`s no longer fit on the same line.

  This kind of problem often occurs when one of the elements is an inline-block; the rest of the time, the extra space typically doesn't matter. Aside from placing the two tags up against each other to eliminate the whitespace, there are several other techniques you will see later that let you remove the space or make it invisible.
