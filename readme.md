## Introduction

Thanks for taking the time to complete this frontend technical assessment. We will be focusing on software quality (scalability, readability, maintainability, etc.) and your eye for detail. You may include any libraries, but Vue.js is preferred and jQuery is not recommended. Along with following best practices, bonus points for following our [coding guidelines](https://github.com/mindarc/frontend-assessment/wiki/Coding-guidelines).

## Exercise 1

Build a responsive page based on the designs.

##### Requirements

1. Match the designs exactly.
2. Needs to be responsive.

##### Designs

- exercise1-desktop.png
- exercise1-mobile.png

##### Assets

- Desktop banner - https://via.placeholder.com/1920x650
- Mobile banner - https://via.placeholder.com/600x600
- Content images - https://via.placeholder.com/400x300

## Exercise 2

Read the `data.json` file and display the data as tabs on desktop and an accordion on mobile.

##### Requirements

1. Display data in tabs on desktop.
2. Display data in an accordion on mobile.
3. Only 1 accordion/tab should be open at a time.
4. Open the first accordion/tab on load.
5. If the open accordion is selected, close it.

###### Bonus points

- Improve the user experience with meaningful animations/transitions.
- Design and styling.
- Explain why the result of `('b' + 'a' + + 'a' + 'a').toLowerCase()` is `banana`.

A: A `+` symbol following or proceedng any String value will concatenate those two values. A `+` symbol on its own before a value will convert that string into a number.

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

Therefore, 'b' + 'a' + NaN + 'a' = 'baNaNa'.

## Submission

We recommend submitting your completed assessment as a forked repository. Please replace README content with instructions and relevant documentation.
