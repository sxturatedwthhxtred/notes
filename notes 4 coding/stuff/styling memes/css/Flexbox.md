## bethink
1. Block model allows adjust size, padding, frame
2. works better with block and inline-block elements

### display
```css
span {
	width: 200px;
	height: 100px;
	display: block;
	backroud-color: #eeeeee;
}
```
property `display: block;` does elements block

```css
	display: inline-block;
```
and this thing makes any element `inline-block`

****
## FlexBox model
```css
	display: flex;
```

`flex-container`  manages
`flex-element` is inside

```html
<div class="container">
	<div class="item"></div>
	<div class="item"></div>
</div>
```

```css
/* flex-container */
.container {
	display: flex;
}

/* flex-item */
.item {
	width: 200px;
	height: 50px;
	margin: 20px;
}
```
container changes items:
1. position
2. size
3. margins

****
## Axis alignment

inside `flex-container` there's 2 axis 
1. main
2. cross
P.s:
`main is like Ox
`cross is like Oy, but inverted`
![[Screenshot 2025-01-03 at 1.12.41 AM.png]]

#### justify-content
main axis
```css
.container{ 
	display: flex;
	justify-content: flex-start;
}
```
`justify-content` property manages position of elements by main axis
by default they are on it's `beginning`

```css
	justify-content: flex-start;
	justify-content: center;
	justify-content: flex-end;
```
in order of `main` axis: 
1. beginning
2. center
3. end
(i don't know how to explain this)
![[Screenshot 2025-01-03 at 1.08.15 AM.png]]

#### align-items
cross axis
```css
.container {
	display: flex;
	align-items: flex-start;
}
```
 `align-items` property manages position of elements by cross axis
by default they are on it's `beginning`

```css
	align-items: flex-start;
	align-items: center;
	align-items: flex-end;
```

in order of `cross` axis: 
1. beginning
2. center
3. end

mixing properties
```css
.container{
	align-items: center;
	justify-content: center;
}
```

****
## Element's width

```css
.container {
	display: flex;
	align-items: center;
	justify-content: center;
	gap: 20px;
}
```
`gap` property -- distance between elements

```css
.item {
	flex-basis: 200px;
	height: 100px;
}
```
`flex-basis` -- size along the main axis

```css
.item1 {
	flex-basis: 30%;
}
.item2 {
	flex-basis: 70%;
}
```
`flex-grow` -- size along main axis
```css
.item {
	flex-grow: 1;
	height: 100px;
}
```

![[Screenshot 2025-01-04 at 01.58.58.png]]



## Conclusion
### Container
1. `gap: 20px` -- manages distance between elements

### Element
1. `flex-basis` -- manages size along main axis
2. `flex-grow` -- manages height along main axis

****

## Grid
```css
.container {
	display: flex;
	gap: 20px;
	flex-wrap: wrap;
}
```
`flex-wrap` -- line feed


```css
.container {
	display: flex;
	gap: 20px;
	flex-wrap: wrap;
}
.item {
	flex-grow: 1;
	flex-basis: 200px;
}
```
combo for `flexible` grid

****
## Adaptive Layout

**`Adaptivity`** -- web-page design, that provides `correct display` of the site on different devices

**`Mobile First`** -- Design and development of a website/application/design first for `mobile devices`, and then for large screen resolutions. 

**`Desktop First`** -- Design and development of a website/application/design first for `large screen` resolutions, and then for mobile devices.

**`Media Request`** -- used when we need to apply different `CSS` styles for different devices

@media
```css
@media screen {
	* {font-family: sans-serif;}
}
```
_Default usage example_

```css
@media screen {
	.sidebar (display: none;)
}
```
_Makes objects with `.sidebar` class `invisible` on smartphones

```Css
@media (min-width: 600px) and (max-width: 800px) {
	/* some style stuff */
}
```
_Rules applies only if displays width is in `range 600-800`


**`viewport`** -- `area` the user sees when accessing web-page from any device

```HTML
<meta
	  name="viewport"
	  content="width=device-width, initial-scale=1"
>
```
_ask browser whats `width` of the device
and calculates all `sizes` according to it

