## backface-visibility

`backface-visibility` in CSS is a property that controls whether or not the back face of an element should be visible when the element is rotated in 3D space. This property is particularly useful when working with CSS 3D transforms.

Here's a breakdown of `backface-visibility`:

- **Property Name:** `backface-visibility`
- **Values:**
  - `visible`: The back face of the element is visible.
  - `hidden`: The back face of the element is hidden.

When you apply a 3D transform like rotation to an element using CSS, such as `transform: rotateY(180deg);`, the element can have a front face and a back face. The `backface-visibility` property determines whether the back face is visible or hidden.

**Use Cases for `backface-visibility`:**

1. **Card Flipping Animation:**
   When creating card flipping animations, such as a card that flips from its front side to its back side, you can use `backface-visibility: hidden;` to ensure that the back face of the card is not visible until it rotates.

   ```css
   .card {
     width: 200px;
     height: 300px;
     background-color: blue;
     transform-style: preserve-3d;
     transition: transform 0.5s ease;
   }

   .card:hover {
     transform: rotateY(180deg);
   }

   .card .back {
     backface-visibility: hidden;
     transform: rotateY(180deg);
   }
   ```

2. **Creating 3D Objects:**
   When designing 3D objects using CSS, you can control the visibility of the back face based on your design requirements. For example, in a 3D cube created with CSS, you might want to hide the back faces to maintain a cleaner appearance.

   ```css
   .cube {
     width: 100px;
     height: 100px;
     transform-style: preserve-3d;
   }

   .side {
     width: 100%;
     height: 100%;
     position: absolute;
     backface-visibility: hidden;
   }

   .front {
     transform: rotateY(0deg) translateZ(50px);
     background-color: blue;
   }

   .back {
     transform: rotateY(180deg) translateZ(50px);
     background-color: green;
   }
   ```

3. **Improving Performance:**
   In some cases, setting `backface-visibility: hidden;` can improve rendering performance by preventing unnecessary rendering of elements that are not visible to the user.

Overall, `backface-visibility` is a handy CSS property when working with 3D transformations and animations, allowing you to control the visibility and appearance of an element's back face.

## :link

The `:link` pseudo-class in CSS is used to target and style links that are in their default, unvisited state. In other words, it selects links that have not been visited by the user and have their default styles applied.

Here's a breakdown of the `:link` pseudo-class:

- **Name:** `:link`
- **Usage:** Targets links in their default, unvisited state.
- **Syntax:** `a:link { /* styles */ }`

When you apply styles using `:link`, those styles will affect the appearance of links that users haven't clicked on yet. This is particularly useful for setting the initial appearance of links in your webpage before they are visited.

For example, you can use the `:link` pseudo-class to set the color, font size, or text decoration of links that are yet to be visited:

```css
a:link {
  color: blue; /* Default link color */
  text-decoration: none; /* Remove underline */
}

a:link:hover {
  text-decoration: underline; /* Underline on hover */
}
```

In the above code:

- `a:link` targets all links (`<a>` elements) that are in their default, unvisited state.
- `color: blue;` sets the default color of unvisited links to blue.
- `text-decoration: none;` removes the underline from unvisited links.
- `a:link:hover` targets unvisited links when hovered over and applies an underline effect (`text-decoration: underline;`) to them.

It's worth noting that modern browsers often apply default styles to links, such as different colors for visited and unvisited links, underlines, and hover effects. Using the `:link` pseudo-class allows you to override these defaults and customize the appearance of unvisited links to match your design preferences.

## animation-fill-mode

The `animation-fill-mode` property in CSS controls how the styles are applied to an element before and after the animation plays. It determines whether the styles defined in the keyframes of an animation should persist after the animation finishes or revert to their initial or final state.

The `animation-fill-mode` property can take the following values:

1. **`none`:** The animation does not apply any styles to the element before or after it plays. The element remains in its initial state before the animation starts and returns to that state after the animation ends.

2. **`forwards`:** The animation applies the styles defined in the last keyframe (100% or `to`) to the element after the animation finishes. The element retains these styles instead of reverting to its initial state.

3. **`backwards`:** The animation applies the styles defined in the first keyframe (0% or `from`) to the element before the animation starts. This is typically useful for setting up initial styles that should be applied before the animation begins.

4. **`both`:** Combines the effects of both `forwards` and `backwards`. The element retains the styles from the last keyframe after the animation finishes and applies the styles from the first keyframe before the animation starts.

Let's illustrate these concepts with an example using CSS animations:

```css
@keyframes slide-in {
  0% {
    transform: translateX(-100%);
    opacity: 0;
  }
  100% {
    transform: translateX(0);
    opacity: 1;
  }
}

.animated-element {
  animation-name: slide-in;
  animation-duration: 1s;
  animation-fill-mode: forwards;
}
```

In this example:

- We define a CSS animation named `slide-in` that slides an element in from the left and fades it in.
- The `.animated-element` class applies this animation to an HTML element.
- `animation-fill-mode: forwards;` ensures that after the animation completes, the element retains the styles defined in the last keyframe (`100%`)—in this case, it remains visible (`opacity: 1;`) and in its final position (`transform: translateX(0);`).

Adjusting the `animation-fill-mode` property allows you to control how elements behave before and after CSS animations, providing more control over the animation effects and their impact on the layout.

## outline vs border

In CSS, both `outline` and `border` are used for styling elements, but they serve different purposes:

1. **Border:**

   - The `border` property is used to create a visible border around an element.
   - It has three main components: `border-width`, `border-style`, and `border-color`, which define the width, style (such as solid, dashed, double, etc.), and color of the border, respectively.
   - Borders are part of the box model and affect the size and layout of the element they are applied to.
   - Borders can be applied individually to each side of an element (top, right, bottom, left), or all sides at once using the `border` shorthand property.

2. **Outline:**
   - The `outline` property is used to create a non-rectangular border around an element, typically used to highlight an element without affecting its layout.
   - It is often used for focus states, such as when an element receives keyboard focus or is clicked.
   - The `outline` property has three main components: `outline-width`, `outline-style`, and `outline-color`, which define the width, style (such as solid, dashed, double, etc.), and color of the outline, respectively.
   - Unlike borders, outlines do not affect the size or layout of the element they are applied to. They are drawn outside the element's border box and do not take up space.

In summary, the main difference is that `border` affects the size and layout of an element, while `outline` is used for visual styling without affecting the layout. Additionally, outlines are typically used for focus states or to highlight elements temporarily, whereas borders are more commonly used for structural styling.
