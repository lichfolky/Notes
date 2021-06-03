fonts size depends from the distance from the screen

mobile
12-16 px

tablet
15-19px

pc
16-20px

46-75 lettere per riga

https://www.gridlover.net/try

contrast ratio at least 4.5:1
https://webaim.org/resources/contrastchecker/

Keep paragraph spacing in the range between .75x and 1.25x of the type size.

A px is 0.75 pt?

Components with greater density should have lower density margins and gutters.

To maintain consistency in your layout, use a consistent aspect ratio on elements like images, surfaces, and screen size.

https://medium.com/variable-fonts/https-medium-com-tiro-introducing-opentype-variable-fonts-12ba6cd2369
OpenType Font Variations

OpenType format
OpenType Layout

TrueType

Compact Font Format (CFF)


https://docs.microsoft.com/en-gb/typography/opentype/spec/


interpolation between design masters as part of their workflows
weights, widths or optical sizes


### After course
16 pixels is a clear standard. 


The line-height property belongs to an exclusive club of CSS properties that accept unit-less numeric values.

```p {
   font-size:; /* Silence is golden; implicity 1em. */
   line-height: 1.5;
}```

Using even numbers for font size and moltiplt for 1.5 will result in a whole number


https://www.smashingmagazine.com/2011/11/the-perfect-paragraph/

but line height 1.5 is enotught
Fonts with a tall x-height or long descenders might benefit from more generous, separative leading. 

p + p {
   text-indent: 1.5em  /* I like to keep the indentation length equal to the line height. */
}

h1 + p:first-letter {
   font-size: 2em;
   line-height: 0;  /* The line-height must be adjusted to compensate for the increased font size, otherwise the leading for the overall line is disrupted. I find that any values below 0.4 work. */
}

$base-font-size: 100; // Converts to 16px
$line-height: 1.6;
$leading: $base-font-size * $line-height;

* {
  line-height: $leading;
  margin-bottom: $leading;
}

text-indent: 0;
Defines the indentation of the element's first line of text.




https://tonsky.me/blog/font-size/

## NO font size

a Point is a physical unit of measure, equal to 1⁄72 of an inch (0.353 mm) The idea here was that you set font size directly in physical units, ignoring minute details like screen resolution. If I want to see my letters 2 inches tall, I can do that by setting the font size to 144 pt.

In practice, nobody does that. Instead, macOS always uses 72 PPI to convert points to pixels. If you put macOS on a 32” monitor and a 24” monitor, both set to 1080p resolution, you’ll get identical pixel size, but not physical size, undermining the original idea.

And they did, indeed. This holds to this day: 16 pt text on Windows is ⅓ larger than 16 pt text on macOS. Fun!

In traditional metal type, em size is the height of the character piece.

Why was the height called “em size”? Because letter “m” was coincidentally a square, and “m” width == character piece height == em size. Simple!