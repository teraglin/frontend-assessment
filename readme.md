# Frontend Assessment - Aidan Kirvan

aidankirvan@gmail.com
[aidankirvan.com](https://aidankirvan.com)

## Installation

| Node Version | package manager | Framework |
| ------------ | --------------- | --------- |
| v20.10.0     | Yarn            | Vue 3     |

1. Install

```bash
yarn install
```

2. Run

```bash
yarn serve
```

## Directory Tree - (excluding node_modules)

```
.
├── assessment-assets
│   ├── data.json
│   ├── exercise1-desktop.png
│   ├── exercise1-mobile.png
│   └── readme.md
├── babel.config.js
├── jsconfig.json
├── package.json
├── public
│   ├── favicon.ico
│   └── index.html
├── readme.md
├── src
│   ├── App.vue
│   ├── assets
│   │   ├── 1920x650.png
│   │   ├── 400x300.png
│   │   ├── 600x600.png
│   │   └── logo.png
│   ├── components
│   │   ├── accordion
│   │   │   ├── accordion-list.vue
│   │   │   └── accordion-section.vue
│   │   ├── buttons
│   │   │   └── card-button.vue
│   │   ├── cards
│   │   │   ├── card-component.vue
│   │   │   └── cards-container.vue
│   │   ├── hero-title.vue
│   │   ├── navigation
│   │   │   └── nav-bar.vue
│   │   └── tabs
│   │       ├── tab-list.vue
│   │       └── tab-section.vue
│   ├── data
│   │   ├── cards-data.json
│   │   └── tabs-data.json
│   ├── main.js
│   └── routes
│       ├── 404-page.vue
│       ├── exercise-1.vue
│       ├── exercise-2.vue
│       └── home-page.vue
├── vue.config.js
└── yarn.lock

13 directories, 33 files
```

# Explain why the result of `('b' + 'a' + + 'a' + 'a').toLowerCase()` is `banana`.

A `+` symbol following or proceedng any String value will concatenate those two values. A `+` symbol on its own before a value will convert that string into a number.

```javascript
// eg.

+"1";
// converts '1' into 1

"1" + "1";
// will concatenate the two values as '11'.

"1" + 1;
// '11'

1 + "1";
// '11'
```

If there are two `+` symbols **following** a String value, the first `+` will concatenate the next value while the second `+` will convert the following value into a Number. Again, regardless of the type of the following or proceeding value, if the first or second value is a string, it will be concatenated.

```javascript
// eg.

"1" + +1;
// will return '11'. Even though the second value is converted into a number, it will still be concatenated.

"1" + false;
// will return '1false' as an example of how this works with other data types.
```

Additionally, if a `+` is converting a value that **is not** a numerical value into a Number, the result will be `NaN` (Not a Number).

So because there are two `+` symbols before the second 'a' String value, it will be converted into a number and concatenated. And seeing as 'a' is not a numerial value, the concatenated value will be `NaN`

Therefore, 'b' + 'a' + NaN + 'a' = 'baNaNa'. And if you add the `toLowerCase()` you will return a new string that converts all uppercase letters to lowercase: 'banana'.

## Future considerations and improvements

Considering certain time constraints, and that this is my first time using Vue.js, I thought I'd write down some notes on things that I would work on or change if I were to continue working on this assessment.

- Look into moving functions out of top level components and ensure that shared logic is imported and distributed from one location at the top level.

- Define breakpoint and spacing css variables.

- More involved atomic structure for components and elements and modules.

- More accessibility and screen reader features:
  - alt attribute on exercise 1 images
  - ensure active and focusable elements are not on unique elements with an id attribute
  - language attributes for html element