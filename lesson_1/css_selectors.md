##### LS202 HTML and CSS > Lesson 1: Your First Web Pages

---

Practice Problems: CSS Selectors

---

1. Set the width of the page body to `600px`.

```css
body {
  width: 600px;
}
```

---

2. Set the font size on all paragraphs to `18px`.

```css
p {
  font-size: 18px;
}
```

---

3. Change the font for all list items (the `li` tags) to a `monospace` font, and give them a color of `purple`.

```css
li {
  color: purple;
  font-family: monospace;
}
```

---

4. Remove the underlines from all links on the page.

```css
a {
  text-decoration: none;
}
```

---

5. Change the `li` selector from problem 3 so that it no longer styles the lists inside the `header` section. Don't add any new CSS, but you can modify the selector for an existing rule. Afterward, the list items in the header should be blue with a proportional (non-monospace) font, and the numbers should be black. All remaining list items should be purple and monospace.

```css
main li {
  color: purple;
  font-family: monospace;
}
```

---

6. Set the color on all paragraphs that are inside an `article` element to `brown`.

```css
article p {
  color: brown;
}
```

---

7. Add the background color `#e0e0e0` to the "First Article" heading.

```css
.subheading {
  background-color: #e0e0e0;
}
```

---

8. Set the font size for the element with ID `intro` to `24px`.

```css
#intro {
  font-size: 24px;
}
```

---

9. **Challenge**: Change the color for all list items directly within an unordered list in the `main` section to `green`. Be careful not to change any of the list items that don't belong to an unordered list, nor any of the list items in the `header` element.

```css
main ul > li {
  color: green;
}
```
