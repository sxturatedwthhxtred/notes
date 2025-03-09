****
### :hover — pointing effect. ✓used in landing
```css
button:hover {
  background: blue;
}
```
Changes **background color of the button** when pointing.
****

### :focus — focusing elements (ex. when inputting)
```css
input:focus {
  border: 2px solid red;
}
```
Make border red when **field in focus**
****

### :nth-child(n) — chooses a specific elements
```css
.list-item:nth-child(odd) {
  background: lightgray;
}
```
odd / even elements gets gray background
****

### :active — used on element when it's activated (usually clicks)
**P.s.: active only when holding mouse click/tap(on mobile devices)**

```css
button:active {
    background-color: #ff0000; /* Меняем цвет кнопки при нажатии */
    transform: scale(0.95); /* Немного уменьшаем кнопку при клике */
}
```