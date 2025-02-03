# Social-Media-Dashboard with theme Switcher.

## 👋Hello, I'm Prabhjot Singh

---

### Functional Requirement of This Project.

Use fieldset, legend, radio inputs.

Light and Dark Mode toggle?

- What HTML Markup to use.
- Switching between dark and light mode.

CSS Variables and Custom variables.

- ` suggestion:` css properties are the simplest (native) way todo it that i know of, Declare themes in :root and apply a class to body or use a prefers-color-scheme media query to overwrite them.

### Syntax of `prefers-data-scheme` media query.

```css
@media (prefers-color-scheme: light) {
  /* Styles for light mode */
}

@media (prefers-color-scheme: dark) {
  /* Styles for dark mode */
}
```

Accessibility

- Use correct heading tags
- Screen reader - only text for card tittles/username.
- Toggle -- https://codepen.io/renddrew/pen/bRomab
- **_Will Use js to toggle between light and dark mode._**

## Changing the root: css and dark mode Using Javascript.

let root = document.documentElement;

```javascript
root.addEventListener("mouseover", (e) => {
  root.style.setProperty("--mouse-x", e.clientX + "px");
  root.style.setProperty("--mouse-y", e.clientY + "px");
});
```
```javascript
    <script>
        const root = document.documentElement;
        const dark = document.getElementById('Dark')
        const light = document.getElementById('Light')

        const enableDark = function () {
            root.style.setProperty('--body', '#000')
            root.style.setProperty('--font', '#fff')
            root.style.setProperty('--slide', '#fff')
            root.style.setProperty('--slider-bg', '#333')
        }

        const enableLight = function () {
            root.style.setProperty('--body', '#fff')
            root.style.setProperty('--font', '#333')
            root.style.setProperty('--slide', '#000')
            root.style.setProperty('--slider-bg', '#eee')
        }

        dark.addEventListener('click', enableDark);
        light.addEventListener('click', enableLight);

    </script>
```