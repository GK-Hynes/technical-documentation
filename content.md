# Introduction

As far as HTML and CSS are concerned, every element on a webpage is a box. You can see this by opening the developer tools, going to the inspector tab, then the styles tab, and adding `border: 1px solid red;` to `*` (the CSS selector that means all elements).

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

When elements are stacked vetically on a page and their vertical margins touch, margin collapsing can occur. Here the margin between the two elements is not the total of the two margins but simply whatever the bigger margin is. So, an element with `margin-bottom: 20px;` and the next element with `margin-top: 15px;` will have a margin between them of 20px, not 35px.

Margin collapsing does not happen to horizontal margins.

If the two margins are equal, the total margin will simply be the margin of one of the elements.

If one margin is negative, it is subtracted from the positive margin to leave the total margin.

If both margins are negative, the total will be the most negative margin.

In the same way, margin collapsing happens when the vertical margin of a child element meets the vertical margin of its parent element. The child element's margin will be overridden by its parent's margin. This can be prevented by seperating the margins of the parent and child elements by adding padding or border to the parent element.

### Overflow

### Outline

### Box-sizing

The `box-sizing` property tells the browser how it should calculate the total width and height of an element. By default, `box-sizing` is set to `content-box`. That means that the width and height you assign to an element are only applied to the content and then padding and border are added on top. An element with a `width` of 500px, `padding` of 25px and `border` of 5px, will have an actual total width of 560px.

By setting `box-sizing` to `border-box`, the browser will factor padding and border into the values you specify for `width` and `height`, and so removes the need for extra calculations. The content box will shrink so that total width and height matches the `width` and `height` values. This makes sizing easier and so `box-sizing: border-box;` is often included in CSS resets.

![Screenhsot of two divs demonstrating the box-sizing property](https://res.cloudinary.com/gerhynes/image/upload/q_auto/v1546372213/box-sizing_ufd0ly.png)

## CSS Positioning

HTML without CSS will display each element one after another down the page in the order they appear in the HTML file. This is the normal layout flow of the document.

The CSS `position` property lets you take elements out of the normal flow and position them where you want them to be, for example overlapping each other, or stuck to the browser viewport.

`position` can take a number of values:

- static
- relative
- absolute
- fixed
- sticky

### Static Positioning

The default value for the `position` property is `static`. A statically positioned element will appear in its normal position in the document layout flow and scrolls when you scroll the page.

### Relative Positioning

Relative positioning places an element "relative" to its normal posiiton in the layout flow. By itself, `position: relative` won't make an change to where an element appears on the page. It still occupies its normal place in the layout, just as if it was positioned statically.

![Screenshot of two divs positioned relative and fixed](https://res.cloudinary.com/gerhynes/image/upload/q_auto/v1546462467/relative-no-offsets_laxqai.png)

However, once an element is positioned relative, you can use the `top`, `right`, `bottom` and `left` properties (the offset properties) to move it around. The offset properties push an element away from its normal position.

The following code will move an element down 50px and right 50px.

```css
div {
  position: relative;
  top: 50px;
  left: 50px;
}
```

![Screenshot of two divs demonstrating posiiton relative](https://res.cloudinary.com/gerhynes/image/upload/q_auto/v1546462658/position-relative_fsmuhp.png);

Other elements will not move away from the new position of the relatively positioned element (as far as they are concerned, it is still in its normal position). Relatively positoned elements will appear on top of statically positioned elements. See `z-index`.

### Absolute Positioning

Absolute positioning removes an element from its normal position in the layout flow altogether and places it on its own layer. As far as the other elements are concerned, it no longer exists, and so elements coming after it in the HTML document will move up to occupy its now "empty" position.

An absolutely positioned element doesn't affect the position of other elements and isn't affected by them. This can be useful when creating isolated UI elements such as popups and modals.

![Screenshot of two divs demonstrating absolute positioning](https://res.cloudinary.com/gerhynes/image/upload/q_auto/v1546463237/position-absolute_gxui2t.png)

Like with relatively positioned elements, absolutely positioned elements can be moved around using the `top`, `right`, `bottom` and `left` offset prpoerties.

But there is an important difference.

With relatively positioned elements, the offsets tell it how far to move in a particular direction away from to its normal position.

With absolutely positioned elements, the offsets tell it how far it should be from each side of the element that contains it.

#### Absolute Positioning and Positioning Context

The "containing element" of an absolutely positioned element is determined by the position properties of its parent elements.

If all of the ancestor elements of the abolsutely positioned element are statically positioned (for example, if their position properties aren't explicitly defined), then its "containing element" is the `<html>` element, which in practice means the viewport.

If you don't want the absolutely positoned element to be positioned according to the viewport, you need to give one of its ancestor elements a position other than static, usually by setting one of its ancestor elements to `position: relative`, for example the `<body>` element. You can then move the absolutely positioned element away from its "containing element" using the `top`, `right`, `bottom` and `left` offsets.

In the first screenshot below the container is positioned statically and so the absolutely positioned div's offsets position it in relation to the viewport.

In the second screenshot, the container is positioned relatively and so the absolutely positioned div's offsets position it in relation to the container.

![Screenshot of an absolutely positioned div inside a statically positioned container](https://res.cloudinary.com/gerhynes/image/upload/q_auto/v1546548991/absolute-element-with-static-container_eqli2d.png)

![Screenshot of absolutely positoned div inside a relatively positioned container](https://res.cloudinary.com/gerhynes/image/upload/q_auto/v1546549063/absolute-element-with-relative-container_cl43ks.png)

### Fixed Positoning

Fixed positioning works in a similar way to absolute positioning. While absolute positioning places an element in relation to either the `<html>` element or an ancestor element that isn't statically positioned, fixed positioning places an element in relation to the viewport.

When the page is scrolled, the fixed element stays in place on the viewport and other elements scroll past it. This is useful for putting UI items in a fixed place, such as the navbar at the top of the viewport.

Like with absolute positioning, fixed positioning takes the element out of the normal layout flow and other elements will move up to fill its "empty" position.

Elements that are positioned fixed can also be moved around using the `top`, `right`, `bottom` and `left` offsets. You might position a navbar at the top of the viewport using:

```css
.navbar {
  position: fixed;
  top: 0;
}
```

![Screenshot of divs and navbar demonstrating position fixed](https://res.cloudinary.com/gerhynes/image/upload/q_auto/v1546551342/position-fixed_elsjfx.png)

### Sticky Positioning

## Z-index

Moving an element away from its "normal" positioning can cause elements to overlap. By default, positioned elements (those given a `position` value such as `relative` or `absolute`) appear on top of static elements.

The property which allows you to decide which element appears on top is the `z-index`.

While offsets move elements around on the x-axis and y-axis, `z-index` moves elements on the z-axis, that is, closer to the screen or further away from it.

By default, all positioned elements have a `z-index` of `auto`, which is the same as setting the `z-index`to 0. Statically positioned elements cannot take a `z-index` value.

Higher `z-index` values make elements appear closer to the screen and lower `z-index` values make them appear further back. You can set `z-index` to negative values to put an element behind another element.

![Screenshot of two divs demonstrating z-index](https://res.cloudinary.com/gerhynes/image/upload/q_auto/v1546549449/z-index_nva7qn.png)

## Further Resources

```

```
