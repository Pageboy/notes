---
date: 2025-02-16
updated: 2025-02-24
title: Preflight and Package for Print
tags:
  - indesign
---


## Introduction

At some point during our workflow and design process we want to send something to the proof printer. Normally the best approach to this is to output to PDF from InDesign and then print from this file.

Ultimately we will need the high quality PDF to send to the printer. We will also need to ‘package’ the InDesign work and include in this package the ‘print ready’ PDF.

## Preflight

We use preflight to check that there are no errors in the InDesign file(s). We want to make sure that:

- There are are no missing dependencies (fonts, images, linked texts)
- All images are CMYK
- All images are at least 250dpi (ideally 300dpi) - DPI = dots per inch
- Images are not resized un-proportionally
- there are are no style overrides (we want to avoid this if possible)

## Preflight profile and checks

### Setting up a profile

Go to Window/Output/Preflight to display the Preflight dialogue box.

Select Define Profiles from the context menu

On the left list of categories, you may see some existing profiles. You need to create a new one and open all the triangles that point to the right that have either a dash or a tick along side them. This opens the topic and reveals its contents:

![See the preflight panel](../../media/ID2package/image1.png)

Starting at the top we will go through the options and explain them.

![Choose a preflight profile or create a new one](../../media/ID2package/image2.png)

- Links
- We need to be sure that the InDesign document can find all linked files.
- Colour
- Colour spaces need to be in CMYK for print
- Images
- Resolution - we need at least 250dpi
- Non-proportional scaling - don’t distort images
- Text
- Overset text
- You may spot a red + sign bottom right of a text box.
- This indicates overset text.
- Font types not allowed
- Type scaling
- Minimum type size

![Preflight can check a number of aspects of the file.](../../media/ID2package/image3.png)

Look through the digital profile and check you understand the selections relevant to this preflight check.

![This panel now shows the errors](../../media/ID2package/image4.png)
 
### Using the preflight profile to check your file

- Display the Preflight panel (Select Window/Output/Preflight).
- Select the correct profile for checking this file. (Print)
- With the profile selected, InDesign displays any errors in the Info box of the Preflight panel.

![Load a preflight profile](../media/Screenshot%202017-12-08%2012.57.18.png)

**Note:** [You can download the configured Preflight Profile][ed212a6e] that I created for you here; once downloaded you can load into InDesign from the Preflight Panel > Define Profiles.

[ed212a6e]: /resources/ShakepeareBook.idpp "Grab this Preflight Profile"

You should correct the errors and recheck the file.

## Creating print ready PDFs

First make sure that there are no preflight errors.

In Indesign go to File>Export>PDF

![Settings for the PDF](../../media/ID2package/image5.png)

## The PDF options

Make sure you have selected PDF for print and not interactive.

Under Marks and Bleeds, select crop marks and use the Document Bleed settings.

### What is the slug?

If your PDF needs it, you might wish to add some notes outside the page but within the print area of the PDF. A slug can be added on any, or all sides of the page.

If you are working on the cover, you may want to add fold marks that align with the spine or even the flaps if your cover includes those. The fold marks must be within the slug but outside the document area.

Once you have the correct settings, use ‘Save Preset’ and give these settings a name.

![The package panel shows errors. There are none in this file.](../../media/ID2package/image1.jpeg)

## Creating the Package from InDesign

For your assignments you need to create a package from InDesign. This process creates a folder with all of the assets (linked files), fonts, and the print ready PDF with the created preset.

To create the package go to File>Package and go through the settings, making sure that you include the print ready PDF. This should be created from the preset that you previously saved.

![Define an Adobe PDF Preset](../media/Screenshot%202017-12-08%2011.59.40.png)

**Note:** You can create the `Adobe PDF preset` before you create the package, so that it is available when reach that point in the package creation dialogue. To create the Adobe PDF preset go to the File menu and find Adobe PDF presets > Define. [Alternatively you can download the one I have created here][2066b844].

[2066b844]: /resources/ShakespearePlay.joboptions "Grab this PDF profile before you create the package"

### Final Steps for creating the InDesign Package

When you create the package you will asked to add some information to an `instructions.txt` file

![The package folder will include these items. Select the PDF preset previously saved. ](../../media/ID2package/image6.png)

![The instructions file will include the printer details.](../../media/ID2package/image7.png)

You should add your name to the appropriate field, and add the extent, size and colour in the blank fields at the bottom as in this image. You may need to edit this text file since this dialogue box is rather limited in space given. You will find the text file ‘instructions.txt’ (unless you renamed), in the package folder.

> [!important] 
> It is important that you get an extent (number of pages) that is even and divisible by 16 or possibly 8 for this project. In a real project, the printer would advise about the working requirements; in other words, you would normally discuss this with the printer.

Don’t forget to count the total number of pages rather than just observe the page numbers.

> Be very careful to count all pages from the half-title to the end. Add blanks if necessary but always end the InDesign file with a left (recto) page.

## Creating the Package from an InDesign Book

If you are using the book panel to combine chapters then the package creation happens from the context menu of the `book panel`. You can only select 'package Book for Print' when you have no InDesign file selected within hte book panel itself.