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
