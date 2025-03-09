### repeat()  

*`repeat()`* — used in `grid-template-columns` and `grid-template-rows`, *to avoid writing same thing 182372 times*
```css
.grid-container {
	display: grid;
	grid-template-columns: repeat(3, 1fr); /* Три равные колонки */
	gap: 10px;
}
```
repeat(3, 1fr) → creates **3 similar columns** by 1 part (fr = fraction).
****

### CSS-variables (*var()*)

CSS-variables allows *set colors, size and reuse 'em*

```css
:root {
	--main-bg: #121212;
	--text-color: white;
}

body {
	background: var(--main-bg);
	color: var(--text-color);
}
```
*declare variable* in *`:root`* (in example: `--main-bg` and `--text-color` — *`var-s names`*) 
****

### translateX()

*`translateX()`* — **moves the item horizontally**.

```css
.element {
	transform: translateX(-50%);
}
```
*`translateX(-50%)`* → moves **left** by **50% of element's width**

  