## Content
1. [[Vue.js#Defenitions|definitions]]
2. [[Vue.js#Connecting via CDN|connection]]
3. [[Vue.js#Data|data]]
4. [[Vue.js#Event handler|event handler]]
	1. [[Vue.js#Events|events in vue]]
	2. [[Vue.js#Methods|methods]]
5. [[Vue.js#Buttons|buttons]]
6. [[Vue.js#4 mastodons of Vue|Vue basis]]
****
## Vue.JS. basics
### Definitions

_Vue.JS_ -- `framework`. Used to create user interface

`Framework` -- suggests specific way to write code, that makes easier and faster developing process. Unlike library, a framework provides a ready-made project structure


> advantages
* quite simple
* make development faster
* takes over the _DOM_
* component-based architecture

> disadvantages
* limited ecosystem for enterprise solutions
* smaller community & fewer developers (for ex. React community >>> Vue.JS community)
* over-flexibility can lead to inconsistent code
* less corporate backing
* potential performance issues in large applications

### Connecting via CDN

`in index.html`
```html
<head>
	<script src=
	"https://cdn.jsdelivr.net/npm/vue/dist/vue.js"
	>
	</script>
	<script src="index.js"></script>
</head>
<body>
	<div id="app">
	<!--here'll be our app-->
	</div>
</body>
```


****
### Data

Any Vue app has some _data_. It's represented by the objects in this template

```js
let app = new Vue({
	el: `#app`,
	data: {
		username: `John`,
		age: 17
	}
})
```

We can _print_ data into template via `{}`

```html
<div id="app">
	<h1>
		My name is {{ usernae }}, and
		I'm {{ age }} years old.
	</h1>
</div>
```


****
### Event handler

We won't see anymore these 3 mastodons of JS:
1. `document.querySelector()`
2. `node.innerHTML`
3. `button.addEventListener()`

> this
#### Events
_Events_ in Vue -- are `directive` -- a special _attribute_ that can be added to any tag

_@event_:
* `@click`
* `@input`
* `@keydown`

#### Methods

App methods are described in object _methods_
```js
let app = new Vue({
	methods: {
		hello() {
			console.log(`Hello, World!`);
		},
		greeting() {
			console.log(`Hi, my name is John`);
		}
	}
})
```

> is one section

_Event_ and _method_ can be easily combined inside app template
```html
<div id="app">
	<button @click="greeting"
			class="btn, btn-primary">
		click me
	</button>
</div>
```


****
### Buttons

Let button has _data-property_ text
```html
<div id="app">
	<button class="btn btn-primary">
		click me
	</button>
	<p> {{ text }} </p>
</div>
```

Using method we can call on property using `this` to change it 
```js
let app = new Vue({
	methods: {
		love() {
		this.text += `🖤`;
		}
	}
})
```

> To call on property using method we _MUST_ use `this`

***INCORRECT***
```js
let app = new Vue({
	data: {
		text: ``
	}
	methods: {
		love() {
			text += `🖤`
		}
	}
})
```

***CORRECT***
```js
let app = new Vue({
	data: {
		text: ``
	}
	methods: {
		love() {
			this.text += `🖤`;
		}
	}
})
```

Changing _data_ automatically causes node to be re-rendered
This is called _responsiveness_ 


****
### 4 mastodons of Vue

1. declare `data`
2. print `data` into template: _{{ text }}_
3. change `data` in `method`: _love() { this.text += "🖤"; }_ 
4. bind `method` and `event`: _@click="love"_


****
