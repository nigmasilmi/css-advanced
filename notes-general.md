## Animation Timing function

[go](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timing-function)

## Backface Visibility

[go](https://developer.mozilla.org/en-US/docs/Web/CSS/backface-visibility)

## :link pseudo-class

[go](https://developer.mozilla.org/en-US/docs/Web/CSS/:link)

## Three pillars to write good html and css

1. Responsive design
   - Fluid layouts
   - Media queries
   - Responsive images
   - Correct units
   - Desktop-first vs mobile-first
2. Maintainable code
   Clean
   Easy to understand
   Reusable
   How to organize files
   How to name classes
   How to structure HTML

3. Performance

## How CSS works BEHIND THE SCENES

- What happenns in the browser
  Loads html and parses it to convert to a Document Object Model
  Meanwhile css is parsed also => Resolve conflicting CSS declarations (cascade) and Process final CSS values
  the parsed css constitutes the CSS Object Model
  Both models create the Render tree

Then comes the website rendering, which is the visual formatting model
And the final rendered website exists

## How CSS is parsed: Part 1: The Cascade and Specificity

A CSS rule is the combination of a selection and its declaration block
A declaration is the property value pair
A property and a <strong>declared value</strong>

# Cascade

Process of combining different stylesheets and resolving conflicts bet dif rules and declarations when more than one rule applies to a certain element.

Author=>User=>Browser rules

Importance (weight) => specificity => source order

1. Importance
   1. User !important
      2 Author !important (use it as a last resource)
      3 Author declarations
   2. User declarations
   3. Default browser declarations

same importance----???

lets solve it with specificity

2. Specificity:

1. inline styles
1. IDs
1. Classes, pseudo-classes, attribute
1. Elements, pseudo-elements

(inline, ids, classes, elements) => number of them for each declaration

(0,0,1,0) => selector specificity for a declaration
(0,1,2,2) => another declaration selector specificity, this is more specific, this wins
(0,1,2,1)

same specificity---?

lets solve it with source order

3. Source order:

The last declaration in the code will override and win.

- Rely more on specificity than on the order of selectors.
- Rely on order when using 3rd party stylesheets

## How CSS is parsed: Part 2: Value Processing

1. Declared value (author declarations) --- width 140px vs 66% --- padding
2. Cascaded value (afther the cascade) ---- 66% --- -
3. Specified value (defaulting, if there is no cascaded value) ---66% -
4. Computed value (converting relative values to absolute) --- 66% --- 0px(initial value)
5. Used value (final calculations, based on layout)----184.8px --- 0px
6. Actual value (browser and device restrictions) ---185px --0px

The font size by default is 16px even if we do not define them as declared
The font-size ej: 1.5rem, 1.5rem, 1.5rem, 24px, 24px, 24px
not declared but the font-size can be inherited

## How units are converted from relative to absolute (px)

- % for fonts x% \* parent's computed font-size
- % for lengths x% \* parent's computed width

- Font-based em and rem

  - em for fonts uses the parent font-size
  - em for lengths uses x \* current element computed font-size
  - rem for font-sizes and lengths both uses x \* root computed font-size

- Based on the browser's viewport
  - vh x\*1% of viewport height
  - vw x\*1% of viewport width

## How CSS is parsed: Part 3: Inheritance

- A way of propagating elements from parents to children
- Each css property must have a value even if we don´t declare them
  ---> is there a cascaded value?
  --> yes, use that ona
  ---> no...is the property inherited (specific to each property)?
  ------> yes specified value = computed value of the parent element
  ------> no specified value = initial value(specific to each property)
  INHERITANCE OF A PROPERTY ONLY WORKS IF NO ONE DECLARES A VALUE FOR THAT PROPERTY
  THE COMPUTED VALUE OF A PROPERTY IS WHAT GETS INHERITED, NOT THE DECLARED VALUE
  THE INITIAL KEYWORD REFERS TO THE INITIAL VALUE FOR A PROPERTY

## Website rendering: the visual formatting model

Algorithm that calculates boxes and determines the layout of these boxes for each element in the render tree in order to determine the final layout of the page.
Takes into account:

- Dimesions of boxes: the box model;
- Box type: inline, block and inline-block
- Positioning scheme: floats and positioning;
- Stacking contexts,
- Other elements in the render tree
- Viewport size, dimensions of images, etc.

## Stacking contexts

- Think like a photoshop set of layers
- The stacking context is created by:
  - z-index
  - opacity
  - filters
