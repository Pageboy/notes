The fixed-layout format ePUB3 format provides a way to deliver every single page in your print book laid out just as it was in the print version.

This fixed-layout format can be considered almost the same as an interactive PDF, however, as you will see, the ePUB can have much more interactivity and, you, the designer can control the way the eBook is displayed.

## Features

- There is no way to include footnotes as popups (they will simply be at the bottom of the page - as in your print version)
- All items will be delivered as they appear, including the master page items.
- Post editing the CSS is almost impossible, because every single word on the page is positioned with the CSS, so you dare not make any adjustments.

## InDesign export to ePUB (fixed layout)

The instructions for this are very limited, but we should first explain that the fixed-layout ePUB is formed from many XHTML files – one for every single page that you see in the InDesign view. Whichever method you use for this output, you need to become aware of the individual pages (how they begin and end, if there are orphans and widows, and what your master page items look like. Effectively, you are now designing as if for print.

## One Page at Time
Go through all the pages, and satisfy yourself that each page is how you want it to be. You can make adjustments to fix widows and orphans. You should be certain that the master page items display correctly.
+ Items can bleed off the page.

Images may be anchored in the text, although technically, for this method you do not need images to be anchored. Since this is all about trying to use the same file for these different techniques, we should have anchored images!

Having had a good look at our InDesign book and files, we only have one matter to address – do we want the table of contents on the page or just as a logical TOC? If the TOC is on the page, then it will be on the page in the ePUB (fixed layout). If you don’t want this, you need to move it on to the paste board and delete those pages – see what I mean about destructive!

You will already be familiar with the panel that appears when you export the ePUB, only this time the features are very limited.

## The General Section

[![Export to Fixed-Layout ePub - The general Section](/images/2017/03/id2fixed_recipes/image2.png)](/images/2017/03/id2fixed_recipes/image2.png)

In the General panel you will need to select the cover image and the table of contents as a Multi Level Navigation from your saved TOC in InDesign.

There are Spread Layout options that will control the way the spread is formed. You can even join the pages as a landscape form. On the other hand, you may simply base the spreads on your layout (as if for print). You can also choose to Disable the Spreads so that only one page will show at a time.

## The Conversion Settings

In this panel we can decide how the export process will convert the graphics in your book.

The other panels that you can select include the following:

The CSS panel allows you to add your own CSS, however there are few adjustments that we are likely to need to make. Likewise the javascript panel provides a chance to add javascript.

We will need to add Metadata in the appropriate panel, before we proceed.

## How Does our Fixed-Layout ePUB look?

You will see pages exactly as you had in the InDesign. Is this successful?
[![Sample spread eBook](/images/2017/03/id2fixed_recipes/image3.png)](/images/2017/03/id2fixed_recipes/image3.png)

Certainly. If this is what you wanted, then we can surely say that we have a good fixed-layout eBook. But take a look at the bottom of the right hand page.

Here we see the problem with our footnotes. They are appearing as they did in the print version and we have no possibility of interactive popup notes unless we edit the inside components of the ePub package. Now have a look at the XHTML of one page in the eBook.

If you look carefully, you will see that every word on the page is wrapped in a span tag with a position set through an inline style rule. This is the way that InDesign has exported the content and it works to precisely position all content on the page. The problem comes when you want to make any edits after-export. We have little hope of making any changes to the CSS other than possibly adding a background colour to the pages.

[![Look at the complexity of the code in the ePub HTML ](/images/2017/03/id2fixed_recipes/image4.png)](/images/2017/03/id2fixed_recipes/image4.png)

So back to the footnotes then; the best approach for these is to convert them to endnotes (or side notes) and this is possible using one of the scripts available from [Peter Kahrel’s web site][b4af0e20].

[b4af0e20]: http://www.kahrel.plus.com/indesignscripts.html "You can download many InDesign scripts from here"

## Layout Changes

The first impressions for the fixed-Layout eBook may be disappointing and you may want to make some changes before we move on. Here are a few suggestions:

## Page numbers and Headers

You should include page numbers by using the master pages. You may also want to use a running header or at the least the title and author of the book in the header. Again, use the master pages for this. Remember, master page items are included in the fixed-layout eBook. You might also consider adding colour into the master pages to give impact.

## Page Layout

The example recipe book has single pages in portrait mode; we are not using a double page spread. By default, then, our fixed-layout eBook will be a single pages. We can change this in a number of ways; we can **go back to the document setup in InDesign and set for facing pages**. This will give us the option of turning the portrait mode into a landscape, side-by-side. When we export to the fixed layout we can choose convert Spread To Landscape Page

[![Choose the Covert to Landscape Page](/images/2017/03/id2fixed_recipes/image1.jpeg)](/images/2017/03/id2fixed_recipes/image1.jpeg)

## Font-size

You may want to increase the font size overall, since users of the fixed-layout form cannot adjust the text size. Hopefully, you have used paragraph styles in such a way as to be able to make adjustments easily.

## Picture size and position

Images do not need to be anchored for the fixed layout eBook, so you can release the images and then move them or enlarge them. You are free to take images out to the bleed. There is no automatic enlargement on double-click in the fixed layout eBook, so you may need to move away from the tiny thumbnail image idea; on the other hand we are going to look at a way to get the images to enlarge on click (more on this later).

[![We have some control as to how the video plays on the page](/images/2017/03/id2fixed_recipes/image5.png)](/images/2017/03/id2fixed_recipes/image5.png)

## Multimedia

We can add audio and video into our eBook. We can also add buttons that control the playing of the multimedia. We can even get audio to play when we reach a particular page.

We can opt to see the standard controllers for audio or we can build our own buttons and then hide the audios behind another object. Audio and video are placed on the page in the same way that we place images.

### Too Big?

It is worth pointing out that the video mentioned above will add 470MB to the eBook, so we should consider this carefully before add the complete video. There is software available to compress video down to a smaller file size and you should take advantage of these. [Milo Video Converter for the MAC][b734772c] is useful for this.

[b734772c]: http://www.mirovideoconverter.com "A good app for converting video"

### Placing the Video

We place video much as we do images. Once placed though, we can then view the settings through the Media Viewer panel.

With the media view we can control the preview image and decide on how to display the controller.

### Adding Audio

Audio can be added in much the same way as the video, but once again we need to be aware that probably only want small snippets of audio in context. The audio will initially be placed as a small square, and you will need to stretch this out to fill the width of the page, so that the audio controller is as wide as possible.

[![Audio will always stop when we turn the page in the fixed-layout ePub](/images/2017/03/id2fixed_recipes/image6.png)](/images/2017/03/id2fixed_recipes/image6.png)

When you create the fixed-layout ePUB from InDesign then the page content will be exactly as you see it in InDesign. With audio you will need to make the audio object fill the frame that you have stretched across the page


We can add audio or video as we can for the reflowable ePUB, but both audio and video will stop playing on page turn on both the MAC and iPad.


### Ambient Sound

It is possible to add audio that plays automatically when a page is opened. The audio will play as long as one XHTML file is open. In other words, you can have a different ambient sound for each chapter in a reflowable ePub. In our example Shakespeare play we can add some ambient audio to the start of the Scene. If you plan to create a reflowable eBook then this sound will play for the whole of this scene by placing the audio once. With a fixed-layout eBook the audio will need to be on each page.

To make the ambient sound user friendly there really needs to be some way to turn this off, if the reader prefers not to hear it.

For the ePUB Fixed layout format, Apple have some proprietary extensions that can handle ambient sound in the ePUB, and if you wish to consider this, then please refer to [Apple’s Asset Guide for eBook production][7b08546e].

[7b08546e]: https://help.apple.com/itc/booksassetguide/en.lproj/static.html "Essential reading"

### Audio on Click or Touch

When build a fixed-layout ePUB with InDesign, it is also possible to have audio play when an object is touched or clicked.

The audio object must first be placed on a page, and you will need to hide it by covering with the object itself or another opaque box. If the audio object is off the page (on the pasteboard), then it will not export.

Remember that the audio will stop when the user moves to another page.

## Animation

InDesign does give you some basic controls over the way objects are dynamically drawn on the screen, and by selecting an object and then the Animation panel (under Window>Interactive), you can invoke an event on page load. Here we see that an image is set to drop down from the top of the page when that page is reached.

[![Here we are setting this image to drop down when the page opens](/images/2017/03/id2fixed_recipes/image2.jpeg)](/images/2017/03/id2fixed_recipes/image2.jpeg)

>**Note**. Animation is not supported on anchored objects, so you will need to release any previously anchored images.


The fixed-layout ePub does not automatically provide image enlargement, but you can make this happen by using a larger version of the image and making this animate to the centre of the screen, invoked by making the smaller version into a button.

### Image Enlargement on Click (or touch)

The image itself must large enough to be viewed full screen. If the image is linked (and not embedded) you can copy and paste to a new layer. The advantage of using another layer, is that you can hide this when you need to get access to the under lying layers. Here are the steps:

* Make a new layer above the current one

* Copy the image on your page

* Paste into the new layer

* Resize and position this image where you want it to appear

* With this image selected invoke the animation panel

* Choose an animation (could be simply fade up)

* Make sure to tick `Hide Until Animated`

* Now hide this layer so you can see the image below

* Select this image and make into a button

* Make the action on the button invoke the animation previously created

* Show the hidden layer again

* Select the large version of the image

* In the animation panel, turn off the `On Page Load` event - There should only be `On Button Event` in the events list

* With the image selected make this into a button

* Make the action to 'Show/Hide' and select itself and hide by selecting the eye icon that has a line through it

* Test this now with the ePub Preview window

  

## Creating a Slide Show in InDesign

  

There is no direct way to create a sequence of images in InDesign (as of this writing), but you can use a `multi-state object` and then create a button that will provide the controls to move through the image sequence.

  

The images in the sequence need to be the same size and proportion (approximately) and you can add them to InDesign using the following workflow:

  

Prepare the images so that they are all the same proportion and size (InDesign will crop them to fit if you don't).

  

You may need to consider using a full page for this asset, so go ahead and create a new page or find a blank one. If your print book had blank pages then this is a good solution to keeping the same pages but avoiding blanks in the eBook.

  

Create an empty graphics frame and adjust the size in the correct proportion for your image sequence.

  

You should configure this frame to ‘Fit Content Proportionally’ and turn on ‘Auto Fit’.

  

Now duplicate this frame for the number of images you want in the sequence. Use the Step and Repeat menu found on the Edit menu. The frames should be offset by a small distance.

  

[![The image frames are offset initially, then we can align so that they sit at the same place](/images/2017/03/id2fixed_recipes/image3.jpeg)](/images/2017/03/id2fixed_recipes/image3.jpeg)

  

Use the Place command and select all[^1] of your images and click each frame in turn to populate the frames with the images. They should automatically resize and crop to fit. When placing images you can select more than one and all we be loaded onto your cursor.

  

Use the align toolbar to make the frames sit on top of each other. You need to align horizontally first and then vertically.

  

Use the Object States menu under Window>Interactive and create a new multi-state object while this group is selected. It will automatically add each image into the different states.

  

[![The multi-state object panel](/images/2017/03/id2fixed_recipes/image5.jpeg)](/images/2017/03/id2fixed_recipes/image5.jpeg)

  

Now we need to create buttons to control the sequence as a slide show.

  

The easiest way to create the controls for a slide show / sequence is to add overall a transparent frame over the left and right halves of the image set, and simply make those into buttons that will move the sequence forward or back.

  

## ePUB Interactivity Preview

  

Under the Window>Interactivity menu you will find the EPUB Interactivity Window. With this, you can test your fixed pages (or indeed the whole book) before exporting to the fixed layout ePUB. Not all features can be previewed but certainly the animation, multimedia and interactivity will show as expected.

  

[![We can preview the ePub before we export](/images/2017/03/id2fixed_recipes/image6.jpeg)](/images/2017/03/id2fixed_recipes/image6.jpeg)

  
  

[^1]: Yes, it's true, when you Place, you can select a bunch of images. These will be loaded onto the cursor and can be placed one at a time; in this case, in each empty frame.