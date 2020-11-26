##### LS202 HTML and CSS > Lesson 3: Images

---

### Practice Problems: Images and Figures

---

These practice problems use this image `https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/cats.jpg`.

1. Write HTML to display the image. Don't use a `<figure>` or `<figcaption>` right now.

```html
<img src="https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/cats.jpg"
     alt="Two Cats: Butterscotch and Pudding" />
```

---

2. Use CSS to set the width of the image to 250 pixels.

```css
img {
  width: 250px;
}
```
Since we specified a width but no height, the height adjusted automatically to maintain the same aspect ratio.

---

3. Update the CSS width from the previous problem with a height of 350 pixels.

```css
img {
  height: 350px;
}
```
Since we specified a height but no width, the width adjusted automatically to maintain the same aspect ratio.

---

4. Set the width of the image to 400 pixels, but keep the height at 350px.

```css
img {
  height: 350px;
  width: 400px;
}
```

---

5. Remove the CSS for the `img` element, and wrap the `<img>` in a `<figure>` tag with a yellow background.

```html
<figure>
  <img src="https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/cats.jpg"
       alt="Two Cats: Butterscotch and Pudding" />
</figure>
```

```css
/*
img {
  height: 350px;
  width: 400px;
}
*/

figure {
  background-color: yellow;
}
```

6. Add a caption below the image.

```html
<figure>
  <img src="https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/cats.jpg"
       alt="Two Cats: Butterscotch and Pudding" />
  <figcaption>
    Butterscotch and Pudding held still long enough for me to capture this
    picture of both of them.
  </figcaption>
</figure>
```

---

7. Move the caption above the image.

```html
<figure>
  <figcaption>
    Butterscotch and Pudding held still long enough for me to capture this
    picture of both of them.
  </figcaption>
  <img src="https://d3jtzah944tvom.cloudfront.net/202/images/lesson_3/cats.jpg"
       alt="Two Cats: Butterscotch and Pudding" />
</figure>
```
