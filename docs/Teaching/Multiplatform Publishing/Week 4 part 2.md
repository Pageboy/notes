# Week 4.5
## Building the responsive menu
**Steps**

Show the simple HTML with some list items

```html
<nav>
  <ul>
    <li><a href="#">Home</a></li>
    <li><a href="#">Information</a>
      <ul>
        <li><a href="#">Services</a></li>
        <li><a href="#">Support</a></li>
        <li><a href="#">Products</a></li>
      </ul>
    </li>
    <li><a href="#">About</a></li>
    <li><a href="#">News</a></li>
    <li><a href="#">Contact</a></li>
  </ul>
</nav>
```

Now some basic CSS to show this off

```css
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: verdana, sans-serif;
  margin: 2em;
  padding: 0;
}
```

>**Note:** In this version we start with CSS that delivers for a large display.

We make the nav item sit at the top and spread out over the page and we make the `ul` inside this as a flex item.


```css
nav {
  width: 100%;
  position: fixed;
  top: 0;
  left: 0;
  background-color: grey;
}

nav ul {
  list-style: none;
  display: flex;
  align-items: center;
  justify-content: flex-end;
}
```

The list items are flex items and we can give them a width (flex-basis)

```css
nav ul li {
  flex-grow: 0;
  flex-shrink: 0;
  flex-basis: 8rem;
  text-align: center;
}

/* we turn off the underline and set the padding and the color */

nav ul li a {
  text-decoration: none;
  padding: 0.8rem 1rem;
  display: block;
  color: purple;
}

/* feedback for the user with a background when hovering hover */

nav ul li:hover {
  background-color: rgb(8, 119, 126);
}

nav ul li a:hover {
  color: white;
}
```

If we have sub menus then we need to hide those until we hover over

```css
/* sub menus */

li ul {
  display: none;
  position: absolute;
  background-color: rgb(8, 119, 126);
}

li ul li a {
  padding: 0.3rem 1.5rem;
}

nav ul li:hover ul {
  display: flex;
  flex-direction: column;
}

nav ul li ul li {
  flex: 0 1 auto;
  width: 8rem;
  /* the same as the value for flex-basis on the parent li */
}
```

### Smaller Screens

Now we need a media query to target when the display is small like on mobile

```css
/* now for the smaller displays */

@media screen and (max-width: 700px) {
  nav ul {
    flex-direction: column;
  }

  li ul {
    position: static;
  }

  nav ul li {
    flex: 0 0 auto;
    /*the same as flex-grow, flex-shrink, flex-basis */
    width: 100%;
  }

  nav ul li:hover ul {
    display: flex;
    flex-direction: column;
    width: 100%;
  }
}
```

This works and we could be happy with this, but now let's try to use a _hamburger_ button to show the menu on the smaller devices.

### Now let’s try with the hamburger menu 

In this version we need to use a hamburger menu item that will reveal the menu.  For this we need a checkbox as input that will toggle this on and off.

We need to add this to the HTML just inside the `nav`

```html
<input type="checkbox" id="toggle">
<label for="toggle" class="hamburger">&#9776;</label>
```

Note that **&#9776;** is an HTML entity that displays the **☰** (hamburger icon.)

Now in the CSS we need to hide this item when we are in the normal wide screen view:

```css
/* we hide the hamburger icon until we are on a small screen */

input[type="checkbox"] {
  display: none;
}

.hamburger {
  display: none;
  font-size: 2rem;
  color: white;
}
```

So when the display is small we can use our **media query** to hide the menu and reveal the hamburger

```css
@media screen and (max-width: 700px) {
  .hamburger {
    display: block;
    float: right;
    cursor: pointer;
  }

  /*   but we also need to hide the menu until that hamburger is clicked */

  nav ul {
    display: none;
  }

  /*when the hamburger is clicked, the ul below it will be made to show */
  /*  the tilda ~ points to the next sibling selector */

  input[type="checkbox"]:checked ~ ul {
    display: block;
  }
}

```

#### CodePen

You can explore this yourself on the [CodePen](https://codepen.io/pageboy/pen/MWqYzgP).

### One more thing

>There is one issue for the smaller screens.

You may notice that when you select one of the items on the menu and this takes you to that target location (maybe a scene in the play), then the menu remains expanded on the page. If you want to get it to hide and the hamburger, return, then you can only do this with javascript.

I have added this feature to the _CodePen_ and here is the explanation.

- first we need to add to the HTML a javascript command.
```html
<nav>
    <input type="checkbox" id="toggle" />
    <label for="toggle" class="hamburger">&#9776;</label>
    <ul onclick="hidemenu()">
    ....
```
-  next we add the following javascript function
```js
function hidemenu() {
  document.getElementById("toggle").checked = false;
}
```

The function looks for the element that has an `id` of `toggle`, and then unchecks the input checkbox and thus - hides away the menu.

>Note: To make this work on a live page we need to add the javascript function into the existing `head` tag of the HTML like this:

```html
<head>
	<script>
	function hidemenu() {
	  document.getElementById("toggle").checked = false;
	}
	</script>
</head>

```