# Frontend Mentor - Four card feature section solution

This is a solution to the [Four card feature section challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/four-card-feature-section-weK1eFYK). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)
- [Acknowledgments](#acknowledgments)

**Note: Delete this note and update the table of contents based on what sections you keep.**

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the site depending on their device's screen size

### Screenshot

![](./documentation/preview-desktop.png)
![](./documentation/preview-tablet.png)
![](./documentation/preview-mobile.png)
### Links

- Solution URL: [github](https://github.com/darkquail/four-card-fature-section)
- Live Site URL: [live preview](https://darkquail.github.io/four-card-fature-section/index.html)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- CSS Grid
- Mobile-first workflow

### What I learned

Clear up my confusion about CSS Grid, rather than wrapping unique column layout i can use `grid-template-areas:` instead.

My first solution is wrapping `.card` content with a wrapper called `.card-wrapper__column` to make card 2 and 3 merge into one column so i can make unique layout according to the design like this :

```css
.card-wrapper__column {
    display: grid;
    grid-template-rows: 1fr;
    gap: 2rem;
}
```
That method is technically works but i don't really like the layout flow idea so i use `grid-template-areas:` properties and delete `.card-wrapper__column` and controlling layout directly from the `.card` wrapper that i named it `.card-wrapper` and select each child element inside it.

```css
.card-wrapper {
        grid-auto-columns: 1fr;
        grid-template-areas:
            ". two ."
            "one two four"
            "one three four"
            ". three .";
    }

    .card:nth-child(1) {
        grid-area: one;
    }

    .card:nth-child(2) {
        grid-area: two;
    }

    .card:nth-child(3) {
        grid-area: three;
    }

    .card:nth-child(4) {
        grid-area: four;
    }
```
NOTE : the `.` is the symbol to make me know which one is the white space.

### Useful resources

- [mdn docs about grid-template-areas](https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-areas) - this help me to understand how `grid-template-areas` properties works

