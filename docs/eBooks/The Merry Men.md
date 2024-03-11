## Robert Louis Stevenson

![Cover image](../../media/merrymencover.jpg)

Robert Louis Stevenson completed ‘The Merry Men’ when he lived in Bournemouth, England between 1884 and 1887. It was first published in 1887 with other short stories as ‘The Merry Men and Other Tales’.

First published in the IDLER, August 1894 and then later in a collection of essays titled ‘The Art of Writing’.

He started the first draft of “The Merry Men’ when he stayed in Scotland during the summer of 1881 and in his essay about the writing of ‘Treasure Island’ he mentions this fact.

The story takes place on the fictional Eilean Aros which Stevenson based on Eilean Earraid, a small islet near to the Ross of Mull and Iona. ‘The Merry Men’ are, in fact, the dangerous reefs known as the Torran Rocks.

[Download the eBook in ePub format](merrymen.epub)


## Technical Stuff

This ePUB was created using InDesign initially but then much editing of the XHTML and CSS was done using Dreamweaver.

One particular technique that I have used - only really experienced within the iBooks app (on Apple iOS devices) - is to provide some extra information as separate XHTML documents, invoked by a hyperlink. These extra pages are outside the flow of the book. This is achieved by editing the spine section of the OPF file thus:

```html
<itemref idref="merrymen"/>   <itemref idref="merrymen-1"/>   <itemref idref="merrymen-1a" linear="no"/>   <itemref idref="merrymen-1b" linear="no"/>
```