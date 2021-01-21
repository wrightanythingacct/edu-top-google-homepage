# Google clone for the Odin project

First exercise of the Foundations course from the Odin Project.

## Cool things I learned

- You can get the favicon.ico of Google and many websites if you search it at the root of the domain.
e.g. [www.google.com/favicon.ico](https://www.google.com/favicon.ico)
There are also other [alternatives for extracting .ico.](https://stackoverflow.com/questions/5119041/how-can-i-get-a-web-sites-favicon)
- Made a good setup of extensions in VsCode, some of the most helpful for me in this project: [Error Lens](https://marketplace.visualstudio.com/items?itemName=usernamehw.errorlens), [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) and [className Completion in CSS](https://marketplace.visualstudio.com/items?itemName=zitup.classnametocss).
- The Odin Project recommends [Flexbox Froggy](https://flexboxfroggy.com/) and [Grid Garden](https://cssgridgarden.com/), and they're so worth it, I definitely recommend them too.
- The standard for [conventional commits](https://www.conventionalcommits.org/en/v1.0.0/) this project uses this type of commits.
- [You cannot do css selector grouping for two child selectors with the same parent.](https://stackoverflow.com/questions/6192596/how-to-select-multiple-elements-that-are-children-of-given-element) A shame, I really thought it was possible.
- IDs should be used mostly when describing a large section of the page, usually combined with section or div element. For all other cases it's better to use classes as it makes selectors easier, also to prevent having multiple IDs which is forbidden and we should only use one ID.
[StackOverFlow Reference 1](https://stackoverflow.com/questions/43074167/why-id-has-stronger-meaning-than-class-in-css-styling-even-if-declared-before-th)
[StackOverFlow Reference 2](https://stackoverflow.com/questions/8084555/why-selecting-by-id-is-not-recommended-in-css)

## Notes from Responsive design

[https://dev.to/jharteaga/px-em-rem-viewport-how-to-know-which-one-to-use-in-css-for-responsive-design-4jbi]

- No use of inches, points, cms and mms unless is printing physical
- Px = thin lines on borders for example, or the exact size of an image so it doesn't get scaled(although for that is better physical units for printing) since they aren't responsive and consistent and sometimes interfere with Zoom functionality.
  - But they're a must on media queries.
- Viewport should be used sparingly for things like overlays that need to scale based on size of the display, large containers are ideal, never use as font sizes, and they're tricky to get right.
- Percentages for elements which logically scale for their parents, for example how big sidebars are in text, or helping set some default number of elements per row/column in a flexbox layout.
- Ems mostly for tweaking the font-size of small sections of text, since it scales a property off the font of the size of the element, or the parent, it has inheritance.
  - But there's an advantage to em that
  em's are great because you set paddings, margins, borders, whatever to em, and then they all scale uniformly just by changing the font size of the item. This is great for buttons or headings where you don't want to redefine all the values every time you change a font size.
- REms for everything else, paddings, font-sizes.

### SVG Study

- The value of the viewBox attribute for SVG elements, is a list of four numbers: min-x, min-y, width and height.
- SVG defines the graphics in XML format
- Example of SVG and explanation by [https://www.w3schools.com/graphics/svg_inhtml.asp]
  - The ```<circle>``` element is used to draw a circle
  - The cx and cy attributes define the x and y coordinates of the center of the circle. If cx and cy are not set, the circle's center is set to (0, 0)
  - The r attribute defines the radius of the circle
  - The stroke and stroke-width attributes control how the outline of a shape appears. We set the outline of the circle to a 4px green "border"
  - The fill attribute refers to the color inside the circle. We set the fill color to yellow

```html
<svg width="100" height="100">
  <circle cx="50" cy="50" r="40" stroke="green" stroke-width="4" fill="yellow" />
</svg>
```

- Predefined SVG shapes
  - Rectangle ```<rect>```
  - Circle ```<circle>```
  - Ellipse ```<ellipse>```
  - Line ```<line>```
  - Polyline ```<polyline>```
  - Polygon ```<polygon>```
  - Path ```<path>```

- The following commands are available for path data:
  - M = moveto
  - L = lineto
  - H = horizontal lineto
  - V = vertical lineto
  - C = curveto
  - S = smooth curveto
  - Q = quadratic Bézier curve
  - T = smooth quadratic Bézier curveto
  - A = elliptical Arc
  - Z = closepath

#### Info from [https://css-tricks.com/scale-svg/](CSS Tricks)

- In HTML SVG is treated like a document, just like:

```html
<object>
  <img>
  <iframe>
```

the default size for this elements is 300x15, but can vary between different browsers.

- The ways you will need scale a SVG is:
  - Scaling to fit a certain size, without distorting the image
  - Scaling to fit a certain size, stretching or compressing the graphic as necessary
  - Scaling to fit the available width, while maintaining the width-to-height aspect ratio
  - Scaling in non-uniform ways, so that some parts of the graphic scale differently from others

- You should use a combination of height and width with viewBox attr
  - it defines the aspect ratio of the image
  - it defines how all the values on the SVG should be scaled to fit the total space available
  - it defines the origin of the SVG coordinate
  
- Is normal that viewBox makes the SVG bigger if the width is smaller [https://stackoverflow.com/questions/40588228/why-when-making-the-viewbox-smaller-does-my-svg-get-bigger]
