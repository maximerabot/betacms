# FRONTEND ARCHITECTURE

### Main goals are

1. Ensure consistency in code and design in all applications.
2. Reduce technical debt.
3. Keep application maintainable, modular and scalable.

---

## CSS File structure
**Goal is to write CSS in specificity order from generic to explicit (based on the ITCSS methodology). Progressively adding, never ondoing styles.**

####NORMALIZE
Makes browsers render all elements more consistently and in line with modern standards. It precisely targets only the styles that need normalizing.

```
vendor.normalize
```

####CONFIG
This file is defining all global variables like color scheme, font family, font size and breakpoints. The values are brand and project specific.

```
config.css
```

####PARTIALS
#####Helpers
Useful functions, icon library and keyframes for animations.

```
// Helpers
partials/helper.mixins.css
partials/helper.icon-font.css
partials/helper.keyframes.css
```

#####Foundation
Defines the foundation of the project.

```
// Foundation
partials/foundation/foundation.base.css [only pure HTML elements like body, a, h1, img]
partials/foundation/foundation.buttons.css [styling all different CTAs]
partials/foundation/foundation.forms.css [form elements like input, textarea]
partials/foundation/foundation.tables.css []
partials/foundation/foundation.layout.css []
```

#####Components
A component is a distinct, independent unit, that can be used in multiple place through the website.

```
// Components
partials/components/component.header.css
partials/components/component.navigation.css
partials/components/component.searchbar.css
...

// Child components (only used if the a lot of styles are needed)
partials/components/component.header.navigation.css
partials/components/component.header.searchbar.css
...
```

## Naming convention
Name something based on what it is, not how it looks or behaves. Semantic class names mean something to both HTML and CSS (and JS). If you’re beginning your search via the HTML (think: inspecting an element) then finding unique CSS selectors based on the class name will be far easier. Semantic class names are unique, so when editing one, you can feel comfortable that your change only applies to the compoment in question as you intended, making maintainance easier.

We will avoid using IDs since the specificity is too high and we can’t override an ID selector’s style with a class name selector easily.

1. components parts should always start with the component name
2. there is a core structure that should not be changed (if, then only from the senior frontends)
3. some elements can be extended by adding double dash to the class (example: .dialog-title--warning)


## Examples
Here are some real examples for components:

```
/* component */
.navbar {}

/* child component */
.navbar.navbar-header {}

/* component modifier */
.navbar-title--user {}

/* if used for javascript only */
.js-icon-animation {}

/* if used for mobile only */
.mobile-price-table {}
```

## Resources
- [ITCSS](https://github.com/itcss) by Harry Roberts
- [MaintainableCSS](http://maintainablecss.com/) by Adam Silver
- [Pattern Lab](http://patternlab.io/) by Brad Frost



