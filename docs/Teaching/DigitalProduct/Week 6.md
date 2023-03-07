---
hide:
 - navigation
tags:
 - css
 - responsive
 - digitalproduct
---
I will be remote for this week since I have Covid

The focus of this session is making sure that the site that is delivered is responsive and should be usable on a mobile phone.

We will look at the CSS and how to use the Flex object to automatically reorganise content when on a smaller device. We also use `media-queries` to make changes to the styles at certain device widths.

## Editing the CSS for responsiveness

Remember that the HTML that we are using is already set up for us (because we are using a CMS) and has a good structure to help us with layout and design.

> [!important] 
> CSS = style, HTML = structure

## Using Flexbox

If we have a block element (such as a `div` or `section`) with a set of direct children (such as other block elements) then we can set the parent block to be a flex box and then the direct children can be arranged horizontally or vertically according to the available space. 

We can use this feature on the listing page, because the HTML (simplified) is like this:

```html
<div class="list">
	<section class="recipe-teaser">
		<h1>Recipe 1</h1>
		<div class="excerpt">
		<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Veritatis quidem placeat animi laboriosam, iste non consequatur velit iusto provident aliquam totam sed.</p>
		</div>
	</section>
	<section class="recipe-teaser">
		<h1>Recipe 2</h1>
		<div class="excerpt">
		<p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Veritatis quidem placeat animi laboriosam, iste non consequatur velit iusto provident aliquam totam sed.</p>
		</div>
	</section>
	<!-- + 3 or more recipe-teasers here -->
</div>
```

We should have 5 of those `recipe-teaser` blocks inside the `list` block.

The CSS that we need then is as follows, with comments

```css

.list {
display:flex;
flex-wrap: wrap; /* when there is not enough space the content will wrap */
justify-content: space-between;
}

.recipe-teaser {
border:1px solid rgb(161, 161, 161);
padding: 1em;
flex-basis: 300px; /* this is the preferred dimension if space allows */
flex-grow: 1; /* the width can grow if space allows */
margin:1em;
}
```

## Media Queries

Using flex box is very useful because the space is arranged automatically. There are some other features of your web pages that we also need to adjust when viewing on different device widths. For these we can use media queries in our CSS to provide some different rules according to the width of the display. For example, we may not want  large margins around the content on smartphones, rather we want to make use of the maximum amount of space that we have.

```css
/* on our normal computer screen we limit the widthof the main box */
	main {
	width:70%;
	padding: 2em;
	margin:4em auto;
	}
	
/* the following means when the screen is smaller than 700px wide */
@media (max-width: 700px) {
	main {
		width:100%;
		margin:0;
		padding:0;
	}
}
```

## Testing the site on mobile

If you are using Apple Safari browser, you need to switch on the `develop` menu by going to _settings_ - _advanced_. Then you can choose `Enrer Design Responsive Mode`. This will give you lots of device options to test your pages.

### On your Phone
Your web site needs to be live. Open the web site in your phone's browser. You can also add the site to your home screen. 

> [!NOTE] The system is already setup to make the web site into a _simulated_ web app for your phone
> You can also change the icon by going to this web site and replacing the icons folder on GitHub
>The template we are using already has a favicon but you can update this to [yours by going to this icon generator here](https://realfavicongenerator.net/) and generating the various versions. You will need to replace the ones in the **icons** folder through GitHub.

See also the following:
[Getting responsive with Flex](../../Web%20Sites%20with%20GitHub/Getting%20responsive%20with%20Flex.md)

You can check this document and look at the CodePen

## Questions about adding Video to site

These can be answered by reading through these instructions.

[Add Multimedia to Your web site](../../Web%20Sites%20with%20GitHub/Add%20Multimedia%20to%20Your%20web%20site.md)