For this week we are looking at more details in how to style the play.

I make this Codepen here for you to explore and try to figure out what is happening.

>I have added 3 things to the HTML that have not been delivered from _InDesign_:

- The title of the play above the Dramatis personae like this:
```html
<header>
	<h1>A Midsummer Night's Dream</h1>
</header>
```
- I have wrapped all content (apart from the `nav` element) in a `main` box. This gives me more control over the overall display.
- I have added another `<li>` item for the link to the `Home page` like this:
```html
<li class="home TOC-Heading-1">
	<a href="index.html">Home</a>
</li>
```

I have created a [CodePen](https://codepen.io/pageboy/pen/YzprOEX) over here that you can explore.

## Unordered List becomes navigation
The exported HTML from InDesign should contain the table of contents as an `unordered list`. If you explore the HTML you are bound to struggle to understand this because InDesign does not put any breaks in the text; also it adds a lot of unnecessary  code. So..... let me show you a simplified version that may help in the comprehension of this.

### It's all about the nesting
A simple list in HTML looks like this:
```html
<ul>
	<li>Act 1</li>
	<li>Act 2</li>
	<li>Act 3</li>
</ul>
```

If we want to _nest_ other items within the top level items then we need another `ul` inside the `li` like this:

```html
<ul>
	<li>Act 1
		<ul>
			<li>Scene 1</li>
			<li>Scene 2</li>
		</ul>
	</li>
	<li>Act 2</li>
	<li>Act 3</li>
</ul>
```

You will notice that `li` for the first item does not close until after the closing of the nested `ul`.

>Note: If for some reason your version does not have this nesting this may be because you did not set up the TOC properly with the correct levels for the Acts and Scenes.

### The hyperlinking in the TOC

What we see here so far is just the structure; we also will have the links within the items. Here is a version with hyperlinks (although the links (#) are just false for now). I will also wrap the whole thing in the `nav` element, to help us turn this into a navigation.

```html
<nav>
	<ul>
		<li><a href="#">Act 1</a>
			<ul>
				<li><a href="#">Scene 1</a></li>
				<li><a href="#">Scene 2</a></li>
			</ul>
		</li>
		<li><a href="#">Act 2</a></li>
		<li><a href="#">Act 3</a></li>
	</ul>
</nav>
```

I hope that helps explain how the structure works.  How about the CSS?

## CSS for lists

By default a unordered list in HTML (`ul`) becomes a bulleted list and there are a number of default features that can be changed.

To remove the bullets:

```css
nav ul {
list-style: none;
}
```

To turn off the default <u>underline</u> on the links:

```css
nav ul li a {
text-decoration: none;
}
```

To hide the second level of the structure until the link above it is selected:

```css
li ul {
display:none;
}

nav ul li:hover ul {
display:block;
}
```

### Responsive Menu
We need to deliver the navigation for both large displays and mobile, so there needs to be a way display this `nav` item in 2 ways.

Optionally, we can display horizontally for large screens and then vertically on mobile.

This will be explored in further notes. In the meantime you can explore 
[Week 4 part 2](Week%204%20part%202.md)
