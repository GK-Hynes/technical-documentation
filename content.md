# Introduction

As far as CSS is concerned, every element on a webpage is a box. You can see this by opening the developer tools, going to the inspector tab, then the styles tab, and adding `border: 1px solid red;` to `*` (the CSS selector that means all elements).

![Screenshot of freeCodeCamp Basic CSS page with elements outlined in red](https://res.cloudinary.com/gerhynes/image/upload/q_auto/v1546287889/Screenshot_2018-12-31_Basic_CSS_freeCodeCamp_imqecp.png)

The size of each element, and the basic ways it is positioned in relation to other elements, are determined by the CSS box model.

## The Box Model

The box model defines the basic structure of an element on a webpage. Every box has certain essential properties: width and height, padding, border, and margin.

![Red square with box model dexcription in developer tools](https://res.cloudinary.com/gerhynes/image/upload/q_auto/v1546287207/box-model_zhzloh.png)

### Width and Height

At the centre of each box is the content box, where the contents of the box are displayed, for example, any text it contains. The element's `width` and `height` properties set the width and height of the content box. By default, width is 100% of the available space.

![HTML element with width and height 250px](https://res.cloudinary.com/gerhynes/image/upload/q_auto/c_scale,w_450/v1546289550/html_element_whgdjm.png)

### Padding

Next comes padding. This is the space on the inside of the element between the content and the element's border. The padding on all four sides of the box can be set at once using the `padding` property or it can be set on each side individually using `padding-top`, `padding-right`, `padding-bottom`, `padding-left`.

If you give an element padding, its total width and height will be `width` and `height` plus whatever padding you set. So an element with a `width` of 250px and `padding` of 10px will have a total width of 270px (`padding-left` + `width` + `padding-right`).

If you give an element a background colour, that colour will extend to the edge of the padding, since the padding is on the "inside" of the element.

![HTML element with padding](https://res.cloudinary.com/gerhynes/image/upload/q_auto/c_scale,w_450/v1546289556/element_with_padding_vx9gky.png)

### Border

An element's border comes between its padding and its margin. By default the border is set to 0, making it invisible. The `border` property is a shorthand way to set the border's thickness, style and colour, for example `border: 5px solid green;`. These properties can also be set individually using `border-width`, `border-style`, `border-color`.

Like with `padding`, the `border` property is shorthand for `border-top`, `border-right`, `border-bottom`, `border-left`, which can each be set individually.

![HTML element with padding and border](https://res.cloudinary.com/gerhynes/image/upload/q_auto/c_scale,w_450/v1546289564/element_with_border_aur4cf.png)

### Margin

The margin is the space that surrounds an elements and pushes other elements away. It exists outside the element's border.

If you give an element a background colour, that colour will not extend to the margin, as the margin is on the "outside" of the element.

Like with `padding` and `border`, the `margin` property is shorthand for `margin-top`, `margin-right`, `margin-bottom`, and `margin-left`.

The `margin` property can accept negative values, causing elements to overlap.

![HTML element with padding, border, and margin](https://res.cloudinary.com/gerhynes/image/upload/q_auto/c_scale,w_450/v1546363200/element_with_margin_ctrv4w.png)

#### Sidenote: Margin Collapsing

When elements are stacked vetically on a page and their vertical margins touch, margin collapsing can occur. Here the margin between the two elements is not the total of the two margins but simply whatever the bigger margin is. So, an element with `margin-bottom: 20px;` and an element with `margin-top: 15px;` will have a margin between them of 20px, not 35px.

If the two margins are equal, the total margin will simply be the margin of one of the elements.

If one margin is negative, it is subtracted from the positive margin to leave the total margin.

If both margins are negative, the total will be the most negative margin.

### Box-sizing

## CSS Positioning

## Z-index

## Further Resources
