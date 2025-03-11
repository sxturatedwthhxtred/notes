****
## bethink
[events](JSMegaBase#Events)
[buttons](JSMegaBase#Buttons)

## Content
1. [[Forms#Event object|event object]]
2. [[Forms#Event listener|event listener]] (more in [[JSMegaBase#Events]])
3. [[Forms#Event objects properties|event props]]
4. [[Forms#Document|document]]
5. [[Forms#Position|position]]
6. [[Forms#node.style|node style]]
7. [[Forms#drop-down list|drop-down list]]
8. [[Forms#Event target|event target]]
9. [[Forms#Finding container|finding container]]
## Theory

### Event object

Event -- information about user or browser action:
1. Mouse click
2. Mouse move
3. Keyboard input
4. Scroll 
5. Video loading 
6. etc.

Browser stores additional info about event in event object 
> for example: click coordinates
```js
buttonNode.addEventListener(`click`, (evt) => {
	console.log(evt.clientX);
	console.log(evt.clientY);
});
```


****
### Event listener

*Events* are caused in *elements*.
To react on 'em we write code in *event listener*
```js
buttonNode.addEventListener(`click`, () => {
	console.log(`Button was clicked`)
});
```


****
### Event objects properties

```js
evt.clientX; // x-axis coord
evt.clientY; // y-axis coord
// (0; 0) -- upper left corner
```


****
### Document

*Document* -- special object that provides access from JS to HTML-file like this: 
```js
document.querySelector(`#node`);
```

if we trynna add event listener on *document* event listener is gonna work on _every_ element on the page 
```js
document.addEventListener(`click`, (evt) => {
	console.log(evt.clientX);
});
```


****
### Position 

> absolute. Used to pin an element relatively browser's window
```css
button {
	position: absolute;
	top: 100px;
	left: 200px;
}
```
`left` and `top` properties shows what idents must be with element and page's side


****
### node.style

Styles of element

if we gotta change *coord* of an element then we can do it via *JS property* `style`
```js
node.style.top = `100px`;
node.style.left = `200px`;
```

after changing `node.style`, the element will have inline-styles

Using this property we can change any CSS property
```js
node.style.color = `red`;
node.style.border = `1px solid black`;
```

if CSS property is written using `-` (hyphen) then in it's capitalized in JS code
```js
// background-color
node.style.backgroundColor;

// margin-bottom 
node.style.marginBottom;
```


****
### drop-down list

> realization via `Bootstrap`
```html
<select class="form-select">
	<option value="1">One</option>
	<option value="2">Two</option>
	<option value="3">Three</option>
</select>
```
<select class="form-select">
	<option value="1">One</option>
	<option value="2">Two</option>
	<option value="3">Three</option>
</select>

[input event for select tag](JSMegaBase#input+select)


****
### Event target

`evt.target` -- Property of an _event object_ contains element where event was triggered
```js
function clickEvent(evt) {
	console.log(evt.target);
};
```

U can use `evt.target` when we gotta _change element_ where event was triggered
```js
function clickEvent(evt) {
	let item = evt.target;
	item.classList.add(`active`);
};
```

#### Checking event target

`example:` what if we don't have elements on a page when we are adding event handlers? 
We can add event handler 2 ways:
1. on element
2. on element's container -- _delegation_

Event target can be any element in the container when used delegation


****
### Finding container

> Finding methods
```js
// finding by class in item
item.querySelector(`.exampleClass`);

// finding by class between item's containers 
item.closest(`.exampleClass`);
```

[[JSMegaBase#Find element in document|more info]]

