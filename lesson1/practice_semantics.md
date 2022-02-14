# Practice Problems: Semantics

1. Which of these tags are semantic, and which are not?

    Semantic tags include: `<article>`, `<aside>`, `<footer>`, `<b>`, `<footer>`, `<h3>`, `<header>`, `<section>`, `<strong>`
    Tags without semantic meaning include: `<span>`, `<div>`
    Note that in HTML5 _all_ content tags have semantic meaning except `<div>` and `<span>`, even tags like `<b>` and `<i>`, which did not previously have semantic meaning in HTML4.

2. What tag would be most semantically appropriate to wrap the following HTML?

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

    In this case we would want to use the `<article>` tag, because this can be independently represented anywhere and still make sense (i.e. the content is self-contained and reusable).

    Note that semantics also depend on context and intent, so we could also treat it as a `<section>` and `<aside>`

3. Given the HTML from question 2, would it be appropriate to replace `<sometag>` with `<address>` or `<blockquote>`? If so, which one?

    `<address>` - semantically indicates that the enclosed content provides contact information, and would not be appropriate
    `<blockquote>` - semantically indicates that the enclosed text is an extended quotation, which would be appropriate in this case.

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

    `<section>` would be the most appropriate tag here, as the content represents a section on the page, in which we have a heading. It does not work independently, and appears to be part of the main document flow, so `<aside>` would not be appropriate.

5. Given the following HTML, would `<aside>`, `<section>`, `<blockquote>`, or `<div>` be the most appropriate element for the tag shown as `<sometag>`?

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

    In this case we would use `<aside>`, since this represents some kind of tangential information to the main content.
