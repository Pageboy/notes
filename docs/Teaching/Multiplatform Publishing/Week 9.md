---
hide:
 - navigation
 - toc
 - tags
---
## The Fixed Layout eBook
[Here is a more comprehensive document](https://www.publisha.org/pages/id2fixed/) that explains all.

- Articles don't have any impact
- All content will show including page numbers and running headers
- We can use the whole spread to the edge of the pages; images can bleed etc.
- You can even add backgrounds but use with caution

### First try

Workflow for the session:

- Use the best version of the InDesign work
	- Duplicate and rebuild book panel
	- Good global toc and be sure to update
- edit the user CSS to the following only:

```css
section.dramatis {
  border-style: none;
}
section.play {
  border-style: none;
}
figure.sceneImage,
figure.playtitle {
  border-style: none;
}
```

>Note: This might be different for yours if the style selectors are not as above (`sceneimage` rather than `sceneImage`). Remember - `figure` and `section` will have borders by default.

Try one attempt at the fixed layout ePub.

Crucial to select `Convert Spread to Landscape Page`

![[Screenshot 2022-03-18 at 10.55.29.png]]

### Issues to note
Half Title appear to the right with blank on the left
Drop down TOC works hopefully
The on-page TOC should also be interactive
If a text box spreads over 2 pages in the spread, it could affect the table of contents if that item is heading used in the toc; ie you may get the item twice in the toc.

## Next Steps
We need a landscape start page so we have 2 options:

1. remove the Half Title and then make the second spread the start page (by page I mean landscape)
2. add a single page to the left of the half title and make this the start 'page'.
3. Your start landscape page needs to be your title page
4. You will need to make something similar for the page that starts the play

### How can we add or remove single pages?

In the pages panel we need to untick the `Allow Document Pages to Shuffle`

![[Screenshot 2022-03-18 at 11.54.15.png]]

Then we can add or remove single pages. We will need to rearrange pages and add a section to get the page numbers back to odd on the right.

## Look at the details
Remember, the fixed layout eBook gives you exactly what you see in InDesign, so before adding enhancements we should check:

- orphans and widows
- page numbers
- running headers
- image positions and wrapping
- table of contents
- preflight errors

### The Page edge
In the fixed layout eBook, content such as images or colour blocks can use the _full_ page; right to the edge. Consider using images beyond the text block and into the margins.

## Images
These will appear as seen but  not enlarge as they do in Apple Books for the reflowable version. We will make interactive by converting to a button.

Images will already be anchored (from the work we did before), but they do **not need to be** for the fixed-layout version, so, if we need to add more images, we can simply place anywhere. We can even create double page spreads for images.

## Enhancing the eBook
We are looking at this in the next weeks but if you want to read ahead on this [then go here for details](https://www.publisha.org/pages/enhanced_eBook/).

### Image Enlargement
We can look at making an image enlarge by making use of buttons and layers.

## How to read eBooks
Here is a developing list of [[epubreaders]]

#epubproduction 