# FRONTEND ARCHITECTURE

**We want to create new features, or edit existing features without having to concern with overriding styles we don’t want applied, or worse that the code we write causes regression elsewhere.**

## Main goals are
1. Ensure consistency in code and design in all applications.
2. Reduce technical debt.
3. Keep application maintainable, modular and scalable.

---

## CSS File structure
####NORMALIZE
Normalize.css makes browsers render all elements more consistently and in line with modern standards. It precisely targets only the styles that need normalizing.

```
vendor.normalize
```

####CONFIG
This file is defining all global variables like colors, font family, font size and breakpoints.

```
config.css
```

####PARTIALS
#####Helpers

```
// Helpers
partials/helper.mixins.css
partials/helper.icon-font.css
partials/helper.keyframes.css
```

#####Foundation
```
// Foundation
partials/foundation/foundation.base.css
partials/foundation/foundation.buttons.css
partials/foundation/foundation.forms.css
partials/foundation/foundation.tables.css
partials/foundation/foundation.layout.css
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


## Examples
Here are some real examples for components:

```
/* component */
.navbar {}

/* child component */
.navbar.navbar-header {}

/* if used for javascript only */
.js-icon-animation {}

/* if used for mobile only */
.mobile-price-table {}
```

## Resources
- [ITCSS](https://github.com/itcss) by Harry Roberts
- [MaintainableCSS](http://maintainablecss.com/) by Adam Silver
- [Pattern Lab](http://patternlab.io/) by Brad Frost


---
## JS File structure
In progress...



