# <img src="images/css3-30.png" alt="CSS"> CSS

- a pair of basic light and dark mode templates with inline notes.

> All CSS files used in Flask and Django frameworks are included in their
> template folders:
>
> - <a href="https://github.com/ilya0x/python-templates/tree/main/flask"><img
>   src="./images/flask-full-30.png" alt="Flask"></a>
> - <a href="https://github.com/ilya0x/python-templates/tree/main/django"><img
>   src="./images/django-full-30.png" alt="Django"></a>

<br>

## <img src="./images/template-20.png" alt="template"> Templates

<br>

## <img src="./images/vscode-20.png" alt="Flask"> Visual Studio Code Extensions

<br>

## 📝Notes

> These notes are updated on regular basis

<!--
TODO: Table of Contents
-->

<br>

### Layout Styles

#### Block layout

- For laying out documents
- Vertically based

Example:

<br>

#### Inline layout

- For laying out text
- Horizontally based

Example:

<br>

#### Positioned layout

- For explicit positioning

Example:

<br>

#### Table layout

- For laying out 2D tabular data

Example:

<br>

#### FLEXBOX

- A more efficient way to layout, align and distribute space among items in a container
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

#### Grid

-

Example:

``` html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Grid Example</title>
    <style>
    
    </style>
</head>
<body>
    
</body>
</html>
```

<br>
