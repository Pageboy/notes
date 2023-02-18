## Some Notes about the CSS for our recipe site

### Specificity

This is an important concept in CSS because we can apply some style rules with fine grain control.

The first way to do this is to make sure that the various elements in the HTML will have class names; this will allow us to target them beyond the default HTML. For example paragraphs are marked up with `<p>` but if we add class names like `<p class="review">` then we can use the following in the CSS:
```css
.review {font-size: 1.5em;}
```

Another way to target specific elements that don't have unique class names is to use the class name on the parent. So, say we have an image that is inside a section with a classname of `introduction` - here is some HTML:

```html
<section class="blurb">
	some content
	<img src="top-pic.jpg">
</section>
<section class="introduction">
	<img src="productpic.jpg">
</section>
```

We can apply different styles to these 2 images with the following CSS:

```css
.blurb img {
border: 1px solid grey;
}
.introduction img {
width: 50%;
float:right;
}
```

So you see we can address each image according to it's parent. This is known as a _descendant selector_.

In the above example you might say "Why can't we add class names to the `img` tag?" - yes, you could but with content management systems we don't always have the ability to control the HTML output.

## The Recipes site
In the recipes site we have 3 types of page; the home page, the listing page and then a recipe page (repeated). There is one thing that makes those pages unique and that is the class name on the body tag.

![](../../media/Screenshot%202023-02-17%20at%2023.20.56.png)

The body tag for the home page looks like this:

```html
<body class="recipeshome">
```

 and for the page for the list of recipes:

```html
<body class="recipelist">
```

and for the recipe page itself:

```html
<body class="recipe">
```

Ok so this means that we can different styles to these page by referring to this parent class. For example to have a different  colour for the header in these pages:

```css
.recipeshome header {
background-color: rgb(87, 82, 69);
}
.recipelist header {
background-color: gray
}
.recipe header {
background-color: black
}
```

### Other ways to target elements according to their position

Sometimes we want to style something differently because it follows a heading or some other item. Take this HTML:


```html
<h2>Method</h2>
<p>Make the dressing with the following ingredients; half a cup of red wine vinegar, half a teaspoon of sugar, salt and pepper and half cup of extra virgin olive oil</p>
<p>Place orzo pasta into a pan of boiling water and cook as directed by instructions on packet. Leave to Cool, then place into serving dish.</p>
```

The paragraphs  are both marked up with just `<p>`.  But if we want the paragraph that follows the heading to have a different appearance we can use the following CSS:

```css
p {
font-size: 1em;
}
h2 + p {
font-size: 1.2em;
}
```

This is known as the *adjacent sibling* selector.  With this CSS,  the paragraphs will have a font size of 1em, but the one that follows the h2 will have a size of 1.2em.