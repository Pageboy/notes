---
tags:
  - css
  - html
  - github
  - vscode
date: 2025-02-16
updated: 2025-02-25
published: true
---


We are using GitHub pages to host a web site for the Shakespeare play. This page explains what we are going to do to get started.

## You will need VS Code software

You will only need the application called _VS Code_ and [this free software is available for your platform here][deb319f2].

  [deb319f2]: https://code.visualstudio.com/download "Grab VS code"

### VSCode Extensions

You need 3 extensions to help with this work.

- Live server
- Prettier
- Github Pull Requests


## Now we need to create the Github repository

Here are the steps:

[Create a Github Account][8c08ca4b] (if you do not already have one) and login to the account.

The final URL of your web site will include your username so be careful when choosing this name.

Here is an example:

> Let's say your username is *unicorn*, then the URL of your web site will be `unicorn.github.io` . Your username may also be referred to as the owner name of your account.

If you already have an account then login at [github.com](https://github.com)

  [8c08ca4b]: https://github.com "Go to GitHub and create and account or login if you already have one"

Now go to this page (put this into the URL box): https://github.com/publisha/shakespeareplay

You will see the green button _Use this Template_

![[templategrab.png]]

Use the template link to receive the repository in your own github account. Make sure that you choose the `Public` option. You will be asked to name the repository.

You now need to name the repository as follows:

It should be formed from your username and I will use the example from above...

The name of the repository when *unicorn* is the username would be `unicorn.github.io`.

![[reponame.jpg]]

## What's inside the repository?

When you download this repository, you will find a variety of files, but the important ones are inside the **docs** folder:

- index.html - this will become the home page for your play. This page will have the cover image.
- styles.css -  this is where you define the styles for the elements in the play. This is inside a folder called `css`.

You can also have a look at the sample scene inside the **sampleScene** folder.

## Editing the home page

Now that we are set up on GitHub, we need to start editing our web site offline, so we now need to **clone** the repository onto to our computer; this involves using vscode that you should now have available from the earlier step.

Go back to the `code` list and touch the green button, then copy the link.

![[getthecode.png]]

### Vscode

Open vscode and click the top left icon. This will then take you to an empty page like this.

![[clone.png]]

When you select `clone` you will need to paste the previously copied link into the box. The code will arrive from GitHub and you need to select a project folder where you would like it to go. Once done then open the window.

We can now use *vscode* to edit the HTML (index.html)  and the CSS (css/styles.css).

## Ok, so what do I do now?

You should now read the help document here, that explains how to generate the HTML files from InDesign.

[From InDesign to HTML and CSS](From%20InDesign%20to%20HTML%20and%20CSS.md)

### Here are the basic steps

- Open InDesign and find your final version of the play (**only the play - not the Introduction**)
- Make any corrections that you like (consider the comments from the previous assignment)
- If you created any new styles you will need to go to the style panel and configure the _Export Tags_ feature, making sure that each style will export with an HTML tag.
- As stated above - read the help document that I have provided
- Follow those instructions to create the interactive table of contents.
- Export your play InDesign document with settings in the instructions.
- You will find that you have now got a new file saved wherever your InDesign file was saved. You can drag this file into the `docs` folder of your working copy of the repo that you have open in Visual Studio Code (vscode). This file should be renamed `play.html` and will replace the existing placeholder file.

> **Note:** if you included images in your play, you will need more work to get those into the appropriate location.

## The Play

In VS Code it will look similar to this screen grab  
![[yourexportedplay.png]]

- Open the _play.html_ file that is inside the docs folder (that you have from your repository) with **VS Code**
- Now edit the _style.css_ file (again inside the docs folder) to style each of the elements in the play
- Review in a web browser
- Validate the HTML file here: https://html5.validator.nu
- Validate the CSS file here: https://jigsaw.w3.org/css-validator/

## The home page cover
- You now need the cover image from the book.
- You can open the PDF of the cover in Photoshop and crop down to the front of the cover. In other words, remove the back and spine.
- The cover image needs to be 1400 pixels wide, because we need this later for the eBook.
- save this image as a JPEG in the **images** folder within the **docs** folder in your repository that you downloaded from GitHub.
- Now edit the index.html file and put the file name of the image where instructed in the markup. Also edit the ALT tag text.
- When you view this `index.html` file the image will be very large, so you must edit the styles.css file to change the width of the image.
- when viewed in a browser, this image will be a link to the play.
- check that the link functions correctly.

## Making the web site work
You can look at the web pages in the web browser by right clicking over the file and selecting _Reveal in Finder_ and then double click the HTML file to open in your default browser. There is an extension for VS Code called _Open Browser Preview_ which can make this easier.

**When you are happy** with the look of these web pages then you can:
- Upload these new versions of these files to your GitHub repository
- You can do this by using the VS Code.
- click the 3rd icon from the top left
- write a message in the commit box (what did you change)
- Click commit
- Click the synch button

Your web site will be updated (it could take a few minutes)

## Back to GitHub

Now we need make the web site live at [github.com][448988fc]

  [448988fc]: https://www.github.com "Login at Github"

Go there in your browser and login with the credentials that you put in before and find the repository that you have previously renamed.

- Under GitHub Pages choose the **docs folder** for the source

![[choose_docsfolder.png]]

- Your web page for the play will be live!
- When you have finished and are ready then post the URL of your site to the Moodle assignment location.

## Summary

Ok, so I know this seems complicated. Let me write out a simple list with the steps. Make this into a check list and tick them off as you go!

- [Download VS Code](https://code.visualstudio.com/download) and install in **your** Applications folder
- add 3 extensions
- Create an account on [Github.com][fc57320f]
- Grab link on Moodle (week 1) for the GitHub template
- Copy the link next to the Clone button
- In vscode, use the icon bottom right to clone and use the window to paste in the link
- [Read the helper document about getting HTML from InDesign](From%20InDesign%20to%20HTML%20and%20CSS.md)
- Add the files into the local version of the repository and edit the HTML and CSS etc
- Check that the site works (home page is the cover image with link to the play)
- `push` the files to your GitHub repository
- Configure your GitHub repository to use the `docs` folder to deliver the web site
- Note the web address and finish

[fc57320f]: https://www.github.com "Create the account"
