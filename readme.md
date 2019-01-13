| LAST UPDATES (13-01-2019)|
| ------------- |
|Added CSS GRID LAYOUT module|
|Optimized typography rules for DESKTOP and MOBILE| 


# FRONTEND ARCHITECTURE

### Main goals are

1. Ensure consistency in code and design in all applications.
2. Reduce technical debt.
3. Keep application maintainable, modular and scalable.

---

## CSS File structure
**Goal is to write CSS in specificity order from generic to explicit (based on the ITCSS methodology). Progressively adding, never ondoing styles.**

#### NORMALIZE
Makes browsers render all elements more consistently and in line with modern standards. It precisely targets only the styles that need normalizing.

```
normalize.scss
```

#### CONFIG
This file is defining all global variables like color scheme, font family, font size and breakpoints. The values are brand and project specific.

```
config.scss
```

#### PARTIALS
##### Helpers

Useful functions and keyframes for animations.

```
// Helpers
helpers/helper.mixins.scss
helpers/helper.keyframes.scss
```
---

##### Foundation
Defines the foundation of the project.

```
// Foundation
foundation/foundation.base.scss
foundation/foundation.buttons.scss
foundation/foundation.forms.scss
foundation/foundation.tables.scss
```
---

##### Layout
Defines layout elements likes sections and grids.

```
// Layout
layout/layout.scss
```
---

##### Components & Atoms
A component is a distinct, independent unit, that can be used in multiple place through the website. An atom is a reusable element but used in context with a component.

```
// Atoms - Examples
components/atom.user-picture.scss
components/atom.reward-label
...

// Components - Examples
components/component.searchbar.scss
components/component.dialog.scss
components/component.shop-block.scss
...
```

## Naming convention
Name something based on what it is, not how it looks or behaves. Semantic class names mean something to both HTML and CSS (and JS). If you’re beginning your search via the HTML (think: inspecting an element) then finding unique CSS selectors based on the class name will be far easier. Semantic class names are unique, so when editing one, you can feel comfortable that your change only applies to the compoment in question as you intended, making maintainance easier.

We will avoid using IDs since the specificity is too high and we can’t override an ID selector’s style with a class name selector easily.


### Example
This example of naming convention is based on the BEM approach:

```html
// Component
<div class="block">...</div>

// Component sub-element
<div class="block">
  ...
  <span class="block__elem"></span>
</div>

// Component modifier
<div class="block block--mod">...</div>
```

## Resources
- [ITCSS](https://github.com/itcss) by Harry Roberts
- [MaintainableCSS](http://maintainablecss.com/) by Adam Silver
- [Pattern Lab](http://patternlab.io/) by Brad Frost
- [BEM](http://getbem.com/naming/)
- [CSS Architecture - Sparkbox](https://seesparkbox.com/foundry/thoughtful_css_architecture)
