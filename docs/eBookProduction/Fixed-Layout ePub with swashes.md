> [!summary] 
> I am using InDesign to build a fixed-layout eBook and I want some alternate swashes in the text. 

## Swashes in the text

Although you can add swash alternates to an **opentype** font in InDesign these won’t get pushed into the fixed layout ePub . You might expect to be able to select individual letters within the word and then add CSS through the style ‘export tagging’. Unfortunately this does not seem to work at all in the latest version of InDesign.

![Looks fine in InDesign](../media/Pasted%20image%2020240222154618.png)
Looks fine in InDesign

### How to fix

This does involve some editing of the HTML as well as the CSS, so beware that you will break the ‘round trip’ to **InDesign**. In other words, only do this at your final stage.

**Here is an example of the output from InDesign** to the fixed-layout ePub:

```html
<span class="CharOverride-2" style="position:absolute;top:-70.31px;left:0px;letter-spacing:-0.64px;">Shakespeare</span>`
```
Yes, I know. Complex is it not?

![](../media/Pasted%20image%2020240222154706.png)

You will see that the word ’Shakespeare’ is enclosed in a span tag with inline CSS for styling.

What we need to do is to enclose each of the letters that need to use the swash in another span tag. (It is perfectly legitimate to nest span tags). This span tag needs a class:

```html
<span class="CharOverride-2" style="position:absolute;top:-70.31px;left:0px;letter-spacing:-0.64px;">   Sha<span class="swash">k</span>espear <span class="swash"> e</span>   </span>`
```
I have gone for the ‘**k**’ and the last ‘e’.

![](../media/Pasted%20image%2020240222154731.png)

Now we need to add some CSS and we can do this in the CSS file that InDesign has created (or we can create our own CSS file to be loaded at export time):

```css
span.swash {   font-feature-settings: "swsh" 1;    }` 
```
You can edit the CSS that InDesign produces, but I prefer to create my own CSS which I add at export time.

![](../media/Pasted%20image%2020240222154801.png)

You can see in the images here that we don't achieve these swashes until we post-edit the ePub after export from InDesign.

The font that I am using here is the revival FELL font created by [Igino Marini](http://iginomarini.com/fell/ "See the web site for this font").