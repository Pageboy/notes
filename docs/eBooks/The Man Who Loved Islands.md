## D. H. Lawrence

![Cover](../../media/lovedislands.jpeg)

This story was written in 1926 but then not published until 1928, after the author's death. The story was published as one of a collection of short stories; _The Woman Who Rode Away and Other Stories,_ Knopf, New York.

This ebook is delivered to you in the ePub format. The epub is optimised for the iPad, but will work equally well on a number of ereaders.

[Download the eBook in ePub format](manlovedislands.epub)

## Technical Stuff

This epub conforms to the epub standard and was validated. The file has been tested on a Sony eReader, on an iPad and an iPhone. The file has also been viewed in Adobe Digital Editions and the Firefox add-on - ePub catalog.

### Some code issues

**Note:** Version 1.2.1 of iBooks makes _page-break-before_ work, but don't use it for header at the top or beginnings of xhtml documents or you will get a blank page.

#### Forcing section headings to start a new page

Very often, you will want to be sure that a heading does not end up at the bottom of the page. You would think that using this CSS rule would do the trick:

`page-break-before:always;`

~~Sorry, but no.~~ While this would certainly force a new page in a print out of the document, it won't work reliably anywhere else. 

Liz Castro, in her book '[ePub: Straight to the Point](http://www.pagetoscreen.net/bookshelf/more/epub_straight_to_the_point/index.html)', suggests using the following:

`display:inline-block;`

For an element that includes the heading and the section that you want to keep together. I have found this to be un-reliable and also a nuisance, because you need to wrap the heading and the first paragraph that follows it in a div. If the paragraph is too long that, this fails also.

There is only one way to be sure that a new page is started, and that is to create a separate XHTML document for each new set of pages. InDesign CS5 does provide ways to do this, so you easily divide up a whole book into chapters. Sections within chapters will also be possible, but handcrafting with markup will not be so easy.

In '_The Man Who Loved Islands_', I did create a separate file for each of the sections; Title page, Introduction, colophon and acknowledgments - as well as one for each of the islands (effectively 'chapters'), but you need to pay special attention to the TOC etc.

#### Specific styles for orientation

The iPhone and iPad have a very clever feature that detects when you are holding it vertically or horizontally. This is really significant for ePub files delivered to the iBooks app on the iPad, because you will get a 2 page layout when seen in landscape mode and one single page in portrait mode. The iBooks app does a good job of giving a different layout, appropriate for the two different modes, but you may want to enhance this, by using different CSS rules depending on the mode. 

##### What doesn't work

In theory you should be able to target these different modes within the CSS file, like this:

```css
@media screen and (orientation:landscape) {
	img {float:none;}
}
@media screen and (orientation:portrait) {
	img {float:left;}
}
```

This will, indeed work for the ePub on the iPad/iPhone, however, if you look at the resulting ePub in Adobe Digital Editions, you won't see any styles at all! ADE will not tolerate such stuff!

**Note:** The Firefox add-on - ePub catalog - does recognise the landscape/portrait difference. You can test this by stretching out the window so that it is wider or narrower and see the change on the title page.

#### So, what did I do?

The solution is a bit more involved, but basically you need 3 copies of your stylesheet, and then inside `<head>` tag for each XHTML document, you will need to put the following:

```html
<link href="template_ade.css" type="text/css" />
<link media="all and (orientation:portrait)" href="template.css" type="text/css" />
<link media="all and (orientation:landscape)" href="template_h.css" type="text/css" />
```

The first css file is loaded by all systems. The second and third are loaded by those devices that understand orientation, and the appropriate css will be loaded when you turn your iPad around. 

#### More details on iBooks

The iBook app on the iPad/iPhone is delivered through the same engine as the Safari browser and, therefore, makes use of the 'webkit' system. You can target certain features of this with special CSS. For example to get shadows on my images:

```css
div.image img {
margin: 0 auto 4px auto;
-webkit-box-shadow:3px 3px 11px #888;
border: 1px solid #888;
```