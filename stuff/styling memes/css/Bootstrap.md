## Fullstack-development

### Framework: theory

- **Framework** — set of components used to automize routine activities
- **Bootstrap** — free and open source HTML, CSS and JS framework

### CDN Connection

- **CDN (Content Delivery Network)** – user data communication network
- **User** will **receive content** the fastest way to wherever he is
- The **sooner** user sees the site the **better**
- To use CDN Connection it's enough to add the relevant **link into the document**


> **NOTE** to include Bootstrap paste following link into `<head>` of site
```html
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous">
```

## Components: Theory

- **Component** — element or part of smth bigger 
- Components examples:  
  - button 
  - card
  - menu  
  - list  
  - table

### Button example

```html
<button class="btn btn-primary">Primary</button>
```
- Bootstrap based on using classes

### Button example with outline 

```html
<button class="btn btn-outline-primary">Primary</button>
```

- Easily change button color without using CSS

> **IMPORTANT!** Classnames are optional to memorize — always can check 'em on site;[[WhatsGithub?]]

## Dropdown (drop-down list)

- Combining familiar tags allows u to create user-friendly dropdown list

### Navigation (Navs)

- **Navs** — basic site navigation component 
- Large code blocks can be simple copied and used

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
## Cards

- **Card** — dynamic card for content
- Less than 10 code lines — finished component

## Bootstrap Grid

### Breakpoints

- Used to manage blocks behavior depending on screen size

| Screen size | class |
| ----------- | ----- |
| ≥ 576px     | sm    |
| ≥ 768px     | md    |
| ≥ 992px     | lg    |
| ≥ 1200px    | xl    |
| ≥ 1400px    | xxl   |

### Container

```html
<div class="container">
  <!-- Some content here -->
</div>
```

- Containers helps to contain, center and fill the content

### Rows and Columns (Row & Col)

- **Row** – horizontal line in container
- **Col** – column in row

#### Adaptive series example:

```html
<div class="row row-cols-1 row-cols-md-3"></div>
```

- On devices ≥ 768px – 3 columns, on smaller – 1 column (**automatically**!).

#### One more example

```html
<div class="row 
 row-cols-1 
 row-cols-md-2
 row-cols-lg-4">
</div>
```

- 4 col-s on desktop, 2 for pads and 1 for mobile
