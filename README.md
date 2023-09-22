# <img src="images/css3-30.png" alt="CSS"> CSS

CSS is a programming language used for styling web content, providing control
over the presentation and layout of HTML documents. It has been gaining adoption
for styling in other UI frameworks.<br>

<br>

> All CSS files used in Flask and Django frameworks are included in their
> template folders:
>
> - <a href="https://github.com/ilya0x/python-templates/tree/main/flask"><img
>   src="./images/flask-full-30.png" alt="Flask"></a>
> - <a href="https://github.com/ilya0x/python-templates/tree/main/django"><img
>   src="./images/django-full-30.png" alt="Django"></a>

<br>

## <img src="./images/template-20.png" alt="template"> Templates

<b>[Generic Dark Mode](generic/dark-mode.css)</b>

<b>[Generic Light Mode](generic/light-mode.css)</b>

<b>[Photo Gallery FLEXBOX](photo-gallery-flexbox/)</b> - includes HTML and
placeholder images (which are all my photographs).

<b>[Grid and Flex Fun Animation Demo](grid-and-flex-demo/)</b> - includes HTML
and images.

> Animation without JavaScript 🤓

<br>

## <img src="./images/vscode-20.png" alt="Flask"> Visual Studio Code Extensions

<b>[CSS Snippets](https://marketplace.visualstudio.com/items?itemName=joy-yu.css-snippets)
</b> - Shorthand snippets for css.<br>

<b>[HTML CSS Support](https://marketplace.visualstudio.com/items?itemName=ecmel.vscode-html-css)
</b> - CSS Intellisense for HTML.<br>

<br>

## 📝Notes

> These notes are updated on regular basis

<br>

### Table of Contents

- <b>[Layout Styles](#layout-styles)</b>
  - <b>[Block Layout](#block-layout)</b>
  - <b>[Inline Layout](#inline-layout)</b>
  - <b>[Positioned Layout](#positioned-layout)</b>
  - <b>[Table Layout](#table-layout)</b>
  - <b>[FLEXBOX Layout](#flexbox-layout)</b>
  - <b>[Grid Layout](#grid-layout)</b>
- <b>[Animation](#animation)</b>

<br>

[Top of Page](https://github.com/ilya0x/css-templates)

<br>

---

<br>

### Layout Styles

#### Block Layout

- For laying out documents
  - Stacking `<div>` blocks
- Vertically based

Example:

``` css
/* Define styles for the individual blocks */
.block {
    background-color: #3498db;
    color: #fff;
    padding: 20px;
    margin-bottom: 20px;
}

/* Add some spacing between blocks */
.block + .block {
    margin-top: 20px;
}
```

Then use `<div class="block">`

<br>

[Back to Table of Contents](#table-of-contents)

<br>

#### Inline Layout

- For laying out text
- Horizontally based
  - Displays list items horizontally

Example:

``` css
.nav {
  background-color: yellow;
  list-style-type: none;
  text-align: center; 
  padding: 0;
  margin: 0;
}

.nav li {
  display: inline-block;
  font-size: 20px;
  padding: 20px;
}
```

<br>

[Back to Table of Contents](#table-of-contents)

<br>

#### Positioned Layout

- For explicit positioning
- `fixed` vs `relative` vs `absolute` vs `sticky`

Example:

``` css
div.fixed {
  position: fixed;
  bottom: 0;
  right: 0;
  width: 300px;
  border: 3px solid #73AD21;
}
```

``` css
div.relative {
  position: relative;
  left: 30px;
  border: 3px solid #73AD21;
}
```

``` css
div.absolute {
  position: absolute;
  top: 80px;
  right: 0;
  width: 200px;
  height: 100px;
  border: 3px solid #73AD21;
}
```

> Internet Explorer does not support sticky positioning. Safari requires a
> `-webkit-` prefix (see example below). You must also specify at least one of
> `top`, `right`, `bottom` or `left` for sticky positioning to work.

``` css
div.sticky {
  position: -webkit-sticky; /* Safari */
  position: sticky;
  top: 0;
  background-color: green;
  border: 2px solid #4CAF50;
}
```

<br>

[Back to Table of Contents](#table-of-contents)

<br>

#### Table Layout

- For laying out 2D tabular data

Example:

``` css
/* Keyword values */
table-layout: auto;
/* Browsers use an automatic table layout algorithm. The column width is set by the
widest unbreakable content in the cells. The content will dictate the layout */
table-layout: fixed;
/* Sets a fixed table layout algorithm. The table and column widths are set by 
the widths of table and col or by the width of the first row of cells. Cells in 
other rows do not affect column widths. If no widths are present on the first 
row, the column widths are divided equally across the table, regardless of 
content inside the cells */
/* Global values */
table-layout: inherit;
/* Sets this property to its default value. */
table-layout: initial;
/* Inherits this property from its parent element. */
```

<br>

[Back to Table of Contents](#table-of-contents)

<br>

#### FLEXBOX Layout

- One dimensional layout along main axis: `flex` row or column
- Directionally agnostic

Example:

``` html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Flexbox Example</title>
    <style>
        .flexbox-container {
            display: flex;
            flex-direction: column; /* Changes the direction of the main axis.
            Default is `row', which is horizontal. */
            flex-wrap: wrap; /* Wraps items if they do not fit on same line */

            /* Can use `flex-flow` property to combine `flex-direction` and `flex-wrap`:
            `flex-flow: column wrap;` */

            /* Use `justify-content` property to align and space-out the items 
            along the main axis */
            /* Use `align-items` property to align the items along the cross 
            axis to each other */
            /* Use `align-content` property to align the items as a group inside
            the container */
        }

        .flexbox-item {
            flex-basis: 15%; /* Starting point of the item's width */
            display: flex; /* Make items into flexboxes themselves */

            /* Use `justify-content` and 'align-items` here to control layout 
            of elements inside items when the items are flexboxes themselves */
        }

        .item-1 {
            min-height: 600px;

            /* Use `flex-grow` property to control the distribution of the 
            free space between the items. Providing a number makes it 
            distributed at that ratio. Grow acts when items do not fill the
            container. */
            /* Use `flex-shrink` property to provide a number to use as ratio 
            at which the items shrink when they fill the container. */

            /* Use `fex` property to set the above ones in one place:
            `flex: a b c;`
            where:
            a is `flex-grow` ratio number,
            b is `flex-shrink` ratio number,
            c is `flex-basis` percentage */
            
            /* Use `align-self` property on each item to individually align 
            them along the main axis */

            /* Use `order` to assign specific order to the items. This number 
            will override their actual place in HTML code */
            order: 2;
        }

        .item-2 {
            min-height: 100px;

            order: 1;
        }

        .item-3 {
            min-height: 250px;

            order: 3;
        }
    </style>
</head>
<body>
    <div class="flexbox-container">
        <div class="flexbox-item item-1">Main Content</div>
        <div class="flexbox-item item-2">Left Aside</div>
        <div class="flexbox-item item-3">Right Aside</div>
    </div>
</body>
</html>
```

> A great YouTube video about FLEXBOX: [Learn CSS FLEXBOX in 20 Minutes](https://youtu.be/qqDH0T6K5gY?si=o3zWeCvcnTXlgQfB)<br>
> The example above is from this video.

<br>

[Back to Table of Contents](#table-of-contents)

<br>

#### Grid Layout

- Two dimensional layout with grid `cells` along grid `lines`
  - a row of the grid `cells` is called a `track`
  - an `area` consists of multiple grid cells (a square or rectangle)
- Directionally agnostic

> Use <b>Grid Template Areas,</b> individually naming all of your grid areas / items.

Example:

``` html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Grid Example</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-size: 30px;
        }

        .grid-container {
            height: 100vh;
            border: 10px solid #14a76c;
            display: grid;
            grid-template-rows: 200px 200px; /* The first two rows are 
            explicitly defined at 200 pixels. The other rows will fit the rest 
            of the space */

            /* Use `grid-auto-rows` to set the height of all subsequent rows 
            after the template ones */

            grid-template-columns: repeat(3, 1fr); /* Defining columns */
            /* `repeat` takes 2 values: how many times, the size */
            /* using fractional units `fr`, the space gets divided accordingly:
            grid-template-columns: 1fr 2fr 1fr; */
            /* the settings can be mixed:
            grid-template-columns: 1fr 100px auto; */

            /* Use `grid-auto-columns` to set the width of all subsequent
            columns after the template ones */

            grid-gap: 20px;
            /* Use `grid-row-gap` and `grid-column-gap` to specify the gaps 
            individually for rows and columns */

            /* Use `justify-items` to horizontally align the items within the
            grid cells (by default it's stretched) */
            /* Use `align-items` to vertically align the items within the grid
            cells (by default it's stretched) */

            /* Use `justify-content` to horizontally align all the cells within
            the container */
            /* Use `align-content` to vertically align all the cells within
            the container */

            /* IF USING Grid Template Area:
            Use `grid-template-areas` to lay out the items (with 3 columns):
            grid-template-areas:
                "header header header"
                "nav main ads"
                "footer footer footer"
            Use `grid-template-rows` to specify row hights:
            grid-template-rows: 60px 1fr 60px;
            Use `grid-template-columns` to specify column widths:
            grid-template-rows: 20% 1fr 15%;
            OR
            Combine it into `grid-template`:
            grid-template:
                "header header header" 60px
                "nav main ads" 1fr
                "footer footer footer" 60px
                / 20% 1fr 15%; */
        }

        .grid-item {
            background-color: #ccc;
            border: 4px solid #ff652f;
            padding: 20px;
        }

        .item-1 {
            grid-area: header; /* Grid Template Area name */

            grid-column: 1 / 3; /* from line 1 to line 3 */

            /* Use `grid-column-start` and `grid-column-end` to specify the 
            start line and end line of column span */
            /* Use `grid-row-start` and `grid-row-end` to specify the start
            line and end line of row span */

            /* Use `justify-self` and `align-self` to align the item 
            vertically and horizontally */
            /* Use `place-self` to combine `justify-self` and `align-self`:
            place-self: bottom right; */
        }
        .item-2 {
            grid-area: nav; /* Grid Template Area name */

            z-index: 1; /* Brings item-2 to top, to be layer 1 */
        }
        .item-3 {
            grid-area: main; /* Grid Template Area name */
        }
        .item-4 {
            grid-area: ads; /* Grid Template Area name */
        }
        .item-5 {
            grid-area: footer; /* Grid Template Area name */
        }
        .item-6 {
            grid-area: 1 / 3 / 3 / 4;
        }
        .item-7 {
            grid-area: 2 / 1 / span 3 / span 2;
        }
    </style>
</head>
<body>
    <div class="grid-container">
    <div class="grid-item item-1">
      item 1
    </div>
    <div class="grid-item item-2">
      item 2
    </div>
    <div class="grid-item item-3">
      item 3
    </div>
    <div class="grid-item item-4">
      item 4
    </div>
    <div class="grid-item item-5">
      item 5
    </div>
  </div>
</body>
</html>
```

<br>

[Back to Table of Contents](#table-of-contents)

<br>

### Animation

<br>

[Back to Table of Contents](#table-of-contents)

<br>
