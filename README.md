A Repository of notes of CMI courses and more!

These notes were taken in [Obsidian.md](https://obsidian.md/). Which is a Zettlekasten based note taking app.

A **TLDR** for the README: Stuff which is recommended 
- Use Obsidian - for the plugins
- Go to MOC folder to find notes, look directly if that does not work

---
## Alert
I strongly recommend using this app if you want to conveniently go over the notes in this repository. There are plugins used that might not be compatible with other markdown readers like logseq, or even the github website. Eventually I will be putting all of these notes on a website to make it easier to view for everyone (if you want that just bug me or the other people into doing it or do it for us).

---
## Finding Notes
Most of the college notes should be in the `Notes` folder, and you should be able to search by the topic.

An easier way to find notes, which will mostly not word for older notes would be to go to the `MOC` folder, and find the subject you are interested in, here notes are grouped based on mostly courses, but I do plan on making MOCs based on subject or other things.

MOC's for the following subjects should be good:
- Complexity
- Logic, Automata and Games
- Games on Graphs 
- Undecidability in Algebra and Topology
- Implementation of Functional Programming Languages

**TLDR** If it works, go to `MOC` folder, find subject, find file, otherwise search file by topic. 

---
## For those who will be using Obsidian

If you do choose to use obsidian for going over notes, the following plugins might be required for some notes
- **Admonition** 
	- This is for callouts in all the old notes before we started using the in built callouts 
- **TikZJax**
	- This plugin lets you render commutative diagrams, category theory and some algebra notes might require this.
- **Excalidraw**
	- For diagrams, this one is used somewhat regularly.

There are also some custom callouts, just put the contents of the code block in a file like `callouts.css`, and put the file in `CMI-Notes/.obsidian/snippets` and enable them in settings.
```css
.callout[data-callout="theorem"] {
    --callout-icon: lucide-pi-square;
    --callout-color: 159, 128, 249;
}

.callout[data-callout="definition"] {
    --callout-icon: lucide-book-a;
    --callout-color: 36, 240, 151;
}

.callout[data-callout="idea"] {
    --callout-icon: lucide-lightbulb;
    --callout-color: 226, 232, 65;
}

.callout[data-callout="history"] {
    --callout-icon: lucide-quote;
    --callout-color: 158, 158, 158;
}
```

---
## Contributing
The point of this repository is to be a resource for, at least, all current and future CMI students, so it would be very helpful if people keep adding notes to the repository. 

The following tips are recommended to keep things uniform
- Use the templates 
- Keep notes short and single-tiny-topic specific unless there is a good reason for it
- Build an MOC while writing the notes
- Mostly conforming to the ideas of Zettlekasten