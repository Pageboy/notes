# What kinds of eBooks are possible?

We can go into the details of these formats later but in this section we can just list the types and some of the basic attributes.

## PDF (Portable Document Format)

Here is a format that many will already use. PDF was invented by Adobe Systems but the format is open and anyone can create an application to display the PDF. The great thing about the PDF is that it can display the various components of a page with graphics, text and fonts all embedded in the same file. This is what makes it easy to distribute, because everything is contained inside one file.

Although the PDF is used to capture _print-ready_ information and is most often used as the final stage in publishing for print, it can also include interactive navigational components and be used as a means to deliver screen based materials. In fact the PDF can be a very sophisticated eBook with animations, multimedia and even javascript that can provide some transitions and menu delivery.

Problems with the PDF as an eBook include the fact that tablets and eInk devices don't have appropriate software to make use of these extra interactive features. Selling PDF eBooks through the main vendor's ecosystems (Apple, Amazon etc.) is also **not** possible. PDFs can be delivered (and often are) through publisher's web sites, but adding DRM (Digital Rights Management) is expensive.
 
## ePub

The first version of the ePub standard was released by the International Digital Publishing Forum (IDPF) in 2007. The IDPF is a consortium of organisations and individuals. The standard is open and anyone can create software that will read and display the ePub.

The specification was originally in use as version 2 (ePub2) and in this release books could **only** be re-flowable with text not formatted as is for print but more like a web page; flowing to fit the size of the device or window.

In 2014 the ePub3 version was released and now includes the ability for content to arranged as 'fixed' or precise layout. This new format also can include 'overlays' to deliver javascript, multimedia and animation.

In the latest version of the format ePub3, we have 2 available modes; the re-flowable and the fixed-layout forms. They are different in the amount of display control that they leave to the user/reader. Within a re-flowable eBook, the user may change the font size, the typeface and (on some devices), display features such as leading, alignment, justification and hyphenation. On the other hand, the fixed-layout form removes any such flexibility, and the page designer can arrange text and image on each page and be sure that this is how it will remain. The fixed-layout form is the friend to the graphic designer; the re-flowable form provides more accessibility for the user.

So, in summary, the ePub can either be used to deliver *re-flowable* or *fixed-layout* content.

The ePub file can be converted to the Kindle `mobi` format (see below), and Amazon make available tools to make this conversion relatively painless[^1]. A good publishing strategy is to create for the ePub format first and then convert to the Kindle format from your validated ePub file. This is the best way you get the best of both worlds because you can test on the devices before release. On the other hand, Amazon will convert the ePub for you when you submit the ePub to them, however, you will not see the Kindle version until it is already on the Amazon Kindle store.

## Kindle Formats

I am separating these formats out because they are specific to the Amazon family of products such as the Kindle eInk reader.

The MOBI format used on the eInk devices is based on the original format used on PDAs (Personal Digital Assistants) such as the _Palm Pilot_. Amazon took over this format in 2005 and have further developed the specification to include a the KF8 format; targeting the Kindle tablets, such as the Kindle Fire, which can display fixed format and media rich eBooks.

The Kindle formats are not an open (public) formats and no devices other than the Amazon family can use the format.

### Apple's Multi-touch eBook format

This format of eBook can only be created with Apple's free software; iBooks Author.

>Apple iBooks Author is discontinued and Apple have enhanced their word processor software  _Page_ such that it can export reflowable eBooks (in the ePub format).

This is a proprietary format, only viewable on Apple devices (iPad or MAC) and is more difficult to define. It is a package of files in a container that has similar characteristics to the ePub, but post editing the contents is not recommended! The iBook format can be read on the iPad's iBooks app or on a MAC with iBooks.

## General Summary

It is very difficult to advise anyone which is the best approach for publishing eBooks, because it will depend on so many variables. For what it’s worth though, here are my 3 points that you should consider:

- If the content is mostly text, then build as a re-flowable ePub3 (ePub2 if you want to support older devices) version and convert to mobi/kindle. This way, you get to distribute for most platforms. You can have nice typography, good table of contents with an attractive cover and chapter headings. You can use Adobe InDesign for this and by adding Amazon’s free _KindleGen_ into your toolset, you get the Kindle version too.

- If the content needs lots of illustrations, embedded in the text, with specific layout requirements (such as double page spreads, or full screen images), then you have to decide between ~~iBooks Author (simple to use free software)~~, that will only deliver to the Apple devices — or a fixed-layout ePub that has limited support on devices other than the Apple tablets, but can (with limitations) be converted to the Kindle KF8 format (for Kindle Fire). You may need to consider your existing workflow and ‘in house’ skills when making this choice. The fixed-layout ePub3 (rather than the ~~iBooks Author iBook~~) is likely to be the best choice if you are publishing to print as well as eBook from the same (InDesign) file.

- If there is a need to add significant amounts of multimedia, interactivity and even quizzes or multiple choice questions, then iBooks Author may be your best option. In a later chapter I will be looking at APP solutions such as Mag+, and HTML5/CSS/javascript frameworks, but APPs are very much tied to their target platform. Please note also that vendors such as Apple may not accept ‘book APPs’ unless they can show a significant reason to be outside the iBooks environment.

## A summary of decisions to be made

OK, let's now try to build a list of the choices
 
### The Overview Choice

- Re-flowable or Fixed layout?

- Which platform? or

- Multi-platform?

- Backlist or fresh build?

- Print first? / Digital First?

### Book / eBook

- From the same file?

- Commit at print stage

- Fork eBook version?

- The differences?

### Page size

- Fix spread or allow single portrait pages?

- Proportion as tablet format?

- Cover size?

### Fonts

- Use Typekit?

- Choose iOS fonts?

- Always embed

- Fine adjust: Tracking and kerning is allowed

### Page Margins

- As in book, but if portrait single pages allowed then match left/right.

- Adjust top / bottom margins in eBook fork?

### Table of Contents

- Logical table of contents

- On page table of contents

- Both built with InDesign

- Can be different

- If line break in heading; include a space

### Index

- Can be interactive in eBook but:

- May need reworking if using InDesign

- Can be removed in the eBook fork

- Page references not chapter / section references

- Style numbers to be interactive visible

- built-in search may replace index

### Footnotes

- Can be left as footnotes in fixed-layout ePub (or even Kindle)

- Can be endnotes and then interactive but post edit required

- Can be popups in re-flowable ePub

- Can be side notes if margins allow

- avoid _ibid_ when popup

### Headers/Footers

- Not relevant to re-flowable ePub

- In the fixed-layout ePub and if single portrait view is to be allowed then keep horizontally centred on the single page, otherwise it keeps flipping side-to-side, when moving through the pages.

- Page numbers (on the page) may not match TOC when converting to landscape fixed-layout

### Images

- Anchor if considering re-flowable eBook (good practice anyway)

- Maintain link (don’t embed in InDesign by pasting)

- Images may bleed (for print) - this is OK for fixed-layout but **not** if you intend to base on portrait page layout.

- If creating for re-flowable remove bleed

- Don’t reduce resolution for eBook until export time

### Images / interactive

- Small images can be made to enlarge

- In reflowable this is automatic so be sure to place an image larger than required on the page

- In fixed layout, javascript is used (InDesign does this but extra work needed beyond print)

- Image needs to be large enough for enlargement to full screen

- Use layers in InDesign to hold larger versions

- Only appropriate in landscape ePub although can be in portrait with care

### Images / captions

- Captions can come from metadata (good practise)

- Captions should be part of group if anchoring

- If allowing portrait single pages, don’t put captions on opposite page in spread (unless text indicates this eg ‘see previous page’)

- Caption can be part of interactive enlargement (with extra work)

### Tables

- do not deliver as rotated page

- Can be set across spread but not if allowing single portrait pages

- Complex tables can be added as long HTML page but requires more work

### Post Editing

- Stylesheet can be added for further control of specific elements

- Other edits to ePub package are possible but *roundtrip* to InDesign may be broken by this

### Post Editing - Front matter

- If landscape is the intent, remove blanks pages and half title

- Optionally add cover image as frontispiece

### InDesign recommendations

- Use book panel and divide by chapter

- Keep cover image separate (as jpeg)

- Manage styles without over~rides

### Checking the ePub

- Check validation with ePubcheck

- ePub3 Fixed layout should work on Apple iBooks (MacOS and iOS)

- Adobe Digital Editions 4.5

- Readium in Google Chrome

### Conversion to Kindle

- ePub3 Fixed layout can be converted

- Only usable on Kindle tablets (Fire)

- Some features won’t work so needs checking carefully

### Conversion to Apple Multi-touch book

- content from print ready InDesign to iBooks Author

- export each chapter as IDML

- Import to iBooks Author

- Different format but media rich

- new type of structure; different from print

[^1]: Converting a re-flowable ePub to the mobi format for the Amazon Kindle is more successful than the fixed-layout format.