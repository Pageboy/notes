# From InDesign to HTML
## Steps

We need the play file not the book.

### Images

If you want you can add the images that you need for the play (6 required) with InDesign, being sure to anchor them. You can wait and add the images in the HTML later, but putting them into InDesign is easier and you will also need for the eBook later.

### TOC

Create toc for the play at the start of the file. Put in a new page with a text block object  - use export tagging to make this the _nav_. Page numbers not needed but the toc styles need to be nested bulleted lists.

### Use articles panel

You should have 3 text blocks; the toc (in an object called _nav_), a Dramatis Personae (in an object called _dramatis) and the play in an object labelled _play_. 

These 3 objects need to go into the articles panel for export.

![](From%20InDesign%20to%20HTML/Screenshot%202022-02-08%20at%2016.13.30.png)

### Export Tagging

We need to make sure that all styles (character, paragraph, object and table) export with the correct HTML tag names and class labels. `Edit All Export Tags` can be found in the paragraph style pane. The template will have most of these already but you may need to add.

![](From%20InDesign%20to%20HTML/Screenshot%202022-02-08%20at%2015.59.26.png)

You only need to use standard tags and semantic class names. No need to worry about styles that we don’t use. 

### Issues

	* If you used a table for the Dramatis Personae
		* Tables can be styled in CSS
		* but advice to change to text
	* If you have the play character on the same line as the first line of the speech
		* Will need some extra CSS because the tab will disappear

[Link to article: InDesign to HTML and CSS](https://www.publisha.org/pages/InDesign_to_HTML/)


#multiplatform

