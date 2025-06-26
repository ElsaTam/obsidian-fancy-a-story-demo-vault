---
doc: https://elsatam.github.io/obsidian-fancy-a-story/docs/dataview/cards-deck.html
---


```dataviewjs
let result    = await dv.query(`LIST FROM "Obsidian UI"`);
let places = result.value.values;
let embeds = places.map(p => "[" + dv.fileLink(p.path, true) + "](<" + p.path + ">)");
dv.el("p", embeds, { cls: "dataview-cards-deck dataview-wide", attr: { id: "dataview-id-places" } });
```

```dataviewjs
dv.el("button", "Stop popover", { attr: { onclick: `
let decks = document.querySelectorAll(".dataview-cards-deck");
for (deck of decks) {
	console.log(deck);
	let links = deck.querySelectorAll("a.internal-link");
	for (link of links) {
		link.addEventListener("mouseover", (e) => {
			e.stopImmediatePropagation();
		})
	}
}` }});
```