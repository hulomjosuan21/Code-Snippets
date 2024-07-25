```
__        __   _                           
\ \      / /__| | ___ ___  _ __ ___   ___ 
 \ \ /\ / / _ \ |/ __/ _ \| '_ ` _ \ / _ \
  \ V  V /  __/ | (_| (_) | | | | | |  __/
   \_/\_/ \___|_|\___\___/|_| |_| |_|\___|
   to my Code Snippets
```
___
## Auto Typed

index.html
```html
<body>
  <div class="container">
    <h1>I'm <span class="auto-type"></span></h1>
  </div>

  <script src="https://unpkg.com/typed.js@2.1.0/dist/typed.umd.js"></script>

  <script>
    var typed = new Typed(".auto-type", {
      strings : ["Sad", "Alone", "Josuan"],
      typeSpeed : 150,
      backSpeed : 150,
      loop : true
    })
  </script>
</body>
```
style.css
```css
.container {
  width: 100%;
  height: 100vh;
  background-color: #020412;
  display: flex;
  align-items: center;
  justify-content: center;
}

h1 {
  color: white;
  font-size: 75px;
}

span {
  color: #fff724;
}
```
credits to https://github.com/mattboldt/typed.js
___

## 5 Basic CSS Animation
index.html
```html
<div class="box"></div>
```
style.css
```css
.box {
  width: 100px;
  height: 100px;
  background-color: rgb(30, 30, 255);
  border-radius: 20%;
}
```
Animation Rotating
```css
.box {animation: rotate 2.6s infinite;}

@keyframes rotate {
  0% {transform: rotate(0deg);}
  100% {transform: rotate(360deg);}
}
```
Animation FadeIn
```css
.box {animation: fadeIn 2s infinite;}

@keyframes fadeIn {
  0% {opacity: 0;}
  50% {opacity: 1;}
  100% {opacity: 0;}
}
```
Animation Pulsing
```css
.box {animation: pulsing 2s infinite;}

@keyframes pulsing {
  0% {transform: scale(1);}
  50% {transform: scale(1.25);}
  100% {transform: scale(1);}
}
```
Animation Sliding
```css
.box {animation: slide 2s infinite;}

@keyframes slide {
  0% {transform: translateX(0);}
  50% {transform: translateX(50%);}
  100% {transform: translateX(0);}
}
```
Animation Bouncing
```css
.box {animation: bouncing 1s infinite;}

@keyframes bouncing {
  0%,50% {transform: translateY(0);}
  40% {transform: translateY(-35px);}
  60% {transform: translateY(-15px);}
}
```
***
## Simple Switch Light and Dark Theme v1
Browser LocalStorage implemented
Get dependencies [https://blog.getbootstrap.com/2021/01/07/bootstrap-icons-1-3-0/]
Include in HTML
```
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.3.0/font/bootstrap-icons.css">
```
index.html
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <link rel="stylesheet" href="style.css">
  <script src="script.js" defer></script>
  
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.3.0/font/bootstrap-icons.css">
</head>
<body>
  <h1>Simple Switch Theme Code</h1>
  <i class="bi bi-brightness-high-fill" id="toggleDark"></i>
</body>
</html>
```
style.css
```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  text-align: center;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}
i {
  font-size: 50px;
}
```
script.js
```javascript
const toggle = document.getElementById('toggleDark');
const body = document.querySelector('body');

const currentThem = localStorage.getItem('theme');

if(currentThem === 'dark'){
  body.style.background = 'black';
  body.style.color = 'white';
  toggle.classList.add('bi-moon');
  toggle.classList.remove('bi-brightness-high-fill');
}else{
  body.style.background = 'white';
  body.style.color = 'black';
  toggle.classList.add('bi-brightness-high-fill');
  toggle.classList.remove('bi-moon');
}

toggle.addEventListener('click', function() {
  this.classList.toggle('bi-moon'); 
  if(this.classList.toggle('bi-brightness-high-fill')){
    body.style.background = 'white';
    body.style.color = 'black';
    localStorage.setItem('theme', 'light');
  }else{
    body.style.background = 'black';
    body.style.color = 'white';
    localStorage.setItem('theme', 'dark');
  }
  body.style.transition = '2s';

})
```
___
## Simple Modal Pop-up
index.html
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <link rel="stylesheet" href="style.css">
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.3.0/font/bootstrap-icons.css">

</head>
<body>
  <div class="container">
    <button onclick="openPopUp()">Pop-up modal</button>
  </div>
  
  <div class="popup-overlay" id="popup-overlay">
    <div class="modal-popup" id="modal-popup">
      <i class="bi bi-x" onclick="closePopUp()"></i>
    </div>
  </div>

  <script src="script.js" defer></script>
</body>
</html>
```
style.css
```css
* {
  margin: 0;
  padding: 0; 
  box-sizing: border-box;
}

:root {
  --transition-duration: 0.4s;
}

.container {
  width: 100%;
  height: 100vh;
  display: grid;
  place-content: center;
}

.popup-overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  backdrop-filter: blur(5px);
  visibility: hidden;
  opacity: 0;
  transition: opacity var(--transition-duration);
  z-index: 1;
}

.set-overlay {
  visibility: visible;
  opacity: 1;
}

.modal-popup {
  position: relative;
  top: 0%;
  left: 50%;
  width: 250px;
  height: 300px;
  background-color: rgb(255, 255, 255);
  padding: 0.5rem;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  border-radius: 8px;

  display: flex;
  justify-content: end;

  transform: translate(-50%, -50%) scale(0);
  visibility: hidden;
  transition: transform var(--transition-duration), top var(--transition-duration);
}

.modal-popup i {
  font-size: 24px;
}

.open-popup {
  transform: translate(-50%, -50%) scale(1);
  top: 50%;
  visibility: visible;
}
```
script.js
```javascript
let modal_popup = document.getElementById("modal-popup");
let overlay = document.getElementById("popup-overlay");

const openPopUp = () => {
  overlay.classList.add('set-overlay');
  modal_popup.classList.add('open-popup');
}

const closePopUp = () => {
  overlay.classList.remove('set-overlay');
  modal_popup.classList.remove('open-popup');
}
```
___
## Simple Switch Light and Dark Theme v2
Browser LocalStorage implemented
Get dependencies [https://blog.getbootstrap.com/2021/01/07/bootstrap-icons-1-3-0/]
Include in HTML
```
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.3.0/font/bootstrap-icons.css">
```
index.html
```html
<button class="theme-toggle"><i class="bi bi-brightness-high"></i></button>
<h2>Switch Color theme</h2>
```
style.css
```css
* {
  margin: 0; padding: 0; box-sizing: border-box;
}

:root {
  --clr-black-: black;
  --clr-white-: white;
}

body {
  height: 100vh; font-family: sans-serif; display: grid; place-content: center; grid-gap: 2rem; background-color: var(--clr-white-);
}

.dark-mode {
  --clr-black-: white;
  --clr-white-: black;
}

.theme-toggle {
  background-color: transparent; padding: 0.5rem; border-radius: 24px; border: none;
}

.theme-toggle i {
  font-size: xx-large; color: var(--clr-black-);
}

h2 {
  color: var(--clr-black-);
}
```
main.js
```javascript
const themeToggle = document.querySelector('.theme-toggle');
const icon = document.querySelector('.bi-brightness-high');

const theme = localStorage.getItem('theme');

theme && document.body.classList.add(theme);

themeToggle.addEventListener('click', () => {
  document.body.classList.toggle('dark-mode');
  icon.classList.toggle('bi-moon');
  if(document.body.classList.contains('dark-mode')){
    localStorage.setItem('theme', 'dark-mode');
  }else{
    localStorage.removeItem('theme');
  }
});
```
___
## Media screen query
xs
```css
@media (min-width: 475px) {}
```
sm
```css
@media (min-width: 640px) {}
```
md
```css
@media (min-width: 768px) {}
```
lg
```css
@media (min-width: 1024px) {}
```
xl
```css
@media (min-width: 1280px) {}
```
2xl
```css
@media (min-width: 1536px) {}
```
___