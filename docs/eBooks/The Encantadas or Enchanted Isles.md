## Herman Melville

![Cover image](../../media/encantadas.jpg)

This essay was first published in Putnam's Magazine in 1854. It was collected in The Piazza Tales, Dix & Edwards in 1856.

The Encantadas are actually the Galapagos Islands. There are ten sections that Melville calls 'Sketches'. Some of them refer to individual islands in the group and some sketches cover some general points, such as pirates and castaways.

Each sketch is prefixed with a quotation from Edmund Spenser's Faerie Queene which was published in 1590.


[You can freely download this ebook (ePub 5.5MB)](http://www.pagetoscreen.net/ebook_resources/encantadas.epub)

---
## Technical Stuff

Built in the first instance with InDesign, but a substantial amount of work done in editing the XHTML, CSS and TOC. I used Dreamweaver - yes, Dreamweaver was used to change the CSS and to make global changes to the mark-up created by InDesign.

### Using Dreamweaver as an ePUB editor

Before your use Dreamweaver you have to break open the ePUB file by renaming to a ZIP file and then unpacking it. Here are the steps needed:

Create a new site but ignore all of the server settings; you are working offline.

The site root will be the folder in which all of your files from the ePUB are located.

Configure Dreamweaver to recognise files with the following extensions: .ncx and .opf; these should open in the code view.

You may need to configure the file extension .xhtml as well.

### Delivering styles for the iPad / iBooks

I use 3 stylesheets. One basic one and then a styelsheet for the horizontal / landscape view on the iPad and one for the portrait view on the iPad.

Devices that are based on the Adobe Digital Editions SDK (Sony eReader), ignore the last 2 stylesheets here:

```html
<link href="css/template_ade.css" type="text/css" />

<link media="all and (orientation:portrait)" href="css/template.css" type="text/css" />

<link media="all and (orientation:landscape)" href="css/template_h.css" type="text/css" />
```

### Getting backgrounds on pages

This seems really unreliable on any device but I have managed something. See the last image here. The word Colophon is put into the background of a block which is then positioned fixed. On a web page setting the z-index to be a negative number would normally set this in a layer below. This seems to be ignored in the iBooks render.

Here is the CSS for the block:

```css
div#backdecor {
	display:block;
	font-size: 16em;
	position: fixed;
	top: 0px;
	left: 0px;
	-webkit-transform:rotate(10deg);
	z-index:-12;
	color: #EBF5F8;
	overflow-x:hidden;
	-webkit-opacity:.5;
}