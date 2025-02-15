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

---

# 🦋Working with npm

- npm stands for "Node Package Manager"

## Basic npm commands

- `npm init -y` creates a initializes a Project(`package.json` file).
- `npm install package-name` installs a package.
- `npm install -g package-name` installs a package a package globally.
- `npm uninstall package-name` deletes the package.
- `npm list --depth=0` is used to get the list of downloaded modules e.g. terser, autofixer, etc.

---

# 😉Working with SASS (Syntactically Awesome StyleSheets)

- It is a preprocessor for css.
- It introduces variables, nesting, functions, and mixins.

## 🏆How I installed SASS using npm.

```
npm install -g sass
```

```
sass --version
```

### 🤠Variables in sass.

```sas
$primary-color : blue;
body{
  background-color : #primary-color;
}
```

### 🤠nesting in sass.

```sas
  nav{
    ul {
      list-styles : none;

      li {
        display : inline;
      }
    }
  }
```

### 🤠mixins(reusable styles) in sass.

```sas
@mixin flex-center {
  display : flex;
  justify-content : center;
  align-items : center;
}

.box {
  @include flex-center;
}
```

### 🤠compiling Sass files.

```sas
sass input.scss output.css
```

# 🤠Working with Gulp.

- A tool that automates tasks like compiling Sass, minifying CSS/JS, and optimizing images.

## 🤠Downloading Gulp.

```javascript
npm install -g gulp-cli
```

- Create a project and install gulp locally.

```javascript
npm init -y
npm install gulp --save-dev
```

- Create a gulpfile.js to define tasks.

### 🤠Compiling sass files into css using GULP.

- First we are going to import the necessary modules.

```javascript
const gulp = require("gulp");// Gulp is used to define and run task.
const sass = require("gulp-sass")require("sass");// Gulp sass is used to compiling Sass files.
```

- Defining the task.

```javascript
function compileSass() {
    return gulp.src('src/scss/**/*.scss') // Get all `.scss` files from the src folder
        .pipe(sass().on('error', sass.logError)) // Compile Sass and handle errors
        .pipe(gulp.dest('dist/css')); // Output compiled CSS to the dist folder
```

### 🤠Exporting the Task.

```javascript
exports.default = compileSass; //This sets compileSass as the default task, so running gulp will execute this function.
```

#### 🤠How to run this Task.

- Make sure you have Node.js and npm installed.
  Initialize npm in your project:

```
npm init -y
```

- Install gulp and gulp-sass as dev dependencies:

```
  npm install gulp gulp-sass sass --save-dev
```

Create the folder structure:
css

```
project/
├── src/
│   ├── scss/
│   │   ├── styles.scss
├── dist/
├── gulpfile.js
├── package.json
```

Run the task:

```
gulp
```