---
hide:
 - navigation
tags:
 - css
 - responsive
 - multiplatorm
 - digitalproduct
---

## Some CSS using **flex**

```css

* {
  box-sizing: border-box;
}

body {
  margin: 0;
  font-family: verdana;
}

h1 {
  text-align: center;
}

h2 {
  margin: 0;
  background: gray;
  color: white;
  padding: 5px;
}

p {
  margin: 2px 5px;
}
```

```css
main {
  font-size: 80%;
  border: 1px solid green;
  padding: 12px;
  width: 75%;
  margin: 0 auto;
  display: flex;
  justify-content: center;
  flex-direction: row;
  flex-wrap: wrap;
}

.info {
  border: 2px solid silver;
  margin: 12px;
  flex-basis: 280px;
}
```

## Media Queries

```css
@media (max-width: 500px) {
  main {
    width: 100%;
  }
  .info {
    flex-basis: 100%;
  }
}

```

You can see a Codepen example [here](https://codepen.io/pageboy/pen/ZEJXJyv)

<iframe height="500" style="width: 100%;" scrolling="no" title="Flex for Responsiveness" src="https://codepen.io/pageboy/embed/ZEJXJyv?default-tab=html%2Cresult" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href="https://codepen.io/pageboy/pen/ZEJXJyv">
  Flex for Responsiveness</a> by Chris Jennings (<a href="https://codepen.io/pageboy">@pageboy</a>)
  on <a href="https://codepen.io">CodePen</a>.
</iframe>