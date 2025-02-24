---
date: 2025-02-16
updated: 2025-02-24
tags:
  - ebookproduction
  - epub
  - indesign
title: InDesign to the Fixed Layout ePub
---

The fixed-layout format ePUB3 format provides a way to deliver every single page in your print book laid out just as it was in the print version.

This fixed-layout format can be considered almost the same as an interactive PDF, however, as you will see, the ePUB can have much more interactivity and, you, the designer can control the way the eBook is displayed. For those that ask ‘why can’t I deliver a PDF?’. The answer is that you cannot sell and distribute a PDF through the same channels as the ePUB (or Kindle) format eBooks.

## The Basics
InDesign Creative Cloud 2014 introduced the ability to export the ePUB3 as a fixed-format package, and we can use this method to create a perfect acceptable ePUB3. However, it should be pointed out that the controls for the way certain aspects work in the export process, are limited:

- There is no way to include footnotes as popups (they will simply be at the bottom of the page - as in your print version)
- You cannot use the Articles panel to order content, or even prevent some objects from exporting.
- All items will be delivered as they appear, including the master page items.
- Post editing the CSS is almost impossible, because every single word on the page is positioned with the CSS, so you dare not make any adjustments. 

## InDesign export to ePUB (fixed layout) 
The instructions for this are very limited, but we should first explain that the fixed-layout ePUB is formed from many XHTML files – one for every single page that you see in the InDesign view. Whichever method you use for this output, you need to become aware of the individual pages (how they begin and end, if there are orphans and widows, and what your master page items look like. Effectively, you are now designing as if for print.

### Duplicate and move on. 

I suggest that you duplicate your InDesign documents and book, because you might (for this fixed-layout edition) be making some destructive changes. You need to *fork* this file as a new version.
  
### Page by Page
Go through all the pages, and satisfy yourself that each page is how you want it to be. You can make adjustments to fix widows and orphans. You should be certain that the master page items display correctly. Items can go to the edge of the page.

> [!important] 
> This help document presumes that you have already created the re-flowable eBook version and you have portrait orientation pages as if for a print book

Images are likely to be anchored in the text, although technically, for the fixed layout ePub you do not need images to be anchored. Since this is all about trying to use the same file for these different techniques, we should have anchored images!

> [!note] 
>  Images can now use the full size of the page, so you can move the images right to the edge of the page.

You will need to be using InDesign Creative Cloud. The screen images in this document are created from InDesign version 11.1.

Having had a good look at our InDesign book and files, we only have one matter to address – do we want the table of contents on the page or just as a logical TOC? If the TOC is on the page, then it will be on the page in the ePUB (fixed layout). If you don’t want this, you need to move it on to the paste board and delete those blank pages.

In the fixed-layout format for Apple devices there are 2 types of ‘tables of contents’; you will always have a thumbnail image version, but your table of contents in InDesign will also provide a logical menu item TOC, that will be available in a drop-down menu.

## Export ePUB (Fixed Layout)
I am presuming that you will export from the book panel, but if you are working with a single file, then the procedures are exactly the same. You will already be familiar with the panel that appears when you export the ePUB, only this time the features are limited.

### The General Section

![In this panel you can decide how the spread will be handled](../../media/id2fxlePub/image1.jpeg)

In the General panel you will need to select the cover image and the table of contents as a Multi Level Navigation from your saved TOC in InDesign.

There are Spread Layout options that will control the way the spread is formed. You can even join the pages as a landscape form. On the other hand, you may simply base the spreads on your layout (as if for print). You can also choose to Disable the Spreads so that only one page will show in a portrait format.

> [!note] 
>  If you decide to convert Spread to Landscape, it will be worth re-organising the pages so that the first is a spread. This will mean adding a page at the beginning.

If you do want to convert the spread to a landscape view you may want to look at adding a thin line to divide the 2 pages and even consider using the full width of the 2 page spread to add an image.  

### The Conversion Settings
![Choose the best quality for images unless the file size will become too large.](../../media/id2fxlePub/image2.jpeg)

In this panel we can decide how the export process will convert the graphics in your book.

The other panels that you can select include the following:

The CSS panel allows you to add your own CSS, however there are few adjustments that we are likely to need to make. Likewise the javascript panel provides a chance to add javascript, as we did for the re-flowable ePUB in the earlier note.

We will need to add Metadata in the appropriate panel, before we proceed.

## How Does our Fixed-Layout ePUB look?

![A sample spread in iBooks](../../media/id2fxlePub/image1.png)

You will see pages exactly as you had in the InDesign. Is this successful?

Certainly. If this is what you wanted, then we can surely say that we have a good fixed-layout eBook. But take a look at another image from a spread in the play.

![A spread showing that footnotes remain just that. No popups are possible](../../media/id2fxlePub/image2.png)

Here we see the problem with our footnotes. They are appearing as they did in the print version and we have no possibility of interactive popup notes.

Now have a look at the XHTML of one page in the eBook.

![The complexity of the markup is overwhelming](../../media/id2fxlePub/image3.png)

If you look carefully, you will see that every word on the page is wrapped in a span tag with a position set through an inline style rule. This is the way that InDesign has exported the content and it works to precisely position all content on the page. The problem comes when you want to make any edits after-export. We have little hope of making any changes to the CSS other than possibly adding a background colour to the pages.

## Some further Notes on the Fixed Layout ePub
### Adding HTML to InDesign

When adding local HTML to page in InDesign:

> If you are adding style or script information you may find that the ePub does not validate. There are 2 reasons for this:
> - you will find a tag 'object' wrapping the item that you added
> - InDesign export also adds 'scope' to the enclosing div.

### The fix
You will need to post edit the ePub to do the following:

- remove the `<object>` tag altogether
- add the value to the scope attribute like this:

`scope='scope'`

### Bookmarks
Bookmarks or hyperlinks (and hyperlink destinations) are the way to make links between documents in a ‘book’. But, the bookmark or hyperlink destination needs to be made by selecting the **whole** heading

### Fixed layout options from InDesign
To make a fixed-layout landscape where the print book is portrait spreads, choose _Convert Spread to Landscape page_

If you choose this option then you will fail if you try to convert to Kindle KF8 because KindleGen cannot locate the proper pages in the TOC.

### Table of Contents

The table of contents can be on the page and also as a logical TOC (provided in the UI of the eReader software). InDesign proves the option of more than one TOC, but the one you choose for the logical TOC would normally be provided on the pasteboard. The reason for this, is that you might want to make some edits to this before exporting to the ePub:

#### Possible issues with the logical TOC
When the heading item in the TOC is present in the cell of a table and the cell spans the spread (which then becomes a forced landscape page), the item is repeated in the TOC. You can only resolve this by editing the `toc.xhtml` file inside the ePub package.

### Export Options and Bleeding Objects

If your print ready InDesign has objects outside the page (ie. bleed), then, if you export the fixed-layout as _Based on Document setup_ - and you have 2 pages portrait as spread, then you may observe scrollbars in the eBook. This will also give you scrollbars where an object is spread across a 2 page spread