#multiplatform

# Week 4
CSS for the play and responsive menu

## Lesson plan

Show my completed play but leaving off the menu to start with

### Show the following issues
* Width of 2 sections
* Use max-width
* Width of images
* Max height when tall
* Media query to reduce size of text
* Break points
* Revert to 100% for width when small
- - - -

### Issues

1. You may have a table for the Dramatis Personae
   * Tables can be styled with css
2. You may have put the character name on the same line as the first line of the speech
  * In this case we need to style the span as below

```css
.character_beforespeech {
  display: block;
  position: relative;
  left: -7em;
  top: 1em;
  font-size: 1.1em;
  /* border-bottom: 3px solid red; */
  width: 4em;
  padding-left: 4px;
}
```
