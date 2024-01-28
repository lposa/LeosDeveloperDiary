# CSS Methodologies

## BEM

Link: https://getbem.com/

Block Element Modifier

BEM is a methodology that helps you to create reusable components and code sharing in front‑end development

The reason I choose BEM over other methodologies comes down to this: it is less confusing than the other methods (i.e. SMACSS) but still provides us the good architecture we want (i.e. OOCSS) and with a recognizable terminology. - Mark McDonnell, Maintainable CSS with BEM

```html 
<div class="card card--light">
    <img class="card__image" src="some/image" alt="img"/>
    <h2 class="card__title">Title</h2>
    <p class="card__body">Paragraph</p>
</div>

<div class="card card--dark">
    <img class="card__image" src="some/image" alt="img"/>
    <h2 class="card__title">Title</h2>
    <p class="card__body">Paragraph</p>
</div>
```

1. -- means a modifier to a block
2. __ means a block element
3. DO NOT HAVE A GRANDCHILD

The block class gives shared styles to elements. This way we don't repeat ourselves, and we also change styles only 1 place. Imagine having 5 different block classes that are essentially the same, and we want to change padding on them, we would have to go through all of them.

SASS makes this even easier:

```scss
.object {
  color: red;
  
  &__descendant {
    color: black;
  }
}

```

## OOCSS 

Object-oriented css.
Separating container and content with CSS “objects”

## SMACSS 

Style-guide to write your CSS with five categories for CSS rules
1. Base - basic default values for our pages (margins, colors, etc...)
2. Layout - divide the page into sections, hold one or more modules together
3. Module - reusable parts that are repeated in some form on the page. Widgets, menus and form styling. Avoid using IDs, stick to classes.
4. State - augments and overrides all other styles. Example: a message may be in a success or error state.
5. Theme - all the other additional decorative visual elements that make your wep page unique. Main colors, shapes, borders, shadows, branding.


## Atomic

Breaking down styles into atomic, or indivisible, pieces
Very similar to bootstrap


## Boostrapt with SASS

```scss
.primary-rail {
  @extend .pull-left, .col-md-6, .small;
}
```

## Assessment requirements

1. Advanced knowledge of several methodologies: BEM, OOCSS, SMACSS, ITCSS, Atomic CSS
2. Able to compare methodologies mentioned above
3. Intermediate understanding of CSS-in-JS, CSS Modules

## Comparison 

### BEM

- Flat structure: Every block (top-level component type) has its own flat namespace and is independent from other blocks.
- Explicit relationships: Element classes explicitly link to their Block parent.
- Self-documenting syntax: The class name directly refers to the purpose or visual aspect of an element.
- Good for small-medium projects, but can lead to long class names and repetition in large, complex projects.

### OOCSS (Object-Oriented CSS)

- Modular approach: Design is broken down into reusable objects or modules.
- Structure vs skin: Separates the structure from the design, leading to reusability of your CSS and less code.
- Agnostic to markup: Encourages class-based design rather than element selectors, providing flexibility.

### SMACSS

- Provides a style guide: Offers prescriptive guidance on structuring and organizing stylesheets.
- Categories for selectors: Base, layout, module, state, and theme.
- Good for large-scale projects, but requires a learning curve and discipline to follow.

### ITCSS 

- Architectural approach: Provides architecture, not naming convention.
- Specificity sort: CSS is organized in order of increasing specificity.
- Highly scalable: Suitable for large, long-lasting, complex projects, with large teams.
- File structure-based: Helps manage growing CSS projects by dividing them into several layers.


### Atomic CSS

- Utility-focused: Class names are usually single-purpose, tied directly to a specific style.
- Less repetition: Prevents redundancy of properties throughout CSS.
- Granular control: Each element's styling is a composition of utility classes.
- No cascade issues: Because classes are single-purpose, it eliminates many of the cascade side effects.
- Considered verbose because each element has a list of class names.
- Learning curve: This system is best suited when the project team is comfortable with functional (utility-first) CSS.

I personally worked with BEM in Salesforce and SMACSS in React/Next.js. 


Extra content: <br/>
BEM: https://www.youtube.com/watch?v=SLjHSVwXYq4&ab_channel=KevinPowell <br/>
SMACSS: https://www.youtube.com/watch?v=DHph0kuNf-s&ab_channel=HiCoders <br/>
About all: https://www.youtube.com/watch?v=IKFq2cSbQ4Q&ab_channel=GainesvilleFront-endDevelopersMeetup