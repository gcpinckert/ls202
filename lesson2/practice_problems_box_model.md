# Practice Problems: The Box Model

1. `img` dimensions include:
  
    - height of 300px
      \+ top & bottom padding of 10px | subtotal = 320px
      \+ top & bottom border of 4px | subtotal = 328px
      \+ top margin 20px | subtotal = 348px
      \+ bottom margin 10px | subtotal = 358px
      \+ top & bottom border of 1px for `div` | **total** = 360px
    - width of 500px
      \+ right & left padding of 20px | subtotal = 540px
      \+ right & left border of 4px | subtotal = 548px
      \+ right margin of 19px | subtotal = 567px
      \+ left margin of 11px | subtotal = 578px
      \+ right & left border of 1px for `div` | **total** = 580px

In order to entirely contain the `img` element (including margins), the `div` needs to have a height of at least 360px and a width of at least 580px.

2.  The `div` must have a least the same dimensions listed in question 1 (360px x 580px), because the `section` element it contains bears the same dimensions as the `img` element in question 1. While the `img` element may have other elements appear on the same line with it (because it has a `display` property on `inline-block`), the `section` element will always stand alone on the same line, due to the fact it's `display` property is set to `block`.

3. The `em` element is inline, so when rendering it the browser will ignore any size specified in CSS as well as any top or bottom margins. Let us assume a height of 20px and a width of 50px is needed for the `content` of `em`:

    - height of 20px:
      \+ top & bottom padding of 10px | subtotal = 40px
      \+ top & bottom border of 4px | subtotal = 48px
      \+ top & bottom border of 1px for `div` | **total = 50px**
    - width of 50px:
      \+ left & right padding of 20px | subtotal = 90px
      \+ left & right border of 4px | subtotal = 98px
      \+ right margin of 19px | subtotal = 117px
      \+ left margin of 11px | subtotal = 128px
      \+ left & right border of 1px for `div` | **total = 130px**

    Note that the top and bottom padding and borders may intersect with other content, as with `inline` elements, top and bottom flow is not adjusted.

4. The `div` element only needs to take into account the margins of `article` and it's own border. Because both elements are set to `border-box`, the padding and border for `article` will be represented within the dimensions specified for `width` and `height`, and the border specified for `div` will also be represented inside it's box.

    - height of 300px:
      \+ top margin of 20px | subtotal = 320px
      \+ bottom margin of 10px | subtotal  = 330px
      \+ top and bottom border of 1px for `div` | **total = 332px**
    - width of 500px:
      \+ right margin of 19px | subtotal = 519px
      \+ left margin of 11px | subtotal = 530px
      \+ right and left border of 1px for `div` | **total = 532px**

5.
    - if `tag1` and `tag2` are both inline elements, they will display side by side in the `div`.
    - If both elements are `inline-block` elements they will display side by side in the `div`.
    - If one element is an `inline` element and one is an `inline-block` element, they will display side by side in the `div`.

6. The two article elements will not display side by side. This is because, by default, `article` is block element, which always takes up an entire "line" when being rendered. We can cause them to display side by side if we switch the `display` property to `inline-block`. Furthermore, because the `box-sizing` property for `article` has not been set, we are relying on the browser default which is `content-box`. Because of this, the true width of each article is actually 50% of the `section` width + 22px to account for the `border` and `padding` values. We can change this by setting the `box-sizing` property to `border-box` which will cause the border and padding to be rendered inside the 50% width specified in the CSS.

7. If we put the `article` tags on separate lines in the HTML, they will no longer be displayed side by side in the `section`. This is because by entering a new-line between both articles, we are actually creating some additional content that must be rendered: a space character. Because the articles require exactly 50% of the width of the `section` to be shown on the same line, the space character causes one to be bumped down (because it takes up some amount of pixels). The total width is now 50% + some pixels + 50% which will add up to more than 100% of the width of the section.

This usually occurs when we are dealing with `inline-block` elements, otherwise the extra space doesn't really have an effect. One technique for dealing with it is to have the two tags next to each other, as in the previous example with Q6. 


