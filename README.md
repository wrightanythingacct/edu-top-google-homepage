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
- The value of the viewBox attribute for SVG elements, is a list of four numbers: min-x, min-y, width and height.