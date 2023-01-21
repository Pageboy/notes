# Week 6
## eBook intro

### Steps

> All depends on how much you changed the play file  

* Go back to the print version with book panel
	* but if you added images in the play then you may need to us e that version
	* if you only added the images in the HTML version, then you still have this extra work to do in InDesign
* We do need 6 images in the play
* We will use the `Articles` panel again
* The TOC does not need to be included but must be in the intro as before from the print version
* we will leave the on-page version out in the articles panel

Note, you can go right back to the original book panel with the 2 files or use the new play if you added the 6 images in there.

### Presentation?

Much of this is a recap on the varois things learnt whai creating the HTML web page for the play. Essentially we look at the CSS equivelants of the InDesign paragraph and character styles.

There is a longer one on Moodle - watch at your leisure

[eBook Typography](https://www.publisha.org/keynotes/eBookTypography/)

* Then demonstrate Dream play
* From [book panel](https://www.publisha.org/pages/InDesignBookPanel/)
* Articles additions
* Export options
* Export tagging
* Toc on page in intro should not export

Remember to add in the CSS file I made available on moodle

[Here is the CSS file to add](https://gist.github.com/Pageboy/731b9b7ad8e42c324dc75528f159ad98).

All images must be anchored and use the object style _scene-image_
The export tagging for this must create a figure
Style source is the intro so any changes must be included in that file (use load all text styles but also the object styles)
Check the table of contents

The first version will be rubbish so we need to go through the **export tagging** for the front matter. 

### Object Export Options
For each page that has an unthreaded object (such as the title page) , we need to:

1. Make sure all objects are in one group
2. Select object export options from the object menu and then
3. Select an appropriate ePub type and 

![[Screenshot 2022-03-05 at 16.10.08.png]]

### Issues
#### Apple Books

Apple Books has been updated later than the version on the iMacs on campus. One very important difference is the way that the table of contents is displayed. This now looks the same as the ios version with the cover shown on the left side of the page when in landcape mode.

#### Problems with the original template

- The original template (that we used for the play originally) has lots of un-named articles in the articles panel. This is a mistake **Please remove** all of these articles by selecting and click the dustbin icon.

- In the export tagging for the various object styles some CSS class names have the same names. This could cause a conflict and (in a way) this is an error in the template, however, we are not actually using all of the object styles.