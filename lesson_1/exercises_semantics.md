##### LS202 HTML and CSS > Lesson 1: Your First Web Pages

---

### Practice Problems: Semantics

---

1. Which of these tags are semantic, and which are not?

   |             |            |            |             |
   | :---------: | :--------: | :--------: | ----------- |
   |             |            |            |             |
   | `<article>` | `<aside>`  |   `<b>`    | `<div>`     |
   | `<footer>`  |   `<h3>`   | `<header>` | `<section>` |
   |  `<span>`   | `<strong>` |            |             |

###### Solution

**Semantic**: `<article>`, `<aside>`, `<b>`, `<footer>`, `<h3>`, `<header>`, `<section>`, `<strong>`

**Non-Semantic**: `<div>`, `<span>`

In HTML5, all content tags except `<div>` and `<span>` have semantic meaning. In particular, both `<b>` and `<i>` have semantic meaning. Some developers may tell you otherwise, but that's a holdover from HTML4, in which both elements are non-semantic. Note, though, that the semantic meanings of `<b>` and `<i>` in HTML5 are somewhat subtle. Avoid using them solely for stylistic purposes, and be sure you understand when they are appropriate.

---

2. Given the following HTML, would `<section>`, `<aside>`, `<article>`, or `<div>` be the most appropriate element for the tag shown as `<sometag>`?

   ```html
   <sometag>
     <h1>Lincoln's Gettysburg Address</h1>
     <p>
       Four score and seven years ago our fathers brought forth on this
       continent, a new nation, conceived in Liberty, and dedicated to the
       proposition that all men are created equal.
     </p>
     <p>
       Now we are engaged in a great civil war, testing whether that nation,
       or any nation so conceived and so dedicated, can long endure. We are
       met on a great battle-field of that war. We have come to dedicate a
       portion of that field, as a final resting place for those who here gave
       their lives that that nation might live. It is altogether fitting and
       proper that we should do this.
     </p>
     <p>
       But, in a larger sense, we can not dedicate—we can not consecrate—we
       can not hallow—this ground. The brave men, living and dead, who
       struggled here, have consecrated it, far above our poor power to add or
       detract. The world will little note, nor long remember what we say
       here, but it can never forget what they did here. It is for us the
       living, rather, to be dedicated here to the unfinished work which they
       who fought here have thus far so nobly advanced. It is rather for us
       to be here dedicated to the great task remaining before us—that from
       these honored dead we take increased devotion to that cause for which
       they gave the last full measure of devotion—that we here highly
       resolve that these dead shall not have died in vain—that this nation,
       under God, shall have a new birth of freedom—and that government of
       the people, by the people, for the people, shall not perish from the
       earth.
     </p>
   </sometag>
   ```

###### Solution

  Based on what we see here, an `<article>` may be the best choice since Abraham Lincoln's Gettysburg Address would make sense if we extracted it from the page and put it elsewhere. That is, it's self-contained and reusable.

  However, semantics depend on context and intent, so whether we treat the Gettysburg address as an `<article>` or `<section>` or `<aside>` may vary from one page to another.

---

3. Given the HTML from question 2, would it be appropriate to replace `<sometag>` with `<address>` or `<blockquote>`? If so, which one?

###### Solution

  Extended quotations like this should use `<blockquote>`. This quotation is also a standalone item, though, so `<article>` is also appropriate. The best solution may be to replace sometag with blockquote, then wrap the entire `<blockquote>` in an `<article>`:

  ```html
  <article>
    <blockquote>
      <h1>Lincoln's Gettysburg Address</h1>
      <p>Four score and seven years ago ...</p>
      <p>Now we are engaged in a great civil war...</p>
      <p>But, in a larger sense, we can not dedicate...</p>
    </blockquote>
  </article>
  ```
  `<address>`, of course, is inappropriate; it identifies contact information, not speeches.

---

4. Given the following HTML, would `<section>`, `<aside>`, `<article>`, or `<div>` be the most appropriate element for the tag shown as `<sometag>`?

```html
<sometag>
  <h3>Text-align Property</h3>
  <p>
    Given the width of the paragraph, the heading looks odd hanging out on
    the left side of the screen. Let's center it instead; we'll do this
    with the text-align property:
  <p>

  <pre>
    <h1 style="color: orange; text-align: center;">Hello, Internet!</h1>
  </pre>
</sometag>
```

###### Solution

This time, a `<section>` tag may be the best choice. The text appears to be part of a larger body of work, but it isn't a standalone block like an `article`. It's also not an `aside` since it appears to be part of the main document flow.

---

5. Given the following HTML, would `<aside>`, `<section>`, `<blockquotes>`, or `<div>` be the most appropriate element for the tag shown as `<sometag>`?

```html
<h3>Hex Colors</h3>

<p>
 Most graphics and design applications like Photoshop and Pixelmator
 display colors in hexadecimal format, so it's easy to copy and paste
 color values you need from one program into your editor as a CSS
 property.
</p>

<sometag>
 <p>
   If you're unfamiliar with the hexadecimal numbering system, it uses 16
   different digits instead of the ten the decimal system uses. The hex
   digits are 0 through 9, as in the decimal system, but also include a
   through f (or A through F) as valid digits.
 </p>
</sometag>
```

###### Solution

The text in the `<sometag>` element feels like a comment added as an `aside`, rather than part of the main text, so an `<aside>` tag would be the most appropriate.
