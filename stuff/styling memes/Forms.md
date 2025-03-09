****
## Theory

### bethink
[buttons 'n events](JSMegaBase)
- - -

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
