---
date: 2025-02-16
updated: 2025-02-25
tags:
  - epub
  - eBooks
  - indesign
title: Roundtripping InDesign and ePub re-flowable
---

> [!info] 
> You know an _InDesign_ file is never finished, even if you do save it as 'Final version'! 

**Get real.** You are going to want to go back to InDesign and re-export your ePub (reflowable), because someone noticed a typo or a badly captioned photo.

What about all those edits you made to the innards of the ePub file — you unpacked it, you fiddled with the CSS, you got it just right and you even added some fancy javascript. But now my editor wants me to go back to InDesign. It was inevitable. Didn't you know that?

Can we, save ourselves a lot of bother by grabbing all those changes and slip them into the new version?

Here's how with InDesign CC (2014 or above) — yes you gotta get the latest version.

_Frankly_, I am only dealing with re-flowable ePubs from InDesign. **Not** fixed-layout.

### An Outline of this Article

This is how I am organising this article:

1. Summary of the Steps
2. Paying attention to the way you work with InDesign
3. Export tagging
4. Editing the CSS
5. Making your own CSS
6. A BUG in InDesign
7. Adding Javascript

### The Steps

Export your first version of the ePub3 file from InDesign, and use this as your experimental version. I use BBedit on a MAC to delve into the CSS.

You can edit the CSS and then look again at the ePub within your eReader. I use iBooks on the MAC.

Go back to InDesign, if you must, and look carefully at the Export Tagging panel. Do this from the '**Edit all Export Tags**' (see figure 1) from the paragraph context menu. Notice, that you can have more than one class name on any style. Just separate them with a single space.

In the ePub you will edit the CSS, and observe the changes until you are happy with the results.

**Note:** Your objective is to avoid editing the HTML, because this will be replaced when you re-export.

Once you have edited the CSS, then you need to take a copy of the contents of the whole file and save somewhere as your own (something.css).

Experiment with Javascript (if you like) but put all of your code in an external file.

### Back to InDesign

#### Avoid the following

- Do not change tag names in the Export tagging panel.
- Do not add styles and their tags.  

![](../media/Pasted%20image%2020240222152810.png)

Export again, but this time find the CSS section (see Figure 2) and add your CSS file saved previously.

This extra CSS file will be added in the head tag of all XHTML files.

**Bug** Alert... we have a problem though.

**CSS** means **C**ascading Style Sheets. The last loaded rule will overide the previous one. What should happen, is that your own personal version of the CSS file should come **_after_**the one that InDesign builds, so that your changes are then implemented.

![](../media/Pasted%20image%2020240222152851.png)

Presently, the only way to change this, is to use a text editor like BBedit to search and replace throughout all XHTML files. Alternatively, you can simply copy and paste your version of the CSS into the end of the CSS that InDesign builds.

### JavaScript

If you want to use javascript (see previous post) in your ePUB, then you need to gather the code and libraries in seperate files. You can use the technique of adding javascript into the head of the individual XHTML files but _only_ during the experimental phase. What you eventually need is to have all JavaScript code in external files.

![](../media/Pasted%20image%2020240222152908.png)

When you export the ePub, then you can then add these JavaScript files into the mix. Find the JavaScript section in the ePub export panel. See Figure 3.

### Conclusion

Apart from the annoying bug in the current version of InDesign, our objective of getting a roundTrip workflow is possible. We can use our our own CSS and our own JavaScript and add those into the ePub at export time. We can continue to go back to InDesign and make editorial changes, but always get the same results when we export to the ePub.

Here is what my markup looks like in the head tag of each XHTML file:

```html
<head>
<title>dream-2</title>   <script src="script/jquery-1.11.1.min.js" type="text/javascript"></script>   <script src="script/jquery.balancetext.min.js" type="text/javascript"></script>   <script src="script/dream.js" type="text/javascript"></script>   <link href="css/idGeneratedStyles_0.css" rel="stylesheet" type="text/css" />
<link href="css/idGeneratedStyles_2.css" rel="stylesheet" type="text/css" />   <link href="css/dream.css" rel="stylesheet" type="text/css" />   </head>`
```
**Why do I have 2 idGenerated CSS files?**

That's because I am exporting the ePub from the book panel.
