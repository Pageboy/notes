---
hide:
 - navigation
tags:
 - css
 - multiplatorm
 - digitalproduct
 - html
---

> We are using GitHub pages to host a web site for the Shakespeare play. This page explains how to add video and audio to the web page.

In this second document we explore the ways to add multimedia content to the Shakespeare play web page.

## Video

There are 2 ways to add video to the HTML and whichever of these 2 ways, you will also need to add some CSS to style the way it is presented.

We will start with the easiest way even though this will have certain disadvantages.

### Embedding from Youtube

First of all you need to find an appropriate YouTube video that will make sense somewhere in your play. Go ahead and search YouTube for your play and see if you can locate an extract of a performance or even an explanation of the plot.

Once you have found something suitable, look for the `Share` link.

Find the Share link

![[sharefromyoutube1.png]]

Now what you need is the `Embed` option like this:

Share the embed

![[shareyoutube2.png]]

You will notice that you can, optionally start the video some way in thus removing any introductions or advertisements.

The copy button will take the code and put into your computer memory so that you can place into the HTML. Here is the example of the embed code:

```html
<iframe width="560" height="315" src="https://www.youtube.com/embed/XL2-MbVniR4?start=6" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
```

> **Note:** It turns out that the attribute `frameborder="0"` is obselete and will break validation when you use the online validator. You can remove `frameborder="0" ` from the code.


You can place this code into somewhere in your play `HTML`.

As you can see the `iframe` has a width and height set and this will cause some problems if you want to make sure that your site is responsive, because the size of the video will always be fixed. To get round this, we need to wrap the `iframe` code inside a `div` and then some CSS to control the size of the video.

The screencast at the end of this section will provide a detailed explanation of how to add the markup but here is the code that you need using the youtube example above.

#### The HTML markup

```html
<div class="video-box">
<iframe width="560" height="315" src="https://www.youtube.com/embed/XL2-MbVniR4?start=6" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>
```

#### The CSS

```css
.video-box {
	position: relative;
	padding-bottom: 56.25%;
	padding-top: 30px;
	height: 0;
	overflow: hidden;
	margin-bottom: 12px;
}

.video-box iframe {
	position: absolute;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
}
```


So if you add this `CSS` to your own CSS file for the play, then the video will resize automatically for different window sizes.

```html
<div class="video-box">
<iframe width="560" height="315" src="https://www.youtube.com/embed/LoPq13JnaVg?rel=0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>
```

### Adding Video by file

Another way to add video to your page is to link to an actual file (probably an `MP4`), but then you need to have access to the file.

#### How to get video to use on your web site.

It is possible to actually download some videos from YouTube, but to do this you will need to install software.

**If you have a MAC** you can download VIDL from here: [https://omz-software.com/vidl/][9ed64ce1]

  [9ed64ce1]: https://omz-software.com/vidl/ "Grab vidl"

It is straightforward and all you need is to grab the share link from YouTube.

For the Windows/PC you can try 4kdownload from here:  [https://www.4kdownload.com][64074bd1]

  [64074bd1]: https://www.4kdownload.com "Grab 4kdownload"

You may not be able to download any video, since it may be protected.

You may be able to find other videos for your play not on YouTube, however even the Folger Shakespeare library hosts their videos on YouTube, so the `embed` method may be preferable in any case.

#### Adding video code to HTML

So, how do we attach a video file to the HTML?

The `video` tag in HTML is similar to the `img` tag, so first of all you will need to add the video file itself to your project space. I suggest that you create a folder named _media_ and put the mp4 file inside that folder. Read about the video tag on [w3 schools][932911ab].

  [932911ab]: https://www.w3schools.com/tags/tag_video.asp "w3Schools"

So here is a sample:

```html
<video controls>
	<source src="assets/msnd01.mp4" type="video/mp4">
	Your browser does not support the video tag.
</video>
```

If you compare to the information you may find elsewhere you will notice 2 things:

1. There are no dimensions for the video
1. There is only one source

We don't want to use  a width and height for the video because it is better to control this with `CSS` so we can keep the responsive qualities of our web page. We simply need to include the following `CSS`:

```css
video {
  width:100%;
}
```

You will see that w3 Schools recommends using an alternative video format for other browsers that do not support `mp4`. It used to be the case that _Google Chrome_ preferred to use the `OGG` format and so this would be required as well. I have found that this is not the case with recent versions of Chrome. I suggest that you use mp4 and then text on all of your own browsers. There are free video converters available that will convert to a variety of formats.

When you test your page in different browsers you will observe that the controls have a different style; Safari looks different from Chrome and different from Microsoft Edge.

#### Poster Image

Before the video plays there is a static image in its place. By default, this is the first frame of the video. If your video starts with a blank or black frame you might want to create an image to take this place. You can then add this attribute to the tag in HTML like this:

```html
<video controls poster="/images/theseus.png">
	<source src="assets/msnd01.mp4" type="video/mp4">
	Your browser does not support the video tag.
</video>
```

Make sure that the poster image is in the same proportions as the video.

### Editing the video

If you have downloaded a video that needs some editing then you will need software to do this. If you are fortunate in having access to Adobe Creative cloud then you can use Premiere Rush or Premiere Pro.

If you have a MAC you can use iMovie or even just **Apple Quicktime** player, if you just want to trim the video (remove some frames at the beginning or end).

You could also try the open source software [ShotCut][a7e4ded6]. This is available for MAC and PC.

  [a7e4ded6]: https://shotcut.org/download/ "Get ShotCut here for MAC or PC"

```html
<div class="video-box">
<iframe width="560" height="315" src="https://www.youtube.com/embed/T-tNjnoXFFQ?rel=0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</div>
```


## Audio

Adding audio to your web page is very similar to the way that you add the video using the file method. First you need to find audio sources and I post here a few possible places that you can try.

One thing to be aware of though; often you will be downloading the full version of the play as an audio file. You will need to edit or extract a small clip to use on the web page. **Do not attempt to use the complete performance on your web site.**

### Editing Audio

As mentioned above, you will need to use an extract rather than a complete recording and to do this, you need to use an audio editor.

If you have access to Adobe Creative Cloud then you _can_ use Audition. but this is really quite complex for the simple task of extracting a clip. A better solution is to download the free software _Audacity_ from [here][8b45ed15].

  [8b45ed15]: https://www.audacityteam.org "Get audacity"

Apparently, Audacity does not officially support MAC OS Catalina, however the workaround [is available here][9b8e4fd5].

  [9b8e4fd5]: https://forum.audacityteam.org/viewtopic.php?t=107162 "Catalina workaraound"

Editing audio in Audacity

![[audacity.png]]

Using `Audacity` is fairly simple, but if you are trying to extract a short clip from a very long file, just select the clip, copy - and then make a new file and past this in.

### File types

The web supports a variety of audio file types, but the one that can be guaranteed to work on all browsers is the `mp3`. So save or export to this format.

### Adding the audio to your web page

The audio tag in HTML is very similar to the video tag described above. Do explore on the [W3Schools web site][932f17fc].

  [932f17fc]: https://www.w3schools.com/tags/tag_audio.asp "w3 schools web site"

Here is an example:

```html
<audio controls>
	<source src="assets/act1scene1_clip01.mp3" type="audio/mpeg">
	Your browser does not support the audio tag.
</audio>
```
Different browsers will display the controller for the audio with different styles.

#### Styles for the Audio

You may wish to make sure that the controller for audio displays as wide as possible, so that the user can easily use the `scubber` to move through the sound. Doing this is simply a matter of useing the following in your CSS:

```css
audio {
  width:100%;
}
```

Here is the audio controller

![[audioninplay.png]]

There are other ways to deliver audio to the web page but these invlove using javascript. We haven't covered this in class, so I don't expect you to use these techniques, however, here is an example of how to use your own buttons instead of the standard controller as shown above:

```html
<audio id="act1scene1">
  <source src="assets/act1scene1_clip01.mp3" type="audio/mpeg">
  Your browser does not support the audio tag.
</audio>

<button class="play" onclick="document.getElementById('act1scene1').play()">Play Speech</button>
<button class="pause" onclick="document.getElementById('act1scene1').pause()">Pause Speech</button>
<button class="stop" onclick="document.getElementById('act1scene1').pause(); document.getElementById('act1scene1').currentTime = 0;">Stop Speech</button>
```
Then to make the buttons look cool we can use something like"

```css
button {
float:right;
display:inline-block;
padding:0.35em 1.2em;
border:1px solid #FFFFFF;
margin:0 0.3em 0.3em 0;
border-radius:0.8em;
box-sizing: border-box;
text-decoration:none;
font-family:'Roboto',sans-serif;
font-weight:300;
color:#FFFFFF;
text-align:center;
}
button.pause {
  background: orange;
}
button.play {
  background: green;
}
button.stop {
  background: red;
}
button:hover{
background-color:black;
color:white;
}
```

Try it!

Here are the audio buttons coloured

![[audiobuttons.png]]

> **Note**: The above CSS will not provide a good result on narrow screens (mobile) so you should add the following to stop the float when the window is narrow.

```css
@media only screen and (max-width: 720px) {
  button {
    float:none;
  }
}
```

This will put the buttons across the page rather than to the right.

## Possible sources

Of course you may want to record your own audio by reading a speech from your Shakespeare play! That would be great. However, if you want to look for recordings of your play try these:

### LibraVox

These are amateur recordings by volunteers and there are several versions to try: [https://librivox.org][a285241f]

  [a285241f]: librivox.org "Go to Libravox"

### Shake5

[This available here](https://moonpub.net/shake5/).

I don't know why it is called that, but you may find your play here. Finding the actual file for download here is a bit tricky, but just explore and find the url of the actual `mp3` file.

Here you see I have found the actual MP3 file for Act 1 Scene 2

![[shakes5.png]]

Once you have located the file you can open in browser and then `save as source`.

## Music

I should mention finally that as another option you could add music to enhance the web page, but there are some issues to consider.

You can only have one music file playing on the web page for the play. Only if you split the HTML into several sections (separate HTML files) can you incorporate different music for different Acts.

Don't play the audio automatically; give the user the opportunity to play the music if they are so inclined.

To this end, you will need to provide audio buttons (use the method above for the `button` code) and style this block of buttons so that they display in a fixed position as the page scrolls. It may be desirable to add these buttons to the menu at the top of the screen if yours is set to be fixed.


