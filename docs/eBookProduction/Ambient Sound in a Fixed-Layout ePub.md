**Just for Apple Books**
When we place audio on the page of a fixed-layout eBook, we cannot expect it to continue to play when the page is turned. Each page is a new XHTML document, so audio (or any media) will stop on leaving that page.

If we want to get audio to continue to play as we turn the pages, we need to modify the markup inside the ePub package after we have exported from InDesign[^1].

## Further Details

Books on Apple devices supports this ambient sound feature and we need to add a reference to the iBooks extensions in the HTML tag at the top of the pages that need this audio. We also need to modify the audio tag inside the HTML markup.

We can use InDesign to add the audio file (we can do this on the master pages), but there are some very specific issues to be aware of:

Each HTML page will have the HTML tag thus:

```html
<html xmlns="http://www.w3.org/1999/xhtml" xmlns:epub="http://www.idpf.org/2007/ops">
```

we need this instead:
```html
<html xmlns="http://www.w3.org/1999/xhtml" xmlns:epub="http://www.idpf.org/2007/ops" epub:prefix="ibooks: http://vocabulary.itunes.apple.com/rdf/ibooks/vocabulary-extensions-1.0/">;
```
When we place audio on an InDesign page it will create HTML for audio like this:

```html
<audio id="_idAudio000" controls="controls">
<source src="audio/dreamambient.mp3" type="audio/mpeg" />
</audio>
```
This is perfectly valid but we need this:

```html
<audio epub:type="ibooks:soundtrack" src="audio/dreamambient.mp3"/>
```

You will want to hide the audio somewhere on the InDesign page, by putting it behind an image.

I do hope the screencast explains this.

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/tdZT2DkI8Rk" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

>**Note**: Apple Books on the MAC has a few anomolies; the soundtrack switch does not always display and the audio icon in the menu bar shows even if there id no audio on that page.

[^1]: Always remember that once we edit the HTML inside the book package then we lose the ability to go back to InDesign for further edits