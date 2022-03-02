# Getting responsive with Flex
## Some CSS using **flex**

```css
/*This is a snippet/*
/* 1rem is root value of em - normally 16px */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: Verdana, Geneva, Tahoma, sans-serif;
  /*your style rules go in here */
}
```

```css
main {
  border: 1px solid green;
  width: 70%;
  max-width: 800px;
  display: flex;
  flex-wrap: wrap;
  margin: 0 auto;
  padding: 0.5rem;
}

p {
  background-color: chocolate;
  color: white;
  padding: 8px;
  flex-basis: 300px;
  flex-shrink: 1;
  flex-grow: 1;
  margin: 0.5rem;
}

img {
  width: 100%;
}

figure {
  flex-basis: 300px;
  flex-shrink: 1;
  flex-grow: 1;
  margin: 0.5rem;
}
```

## Media Queries

```css
@media only screen and (max-width: 550px) {
  main {
    width: 90%;
    padding: 10px;
  }

```
#multiplatform