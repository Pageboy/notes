## Robert Louis Stevenson

![](../../media/isletcover.jpg)

When I read this short essay by Robert Louis Stevenson, I recognised a man who loved islands, since there are references to different islands that he had either explored or invented.

I have created a few versions of this wonderful essay from RLS, partly from an interest in islands, but also because there are many opportunities to make cross references to other material from RLS himself. I have also travelled to the island described and I have included some photographs within the book.

Back in 2001, I created a Quicktime VR movie and had included this in a PDF version of this eBook. Including this in the ePub version seems impossible for the moment. Even putting a link to the QTVR online is a bit risky because recent versions of Quicktime from Apple no longer supports this format.

[![Memoirs of an Islet - Robert Louis Stevenson & Chris Jennings](http://r.mzstatic.com/images/web/linkmaker/badge_bookstore-lrg.gif)](https://itunes.apple.com/gb/book/memoirs-of-an-islet/id582663546?mt=11&uo=4)

---
## Technical Stuff

> [!failure] 
> Please note that some of these features no longer work in the latest version of **Apple Books**.

### Panoramic Image

Is there a way to display a panoramic image? Yes. Here is how I have delivered this for this version of Memoirs of an Islet. This only works in iBooks on the Apple devices:

The once the image has been patched together from all of the individual components, you then need the long horizontal image as a JPEG. Then you need to put this on an HTML page. In other words you are creating a web page with this image displayed centrally. The image needs to be enclosed in a <div> that is absolutely positioned and content set to scroll horizontally.

```css
.container { 
position:absolute;
top:20%;
width:100%; 
overflow-x:scroll;
-webkit-overflow:hidden; 
-webkit-overflow-scrolling:touch; 
padding:0;margin;0;   height:363px; 
}
```

The image itself is marked up with HTML thus:

``` html
<img src="images/balfourbaypano_large.jpg" style="height:100%;width:3000px;" alt="balfourbay"/> 
```

### Pictures

Images that relate to the text are set to float to the right together with their captions. This is achieved by including the img tag and the caption inside a block element. Only the width of the image is specified in the mark-up, and this is set to 100%. The containing block, however, is styled to be set to 35%. This means that the image and caption will reduce when the width of the display is reduced. This seems to work well in Adobe Digital Editions as well as iBooks.

#### Specifics for iBooks

The iBook interface allows for image enlargement by double tap so there are some things to consider:

- the double tap will display the whole image
- if the image is smaller than 658 x 860 then it will be centred with white space around
- larger than 658 x 860, there will be no cropping, and it will resize to fit but maintaining the proportions of the image
- I guess the trick is to keep an image as large as possible but with the view to overall file size of the ebook. In other words, don't overdo the size; you won't get better quality.
- store the image as big as the iPad screen (careful here... maybe future versions will change!)
- in landscape mode, the image can enlarge to 860pixels wide. It may be larger, in fact for the sake of future developments, maybe 1000pixels width is better

##### There is a strange anomaly with the screen size:

If you make the cover image 658 x 860pixels 72dpi, then you get a good thumbnail for the bookshelf in the iBooks library, and if you double tap when in portrait mode, the cover will enlarge to the full iPad screen (and look gorgeous!), however, if you make the images in the book, this same size, then double tap does not fill the screen with the image; instead you will find some white space left and right or - top and bottom if in portrait orientation, with a portrait image.

#### Shadows on images

Yes, you can get them on the iPad and on Safari with this rule for the img elements:

```css
-webkit-box-shadow:3px 3px 11px #888;
border: 1px solid #888; 
```

### Hyperlinks
With CSS you can style the hyperlinks, as you normally would for a web page, however:

The iPad cannot make any sense of the hover state, but you may want to include it for ADE and the Firefox reader. The default hyperlink style for iBooks, is very low key and I really want to inform the reader that there is more information inside. I have made the hyperlinks display stronger and with a dotted underline. 'Hover' doesn't work on an ereader device but 'active' does. 'Visited' doesn't work. So here is the relevant CSS:

```css
a:link { 
text-decoration: none;
font-weight: bold;
border-bottom: 1px dotted #96CEEB; 
color: #426AC6;
}
```

```css
a:active { 
text-decoration:none;
font-weight:bold;
border-bottom:none; 
background:#96CEEB; 
color:white; 
}
```

#### Cross references

The ePub3 standard allows for non-linear content and this is used to deliver the panoramic image discussed above. But for referencing other material, I have created styled HTML documents and set them to be non-linear in the spine section of the OPF file.

Within the main text, we create a link thus:

```css
<a id="raleigh" href="raleigh.xhtml">an island</a>
```

This takes us to the document _raleigh.xhtml_