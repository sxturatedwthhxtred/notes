## Content
## Part 1
1. [[Vue.js#Defenitions|definitions]]
2. [[Vue.js#Connecting via CDN|connection]]
3. [[Vue.js#Data|data]]
4. [[Vue.js#Event handler|event handler]]
	1. [[Vue.js#Events|events in vue]]
	2. [[Vue.js#Methods|methods]]
5. [[Vue.js#Buttons|buttons]]
6. [[Vue.js#4 whales of Vue|Vue basis]]

## Part 2
1. [[Vue.js#Creating a project|creating a project]]
	1. [[Vue.js#App mount|app mount]]
2. [[Vue.js#Another approach|another approach]]
	1.  [[Vue.js#Component connection|component connection]]
	2.  [[Vue.js#Component naming|how to name components]]

## Part 3
1. [[Vue.js#Attributes|attributes]]
	1. [[Vue.js#v-bind|v-bind directive]]
2. [[Vue.js#Classes|classes]]
3. [[Vue.js#Styles|styles]]
4. [[]]
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

We won't see anymore these 3 whalex of JS:
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
### 4 whales of Vue

1. declare `data`
2. print `data` into template: _{{ text }}_
3. change `data` in `method`: _love() { this.text += "🖤"; }_ 
4. bind `method` and `event`: _@click="love"_


****
### Creating a project

run command:

```bash
npm create vue@3 project_name
```
> replace project_name with ur own

open project directory and install packages:
```shell
npm install
```


#### App mount

`main.js`
```js
import { createApp } from "vue";
import App from "./App.vue"

createApp(App).mount("#app");
```

`index.html`
```html
<body>
	<div id="#app">
		<!--- here'll be our app --->
	</div>
	<script type="module" src="/src/main.js"></script>
</body>	
```


#### Running project

We can use this command after installing packages:
```shell
npm run dev
```

In general we can see the sequence of commands in terminal. It'll be like this:
```shell
Done. Now run:

	cd components-app
	npm install 
	npm run dev
```


****
### Another approach

At the core of Vue there are _components_ -- special interface elements that can be reused
Every component is saved in the individual `file.vue`

Every component contains 3 tag sections:
```vue
<script>
...
</script>

<template>
...
</template>

<style>
h1 { font-size: 40px }
</style>
```

_Components_ are like constructor, using them we can build an app

Component _`App.vue`_ -- is like platform for other component constructor
Here we can connect another components and call them like tags
```vue
<template>
	<h1>This is HTML tag btw</h1>
	<hello-world></hello-world>
	<hello-world />
</template>
```

When user will open our site _`App.vue`_ -- is the first thing he'll see
Vue has uniq browser-unfriendly syntax, so then we need `Vite assembler`

Assembler is used to translate Vue components to HTML, CSS and JS
It also runs local server that makes available files on `localhost`


#### Component connection

> import
```html
<script>
	import ComponentOne from './components/ComponentOne.vue'
	import ComponentTwo from './components/ComponentTwo.vue'

	export default {
		components: {
			ComponentOne,
			ComponentTwo
		}
	}
</script>
```

> usage
```html
<template>
	<component-one> </component-one>
</template>
```
or
```html
<template>
	<component-two /> 
</template>
```

#### Component naming
1. two-word phrase
2. CamelCase
3. doesn't repeat HTML-tags


#### Component creation
1. create a component file.vue in `components` folder
2. connect component into App

> Q: where to code styles?
> A: in components' file

****
### Attributes

We can change attributes (ex. to change image)
```vue
<script>
export default {
	data() {
		return {
			image: "src/assets/img.png"
		}
	}
}
</script>
```


> incorrect
```vue
<template>
	<img src="{{ image }}">
</template>
```

To substitute attribute into template we're using `v-bind` directive
```vue
<template>
	<img v-bind:src="image">
</template>
```

#### v-bind
1. spelt w/ `:`
	 `:src="imageSrc"`
2. classes via objects
	 `:class="{'isDark': true}"`
3. styles via objects
	 `:style="{'color': 'black'}"`


> shorter ver
```vue
<template>
	<img :src="image">
</template>
```

So, using `v-bind` we can paste any data-property into any attribute

```vue
<script>
export default {
	data() {
		return {
			image: "src/assets/img.png",
			imageWidth: 500,
			imageClass: "img img-fluid"
		}
	}
}
</script>



<template>
	<img :src="image"
		 :width="imageWidth"
		 :class="imageClass"
	>
</template>
```


****
### Classes

DOM example
```js
let button = document.querySelector(`.btn`);
let node = document.querySelector(`.node`);

button.addEventListener(`click`, () => {
	node.classList.toggle(`hidden`);
});
```

Instead of working w/ DOM, Vue works on principle of _reactivity_
Changing _data_ will cause _components_' redraw 

Same ex. but using `data`, `v-bind`, `@click`

> :class attribute can be set as an object w/ values _true_/_false_
```vue
<div :class="{
		'table': true,
		'red': false,
		'white': true
}">
...
</div>


<!--- same to the following v--->
```
```html
<div class="table white">
</div>
```


By principle of _reactivity_ we can bind a _data-property_ dependence for adding class:

> property
```vue
<script>
	data() {
		return {
		isHidden: true
		}
	}
</script>
```

> class
```vue
<template>
	<div :class="{
		'hidden': isHidden
	}">
		...
	</div>
</template>
```


Or add a _method_ that toggles class after _click-event_
```vue
<script>
	methods: {
		toggle() {
			this.isHidden = !this.isHidden;
		}
	}
</script>
```

```vue
<template>
	<button @click="toggle">
		Hide
	</button>
</template>
```


### Styles

Sometimes classes don't give us enough change flexibility
So then _styles_ come to the rescue

Attribute `:style` can be set like an object with _`CSS-properties`_ 
```vue
<div :style="{
	'font-size': '20px',
	'color': 'white'
}">
	...
</div>
```

Ofc we can make this _styles_ reactive by binding to the _data-properties_
```vue
<div :style="{
	'font-size': size + 'px',
	'color': color
}">
	...
</div>
```


mb the end btw