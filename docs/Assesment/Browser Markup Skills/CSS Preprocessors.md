# CSS Preprocessors

## SASS - SCSS

- Variables - they add consistency in the code. Let's say we have colors, we can have a ```primaryColor:blue``` and use it throughout the code. If we want to change
the color at any time, instead of changing it one by one, we can just change the variable.
- Nesting - better organization of code, although, we should avoid too much nesting.
- Partials - dividing the styling by file, importing them where needed. Useful in organization and readability. Good to combine in with the SMACSS methodology (style-guide)
- Mixins - create a "function" that returns a specific style. This helps us avoid repetition. Can use variables.
- Inheritance - we can extend a specific style in another one. It will inherit all the styles from the extended style.
- Calculations - we can use calculations for a more dynamic styling.
- Conditions and loops - sass supports this. This powerful functionality can help to generate complex stylesheets while keeping your SCSS source code DRY (Don't Repeat Yourself) and readable.

### Mixins vs. @extend

- Use mixins if you require dynamic styles. Mixins are injected multiple times in the compiled css, so it creates a bloated stylesheet.
- @extend shares the code, so it's not repeated. But, it can't support dynamic styles, but again, overusing it can create bloated CSS.

Extra resource: https://www.youtube.com/watch?v=Zz6eOVaaelI