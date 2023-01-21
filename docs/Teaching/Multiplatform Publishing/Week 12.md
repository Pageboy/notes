---
hide:
 - navigation
---

# Week 12
Here are a few extra issues that have been noticed that can be fixed!

## Do you have a line down the middle of the spread?
If you have a solid colour across the spread - maybe a background or an image that covers both pages, you may notice a faint line down the middle. This is only noticeable in Apple Books, but here is why this is happening:

> This seems to be caused by the fact that the overall width of the eBook delivered by InDesign is 732px. For some reason, InDesign then creates 2 `divs` in the HTML with a width of 365.67px (this really should be 366px). 

I guess that Apple Books is able to comprehend a fraction of a pixel and makes this white line.

### How to fix

We can target that first div in the HTML with the CSS and correct the width. Fortunately there is a concept of  `first-child` in CSS, so what you need to do is to add this in your CSS that you are adding at export time:

```css
body > :first-child {
width: 366px !important;
}
```

This should correct the very first div and remove that annoying line.

## My full width video still doesn't play properly.

OK, it may be that although you added the javascript (see previous note for week 11), the video still splits into two. The cause may be because you have animated the video to appear on the page when loading. Perhaps you decided to fade up the video before it plays.

This will make the extra javascript inoperable. So - **don't do any fancy animation on that spread!**




