---
tags:
 - digitalproduct
 - vscode
 - github
hide:
 - navigation
---

This week is to cover the basics of `HTML` and `CSS`.
We have covered this before in _Typographic Design for Page and Screen_, but I am very much going to go through the basics using **vscode**

First we need to get a copy of vscode

- Install vscode

[https://code.visualstudio.com/download]()

* Put the vscode icon on the dock

get this extension for vscode:

* Liveserver

Download the folder to try out styling one recipe. This is on moodle.

Connect to HTML and CSS tutorial

[The basics of HTML and CSS](The%20basics%20of%20HTML%20and%20CSS.md)

Hoe can we target the image and it's caption together when thaey are both in the paragraph like this:

```html
<p><img src="uploads/nikldn-qp7WA8AV2x0-unsplash.jpg" alt="pancakes and blueberries" />
<span class="caption">Photo by Joseph Gonzalez</span></p>
```

We can use the `has` selector like this:

```css
p:has(img) {
width: 45%;
float:right;
}

img {
width:100%;
}
```

This means that the image _together_ with the caption will float to the right.

In case the `has` selector is not supported everywhere we can use:

```css
.caption {
float:right;
width:50%;
}

img {
width:50%;
float:right;
margin-left: 10px;
}
```

As long as the caption and the image are set with the same width, this seems to work OK.