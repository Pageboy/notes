---
tags:
  - ebookproduction
  - indesign
  - html
  - css
date: 2025-02-16
updated: 2025-02-25
title: Notes on Fixed Layout eBook
---

## Adding HTML to InDesign

When adding local HTML to page in InDesign:

If you are adding style or script information you may find that the ePub does not validate. There are 2 reasons for this:

- you will find a tag 'object' wrapping the item that you added
- InDesign export also adds 'scope' to the enclosing div.

### The fix

You will need to post edit the ePub to do the following:

- remove the \<object\> tag altogether
- add the value to the scope attribute like this:

`scope='scope'`

## Bookmarks

Bookmarks or hyperlinks (and hyperlink destinations) are the way to make links between documents in a ‘book’. But, the bookmark or hyperlink destination needs to be made by selecting the **whole** heading

## Swashes in the text

Although you can add swash alternates to an opentype font in InDesign these won’t get pushed into the fixed layout ePub . You might expect to be able to select individual letters within the word and then add CSS through the style ‘export tagging’. Unfortunately this does not seem to work at all in the latest version of InDesign.

### How to fix

This does involve some editing of the HTML as well as the CSS, so beware that you will break the ‘round trip’ to InDesign. In other words, only do this at your final stage.

Here is an example of the output from InDesign to the fixed-layout ePub:


```html
<span id="idTextSpan003" class="CharOverride-2" style="position:absolute;top:-70.31px;left:0px;letter-spacing:-0.64px;">Shakespeare</span>
```

Yes, I know. Kind off complex isn’t it?

You will see that the word ’Shakespeare’ is enclosed in a span tag.

What we need to do is to enclose each of the letters that need to use the swash in another span tag. (It is perfectly legitimate to nest span tags). This span tag needs a class:


```html
<span id="idTextSpan003" class="CharOverride-2" style="position:absolute;top:-70.31px;left:0px;letter-spacing:-0.64px;">Sha<span class="swash">k</span>espear <span class="swash"> e</span></span>
```

I have gone for the ‘k’ and the last ‘e’.

Now we need to add some CSS and we can do this in the CSS file that InDesign has created (or we can create our own CSS file to be loaded at export time):

```css
span.swash {
font-feature-settings: "swsh" 1;
}
```

The font that I am using here is the revival FELL font created by [Igino Marini][1].

### Fixed layout options from InDesign

To make a fixed-layout landscape where the print book is portrait spreads, choose _Convert Spread to Landscape page_

If you choose this option then you will fail if you try to convert to Kindle KF8 because KindleGen cannot locate the proper pages in the toc.

### Footnote Options for the Fixed-layout ePub

InDesign can build the footnotes perfectly well for print / PDF. Some clever options for the styling and the amount of offset from the body text. This will translate to the fixed-layout ePub; what you see is what you'll get. The reflowable ePub (from InDesign) will provide the option for making the footnotes popups (nice), or making the footnotes hyperlinked to the back of the book (endnotes). Fixed-layout export does not give you any options like this, so you will need to consider a hack if you want anything different.

#### Let's hack the footnotes then

[see this artcle](../Articles/Footnotes-and-%20other-Diversions.md)

### Table of Contents

The table of contents can be on the page and also as a logical TOC (provided in the UI of the eReader software). InDesign proves the option of more than one TOC, but the one you choose for the logical TOC would normally be provided on the pasteboard. The reason for this, is that you might want to make some edits to this before exporting to the ePub:

#### Possible issues with the logical TOC

When the heading item in the TOC is present in the cell of a table and the cell spans the spread (which then becomes a forced landscape page), the item is repeated in the TOC. You can only resolve this by editing the toc.xhtml file inside the ePub package.

Other noted issue: if your print ready InDesign has objects outside the page, then if you export the fixed-layout as 'Based on Document setup'- and you have 2 pages portrait as spread, then you may observe scrollbars in the eBook.

## Decision workflow

Is the book to be both print and eBook?
### If Yes

Has the page size been determined?

Will this be fixed layout?

Page size:

If the design of the book needs to show spreads (because there are images or tables across the spine), then choose a page size that is near as possible 8x6 proportion. This is so that the eBook can use all space on a standard tablet.

You can fork the eBook version and modify the page size if you really need a more square format for the printed book.


