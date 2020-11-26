##### LS202 HTML and CSS > Lesson 4: Lists and Tables

---

### Practice Problems: Lists

---

1. Using the "Raw Text" shown below, create a Web page that looks like the image pictured below it.

```plaintext
The Next Reckoning: Capitalism and Climate Change
By NATHANIEL RICH
The world’s most difficult problem has a solution so simple that it can be
expressed in four words: Stop burning greenhouse gases. How exactly to pull
this off is somewhat more complicated — just not as complicated as most
Americans have been led to believe.

Related articles
What Survival Looks Like After the Oceans Rise
How Big Business is Hedging Against the Apocalypse
Climate Chaos is Coming–and the Pinkertons Are Ready
```

**[image not shown]**

###### Solution:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title></title>
    <meta charset="utf-8" />
    <style>
      h1 {
        width: 700px;
      }

      p {
        width: 700px;
      }
    </style>
  </head>
  <body>
    <header>
      <h1>The Next Reckoning: Capitalism and Climate Change</h1>
      <p>By NATHANIEL RICH</p>
    </header>
    
    <p>
      The world’s most difficult problem has a solution so simple that it
      can be expressed in four words: Stop burning greenhouse gases. How 
      exactly to pull this off is somewhat more complicated — just not as
      complicated as most Americans have been led to believe.
    </p>

    <h2>Related Articles</h2>
    <ul>
      <li>What Survival Looks Like After the Oceans Rise</li>
      <li>How Big Business is Hedging Against the Apocalypse</li>
      <li>Climate Chaos is Coming–and the Pinkertons Are Ready</li>
    </ul>
  </body>
</html>
```

If I leave out the width in `p` and `h1` then the only way to achieve the same results as the image[not shown] is to adjust the size of the browser. Using the widths allows for the text to wrap as it is in the image.

---

2. Add CSS to your solution for the previous problem to remove the bullet character before each list item.

###### Solution:

```css
  ul {
    list-style-type: none;
  }
``` 

---

3. Using the "Raw Text" shown below, create a Web page that looks like the image pictured below it.

```plaintext
5 Reasons to Use jQuery
Open Source
Endless Tutorials
Huge Library
Cross-browser Compatibility
Large Variety of Plugins
```

[image not shown]

###### Solution:

```html
<h1>5 Reasons to Use jQuery</h1>
<ol>
  <li>Open Source</li>
  <li>Endless Tutorials</li>
  <li>Huge Library</li>
  <li>Cross-browser Compatibility</li>
  <li>Large Variety of Plugins</li>
</ol>
```

---

4. Add CSS to your solution for the previous problem to change the numbers from decimal to uppercase Roman digits (I, II, III, IV, V).

###### Solution:

```html
<style>
  ol {
    list-style-type: upper-roman;
  }
</style>
```

---

5. Update your solution from the previous problem to number the items in descending order (V, IV, III, II, I).

###### Solution:

```html
<h2>5 Reasons to Use jQuery</h2>
<ol reversed>                       <!- new code ->
  <li>Open Source</li>
  <li>Endless Tutorials</li>
  <li>Huge Library</li>
  <li>Cross-browser Compatibility</li>
  <li>Large Variety of Plugins</li>
</ol>
```

Before HTML5, you would have had to code this as:

```html
<ol reversed="reversed">
```

---

6. Using the "Raw Text" shown below, create a Web page that looks like the image pictured below it.

```plaintext
HTML
Hypertext Markup Language, a standardized system for tagging text files to
achieve font, color, graphic, and hyperlink effects on World Wide Web pages.

Semantic
Relating to meaning in language or logic.

CSS
A style sheet language used for describing the presentation of a document
written in a markup language.
```

**[image not shown]**

###### Solution:

```html
<dl>
  <dt>HTML</dt>
  <dd>
    Hypertext Markup Language, a standardized system for tagging text files
    to achieve font, color, graphic, and hyperlink effects on World Wide Web
    pages.
  </dd>
  <dt>Semantic</dt>
  <dd>
    Relating to meaning in language or logic.
  </dd>
  <dt>CSS</dt>
  <dd>
    A style sheet language used for describing the presentation of a
    document written in a markup language.
  </dd>
</dl>
```

---

7. The following code is an attempt to create a vertical navigation list on a web page:

```html
<nav>
  <ul>
    <li>Home</li>
    <li>Projects</li>
    <li>Team</li>
    <li>Help</li>
  </ul>
</nav>
```

```css
html {
  font-size: 20px;
}

nav ul {
  background-color: yellow;
  width: 200px;
}

nav li {
  color: blue;
}

nav a {
  box-sizing: border-box;
  line-height: 2.5;
  padding: 0 10px;
  text-decoration: none;
  width: 100%;
}
```

Modify the code to remove the bullets. Each item should be 10px from the left edge of the yellow box. When you point to any line in the menu, the browser should highlight the entire line inside the yellow box. The final result should look like this:

[image not shown]

###### Solution:

```html
<nav>
  <ul>
    <li><a href="">Home</a></li>
    <li><a href="">Projects</a></li>
    <li><a href="">Team</a></li>
    <li><a href="">Help</a></li>
  </ul>
</nav>
```

```css
html {
  font-size: 20px;
}

nav ul {
  background-color: yellow;
  list-style-type: none;
  padding-left: 0;
  width: 200px;
}

nav li {
  color: blue;
}

nav a {
  box-sizing: border-box;
  display: inline-block;
  line-height: 2.5;
  padding: 0 10px;
  text-decoration: none;
  width: 100%;
}

nav a:hover,
nav a:focus {
  background-color: green;
  color: yellow;
}
```

---

8. Convert the solution from the last problem to a horizontal navigation bar that takes up the full width of the page. Again, try not to peek at the previous assignment.

###### Solution

```css
nav ul {
  font-size: 0;
  width: 100%;
}

nav li {
  display: inline-block;
  font-size: 1rem;
  text-align: center;
  width: 25%;
}
```