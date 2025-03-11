****
## Content:
1. [[JSMegaBase#what JS can do?|intro]]
2. [[JSMegaBase#Output on page|outputs]]
3. [[JSMegaBase#Find element in document|finding elements]]
4. [[JSMegaBase#Classlist|classlist]]
5. [[JSMegaBase#Buttons|buttons]]
6. [[JSMegaBase#Events|events]]


****
### what JS can do?

1. Works with DOM(Document Object Model)
> for example: document.querrySelector(...)
2. Contact with server
3. Responds to users actions
> `onclick` option, event listeners, etc.


```JS
const headers = document.querySelectorAll("h1");

// headers[0] -- the first h1

// headers[1] -- next one etc.

alert(headers[0].nodeName);
```

****
### Output on page

1. Create HTML file (4 now test-output.html)

2. Find it using JS (or write JS code in the script tag)

3. Output something in element

> note: this thing

```javascript

object.nodeName;

```

> returns the name of current node (as a string)

****
### Find element in document

> note: use `.classname`, `#id`, `tagname`, `div.card.a` (idk whats this)

`node.querySelector(selector)` -- find DOM element that matches selector
`node.querySelectorAll(selector)` -- returns all elements
> note: use just `classname`

`node.getElementById(id)` -- find element by its id (works faster if searchin' in full document)
`node.getElementsByClassName(classname)` -- by class name
etc.

```JS
// returns static NodeList representing a list of the document's elements that matches the specified group of selectors
document.querySelectorAll(selectors);

// returns the first found Node matching selectors
// syntax: #id, .classname
document.querySelector(selectors)

//example
let buttonNode = document.getElementById("click");
let specifiedWithIdNode = document.querySelector("#customid");
let someNode = document.querySelector(".customClassName");

// etc.
```


`node.closest()` -- finds container where the node is located (also it can be not found)
```js
function onClick(evt) {
	let node = evt.target;
	let item = node.closest(`.item`);
	if (black) {
		black.classList.toggle(`item-active`);
	}
}
```
****
### Classlist

#### classList changes
we can _add/remove/toggle_ class in element's class list using JS like this:
```js
textNode.classList.add(`class-1`);
textNode.classList.remove(`class-1`);
textNode.classList.toggle(`class-2`);
```

#### classList.contains()
using `classList.contains()` we can check what element do we have
```js
function onClick(evt) {
	let item = evt.target;
	if (item.classList.contains(`item-clickable`)) {
		item.classList.remove(`item-clickable`);
	}
	else {
		item.classList.add(`item-clickable`);
	}
};
```


****
### Buttons 

// there is few options to handle button click
1. `onclick` -- property of the DOM element
2. `button.addEventListener()` -- method, can be called several times
(needs to have several handlers), also allows to specify the event phrase
> `eventListener` method
```js
buttonNode.addeventListener(`click`, () => {
	console.log(`smth`);
});
```

> `onclick` property
```html
<div class="demo" onclick="exampleFunction">click me</div>

<script>
	function example() {
		document.querySelector(`.demo`).style.color = "fb8500";
	}
</script>
```

****
### Events
> `click` Just click, hopefully it not needed in description
```js
buttonNode.addEventListener(`click`, function() {
	console.log(`Hello, World!`);
});
```

> `mousemove` Triggers at every time mouse moves (even for 1 pixel)
```js
document.addEventListener(`mousemove`, (evt) => {
	console.log(evt.clientX);
});
```

> `keydown` Triggers when user clicks' any key
```js
document.addEventListener(`keydown`, (evt) => {
	console.log(evt.key);
});
```

> `input` Triggers when user types new symbol in text input area
```js
textNode.addEventListener(`input`, () => {
	console.log(textNode.value); // value contains information from input area
});
```

#### input+select
_input_ for _select_ tag triggers when any option was selected

value of this option can be viewed when calling select (like for text nodes)
```js
selectNode.addEventLister(`input`, () => {
	console.log(selectNode.value);
});
```

