## Dark Theme
### Description
- Dark Theme used on `body` by adding`class="dark-theme"`.
- Logo's color changes using `filter: invert(1)`.
- using `localStorage` to save theme

  
### Code
``` css
body.dark-theme {
  background: #121212;
  color: white;
}

  

.dark-theme .logo {
  filter: invert(1); /* Инвертирует цвет логотипа */
}
```
``` js
const themeToggle = document.querySelector('.theme-toggle');

themeToggle.addEventListener('click', () => {
  document.body.classList.toggle('dark-theme');
  localStorage.setItem('theme', document.body.classList.contains('dark-theme') ? 'dark' : 'light');
});

// Проверяем сохранённую тему при загрузке страницы_
if (localStorage.getItem('theme') === 'dark') {
  document.body.classList.add('dark-theme');
}
```
