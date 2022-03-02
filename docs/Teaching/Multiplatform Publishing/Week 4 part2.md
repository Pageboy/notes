#multiplatform

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

**Note: In this version we start with the large display mode**

We make the nav item sit at the top and spread out over the page and we make the `ul` inside this a flex item.


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
  flex: 0 0 8rem; /*the same as flex-grow, flex-shrink, flex-basis */
  text-align: center;
}

/* we turn off the underline and set the padding and the color O */

nav ul li a {
  text-decoration: none;
  padding: 0.8rem 1rem;
  display: block;
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
  /*   font-size: 0.8rem; */
}

nav ul li:hover ul {
  display: flex;
  flex-direction: column;
}

nav ul li ul li {
  flex: 0 1 auto;
  width: 8rem; /* the same as the value for flex-basis on the parent li */
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
    flex: 0 0 auto; /*the same as flex-grow, flex-shrink, flex-basis */
    width: 100%;
  }

  nav ul li:hover ul {
    display: flex;
    flex-direction: column;
    width: 100%;
  }
}
```

Now let’s try with the hamburger menu 

In this version we need to use a hamburger menu item that will reveal the menu.  For this we need a checkbox as input that will toggle this on and off.

We need to add this to the HTML inside the `nav`

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

So when the display is small we can use our media query to hide the menu but reveal the hamburger

```css
.hamburger {
    display: block;
    float: right;
    cursor: pointer;
  }

  /*   ~ the tilda points to the next sibling selector */

  input[type="checkbox"]:checked ~ ul {
    display: block;
  }
```
