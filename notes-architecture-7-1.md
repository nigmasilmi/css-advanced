## The Think - Build - Architect Mindset

### Think: Component Driven Design

- Divide page into modular components, the building blocks, that must be independent, re-usable, held together by the layout of the page.

(ATOMIC DESIGN bradfrost.com)

### Build: structure naming convention: BEM

- Block Element Modifier
- Block is a standalone component that can live on its own (a component defined before) e.g: recipe\_\_
- Element is a part of a block with no meaning of its own e.g: recipe\_\_stat
- Modifier is a flag in a element to make them different from the normal elements e.g: recipe\_\_btn--round

### Architect: logical structure

#### The 7-1 Pattern

- 7 different folders for partial Sass files and 1 main Sass file to import all other files into a compiled CSS stylesheet.
  - base/
  - components/
  - layout/
  - pages/
  - themes/
  - abstracts/
  - vendors/
    All or some of them can be used.
