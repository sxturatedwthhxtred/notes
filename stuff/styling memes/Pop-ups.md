### Description:

• Pop-up shows **at the bottom**, when there's `class="active"`.
• Using `position: fixed` to fix it by display
• Animation realized using `bottom: -100%` →` bottom: 20px`.

### Code
```HTML
<div class="popup">
	<p>Ваш текст здесь</p>
	<button class="close-popup">Закрыть</button>
</div>
```
```css
.popup {
	position: fixed;
	bottom: -100%; /* Скрыто за пределами экрана */
	left: 50%;
	transform: translateX(-50%); /* Центрируем по горизонтали */
	width: 300px;
	background: white;
	padding: 20px;
	box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
	transition: bottom 0.3s ease-in-out; /* Анимация появления */
}

.popup.active {
	bottom: 20px; /* Показываем поп-ап */
}
```
```js
document.querySelector('.close-popup').addEventListener('click', () => {
  document.querySelector('.popup').classList.remove('active');
});

// Чтобы открыть поп-ап программно
document.querySelector('.popup').classList.add('active');
```
