# Sass 💗

[ Go](https://sass-lang.com/documentation/)
[What are you waiting for...? Go!](https://sass-lang.com/guide)

## Installation npm sass

[npm sass](https://www.npmjs.com/package/sass)

## to compile

[One-to-One or Many-to-Many](https://sass-lang.com/documentation/cli/dart-sass/)

### gradients with sass color variables

```scss
linear-gradient(
      to right bottom,
      rgba($color-primary-light, 0.8),
      rgba($color-primary-dark, 0.8)
```

## 7-1 architecture

The 7-1 architecture is a common way to organize your Sass (SCSS) files in a structured and scalable manner. Here's a description of what each folder typically contains in the 7-1 architecture:

1. **base/**

   - Contains global styles, resets, and typography.
   - Files like `_reset.scss`, `_typography.scss`, `_colors.scss`, etc., would be placed here.

2. **components/**

   - Contains styles for reusable UI components.
   - Each component has its own folder with a Sass file containing component-specific styles.

3. **layout/**

   - Contains styles for the layout structure of your application.
   - Files like `_grid.scss`, `_header.scss`, `_footer.scss`, etc., would be placed here.

4. **pages/**

   - Contains page-specific styles.
   - Each page of your application can have its own folder with a Sass file containing styles specific to that page.

5. **themes/**

   - Contains styles related to theming or different visual variations of your application.
   - Files like `_dark-theme.scss`, `_light-theme.scss`, etc., would be placed here.

6. **abstracts/**

   - Contains Sass utilities, mixins, functions, and variables.
   - Files like `_variables.scss`, `_mixins.scss`, `_functions.scss`, etc., would be placed here.

7. **vendors/**

   - Contains third-party or external styles, such as CSS frameworks or libraries.
   - Files like `_bootstrap.scss`, `_font-awesome.scss`, etc., would be placed here.

8. **main.scss**
   - The main entry point for your Sass styles.
   - This file typically imports all other Sass files and acts as the compiled output for your entire stylesheet.

This architecture helps maintain a clear separation of concerns, making it easier to manage and scale your stylesheets in large projects. Each folder has a specific purpose, making it easier to find and update styles as needed.

## Interpolation

Example of using interpolation within a mixin in SCSS:

```scss
// Define a mixin with interpolation
@mixin dynamicProperty($property, $value) {
  #{$property}: $value;
}

// Usage of the mixin with interpolation
.my-button {
  @include dynamicProperty("background-color", blue);
  @include dynamicProperty("border", 1px solid black);
}
```

In this example:

- We define a mixin `dynamicProperty` that takes two parameters: `$property` (the CSS property name) and `$value` (the value for that property).
- Inside the mixin, we use interpolation `#{ ... }` to dynamically generate the CSS property name based on the `$property` parameter.
- We then include the mixin `dynamicProperty` twice within the `.my-button` selector, passing different property-value pairs.

When this SCSS code is compiled to CSS, it generates:

```css
.my-button {
  background-color: blue;
  border: 1px solid black;
}
```

This approach is powerful for creating reusable mixins that generate dynamic CSS rules based on the parameters passed to them, making your stylesheets more versatile and adaptable.
