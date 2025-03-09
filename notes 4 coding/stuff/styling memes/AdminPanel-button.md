### Description
- Button is fixes at the top right corner `position: fixed`.
- When Clicked opens modal window with 2 inputs
  

```html
<button class="admin-btn">Admin Panel</button>
```
```css
.admin-btn {
  position: fixed;
  top: 10px;
  right: 10px;
  padding: 10px 20px;
  background: red;
  color: white;
  border: none;
  cursor: pointer;

}
```
```Js
function openAdminPanel() {
	document.getElementById("adminModal").style.display = "flex";
};

function closeAdminPanel() {
	document.getElementById("adminModal").style.display = "none";
	document.getElementById("loginMessage").innerText = ""; // Очищаем сообщение

};
```