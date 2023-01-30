---
hide:
 - navigation
tags:
 - multiplatform
 - typography
 - indesign
---

Following on from page size in the reflowable eBook, how about the fixed-layout eBook after it has been created as a print book? So you have used InDesign to create a wonderful printed book of a Shakespeare play, and you chose a standard page size (my example is: 216mm x138mm). Now when you make the fixed layout eBook from the spreads there might be a few observable problems.

## Proportion

Our print book spreads will become landscape in the fixed-layout eBook. So, we will get the following proportions:

`width:138 x 2 = 278`
`height = 216`

`Proportion = 216/278 = 0.7777`

On a computer running Apple iBooks or any other eReader, the proportion is
not really significant because all computer displays vary in proportion. However, on a tablet such as the iPad the proportion is specifically 6x8 or 0.75. So, we need to modify the size of the pages in the InDesign file very slightly; keeping the width of the pages, we take the width of the spread and multiply by 0.75 and we get 208.5. So we lose about 8mm in the height.

Here we see that the page size does not exactly fit on the iPad

![[ipad_edgerevealed.jpg]]

## Theory and Practice

The above scenario takes a book designed for print and makes one adjustment in a attempt to resolve the proportion riddle, however, in practise there may still be gaps and mysterious white lines.

### It's all about the units

The numbers that we refer to above are in millimetres because in Europe we tend to use metric units to measure page sizes.

When InDesign exports the fixed-layout eBook, it needs to make a conversion from real-world units (millimetres) to pixels. If we take a peak inside the ePub package at one of the `XHTML` files we see that:

`<meta name="viewport" content="width=782,height=591" />`

This tells the ereader that the size is 782x591. The proportion, therefore is `0.755754475703325` - very slightly wrong! The height should be: `586.5`.

### Let's not edit the ePub

We don't need to edit the XHTML code inside the ePub. No, we just need to adjust the InDesign file to use pixel units. Here's how:
### Unit Preferences

In Indesign, go to the preferences panel and find the `units and increments` section. Change the Ruler units for both vertical and horizontal to **pixels**.

Change from millimetres to pixels

![[changetheunitstopixels.png]]

### Page size

Now go to File>Document setup and see that the page size is now an untidy fraction of pixels (391.181 x 591.024). Not nice!

We need to do some adjustment to these numbers to get a 3/4 proportion and hopefully exact pixels numbers. Pixels are tiny little units so this should not impact our designs too much.

The result is a page width of `396 pixels` and page height of `594 pixels`. When we add 2 pages together the landscape becomes `792 x 594 = 8 x 6`.

## Document set up or pages size

You can go back to the File>Document setup and change the page size. This will work, however, you can use the Page Tool on the tool palette and select all master pages in the Pages panel. You then can control the reference point for the change to happen (choose the centre top).

In the documents setup we now need to adjust to a whole pixel number.

![[documentsetup.png]]

Then you need to apply the master pages to all pages and also set the page size in the document setup panel.
