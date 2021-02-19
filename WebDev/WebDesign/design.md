 ### Naming conventions
- It's better to separate words with dashes, rather than underscores: my-file.html vs. my_file.html. (hyphen vs dash)
- images styles scripts folders
- relative paths  ../subdirectory/another-subdirectory/my-image.jpg

### stuff to remember
<title> is used for browser tab title but also for favorites.
use Headings for actual titles of the page and sections

if you use one type of quote, you can include the other type of quote inside your attribute values

"Isn't this fun?"
or
'Isn&apos;t this fun?'

### CSS
Block and inline boxes


If a box is defined as a block, it will behave in the following ways:

The box will break onto a new line.
The box will extend in the inline direction to fill the space available in its container. In most cases this means that the box will become as wide as its container, filling up 100% of the space available.
The width and height properties are respected.
Padding, margin and border will cause other elements to be pushed away from the box
<h1> <p>  use block box

If a box has an outer display type of inline, then:

The box will not break onto a new line.
The width and height properties will not apply.
Vertical padding, margins, and borders will apply but will not cause other inline boxes to move away from the box.
Horizontal padding, margins, and borders will apply and will cause other inline boxes to move away from the box.

<a> <span>, <em> and <strong> use inline box display type

inner display type :
display: flex;

change for any **direct** children!


If you want all of your elements to use the alternative box model, and this is a common choice among developers, set the box-sizing property on the <html> element, then set all other elements to inherit that value, as seen in the snippet below. If you want to understand the thinking behind this, see the CSS Tricks article on box-sizing.

html {
  box-sizing: border-box;
}
*, *::before, *::after {
  box-sizing: inherit;
}

If async is present: The script is executed asynchronously with the rest of the page else defer

## margin collapsing

If you have two elements whose margins touch, and both margins are positive, those margins will combine to become one margin, which is the size of the largest individual margin. If one or both margins are negative, the amount of negative value will subtract from the total.


in inline Horizontal padding, margins, and borders are respected,
width and height are ignored

##  display: inline-block

The width and height properties are respected.
padding, margin, and border will cause other elements to be pushed away from the box.
It does not, however, break onto a new line,

per fare padding ad un link o span


em	Font size of the parent, in the case of typographical properties like font-size, and font size of the element itself, in the case of other properties like width. As such, a font-size: 16px straight-up means that 1em corresponds to 16px

ex	x-height of the element's font. Unlike ems, which don’t change when you change the font-family, ex units do change when you change the font-family, as the value of one unit is specifically bound to that font.
ch is based on the width of the zero (0) character instead of the height of the x character. It also changes as the font-family changes.

rem
A relative unit, like em, but it is always relative to the “root” element (i.e. :root {}) rather than using the cascade, like em does. This vastly simplifies working with relative units. doesn’t work in IE 8, Safari 4, or iOS 3.2.


viewport not supported in mobiles
1vw is equal to 1% of the width of the viewport. / vh


percentage is based on the length of the same property of the parent element. For example, if an element renders at 450px width, a child element with a width set to 50% will render at 225px Assuming the child element isn’t inline-level or a table cell with some weird table-y stuff going on, or a flex child or grid cell or any other fancy wacky stuff.



principles
With anything added to a page, you need to be able to answer the question of “What value does this provide?” and in turn be able to determine if the value outweighs the pain.
