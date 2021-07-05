https://responsibleweb.app
Joy Heron

responsive and accessible web applications

Responsive Layout Containers

```
.layout {
	display: grid;
	grid-template-areas:
		"header"
		"sidebar"
		"main"
		"sidebar-right"
		"footer";
	grid-template-rows: auto auto 1fr auto auto;
}
.layout > header {
	grid-area: header;
}
.layout > aside:nth-of-type(1) {
	grid-area: sidebar;
}
.layout > main {
	grid-area: main;
}
.layout > aside:nth-of-type(2) {
	grid-area: sidebar-right;
}
.layout > footer {
	grid-area: footer;
}

@media (min-width: 40rem) { /* Breakpoint Tablet portrait up */
	.layout {
		grid-template-areas:
			"header header header"
			"sidebar main sidebar-right"
			"footer footer footer";
		grid-template-rows: auto 1fr auto;
		grid-template-columns: 20% 1fr 20%;
	}
}
```

https://www.freecodecamp.org/news/the-100-correct-way-to-do-css-breakpoints-88d6a5ba1862/

## Squishy Components

```
.container {
display: flex;
flex-wrap: wrap;
}
```

### Intrinsic Grid

```
.container {
	display: grid;
	grid-template-columns:
		repeat(auto-fill, minmax(var(—col-width), auto));
}
```

### Horizontal Scrolling

```
.horizontal-scroll {
overflow-x: auto;
}
```

### Squishy-text -> hyphens

```
.squishy-text {
word-break: break-word; /_ Samsung browser _/
word-wrap: break-word; /_ IE 11 _/
overflow-wrap: anywhere;
-webkit-hyphens: auto;
-ms-hyphens: auto;
hyphens: auto;
}
```

## Accessibility

### Headings

You need to ensure that your document hierarchy is complete and doesn't skip levels (h2 is always directly followed by a h3)

### Landmarks

https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques#landmark_roles

important: main, header, nav

### Labels

```
<label>
	First Name
	<input type="text" value="name" placeholder="Jane" />
</label>
```

(you can aslso use "for" )

not use the placeholder attribute to label the input field
The placeholder attribute should be used to show an example of how the data we expect should appear

### lists

Using lists (an unordered list, an ordered list, or a description list) for things in a UI will also add extra context for assistive technologies. For instance, it will tell assistive technologies how many elements are contained in a list.

check Description List
https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dl

```
<p>Cryptids of Cornwall:</p>

<dl>
    <dt>Beast of Bodmin</dt>
    <dd>A large feline inhabiting Bodmin Moor.</dd>

    <dt>Morgawr</dt>
    <dd>A sea serpent.</dd>

    <dt>Owlman</dt>
    <dd>A giant owl-like creature.</dd>

</dl>
```

```
<dl>
  <div>
    <dt>Name</dt>
    <dd>Godzilla</dd>
  </div>
  <div>
    <dt>Born</dt>
    <dd>1952</dd>
  </div>
  <div>
    <dt>Birthplace</dt>
    <dd>Japan</dd>
  </div>
  <div>
    <dt>Color</dt>
    <dd>Green</dd>
  </div>
</dl>
```

### Accordions

```
<details>
	<summary>Toggle Button</summary>
	Content which will be expanded/collapsed when clicking the
	summary element
</details>
```

use the details element

We can also implement this in JavaScript using a button and the aria-expanded attribute. The aria-expanded attribute adds context information to the button which will tell the screenreader if the area that the button is toggling is currently collapsed or expanded.

```
<button is="toggle-button" data-target="#section2"
		  aria-expanded="false" hidden>
		Toggle Section 2
</button>

class ToggleButton extends HTMLButtonElement {
	connectedCallback () {
		this.removeAttribute("hidden");
		if (this.getAttribute("aria-expanded") !== "true") {
			this.setAttribute("aria-expanded", "false");
			this.target.classList.add("hide");
		}
		this.addEventListener("click", this.toggle.bind(this));
	}

	toggle () {
		let classList = this.target.classList;
		if (classList.contains("hide")) {
			classList.remove("hide");
			this.setAttribute("aria-expanded", "true");
		} else {
			classList.add("hide");
			this.setAttribute("aria-expanded", "false");
		}
	}

	get target () {
		return document.querySelector(this.getAttribute("data-target"));
	}
}
customElements.define("toggle-button", ToggleButton, { extends: "button" });
```

https://joyheron.com/a11y-playground/collapser.html

## Hiding content visually (but not from screenreaders)

```
.visually-hidden {
	clip: rect(0 0 0 0);
	clip-path: inset(50%);
	height: 1px;
	overflow: hidden;
	position: absolute;
	white-space: nowrap;
	width: 1px;
}
```

## Hiding content from assistive technologies

sing the aria-hidden attribute.

## check focus style

, you can customize them with the :focus CSS pseudo-selector. However, here it is very important that you still provide a focus style which has a high contrast and is easily identifiable within the UI.

For instance, if we are adding content to our DOM with JavaScript, as I did with this “Show More” Pagination Example, we should consider whether we should move the focus to the new content after it has loaded.

ensure that the focus is set correctly.
