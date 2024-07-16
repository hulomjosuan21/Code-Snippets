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
## Simple Switch Light and Dark Theme
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

toggle.addEventListener('click', function() {
  this.classList.toggle('bi-moon'); 
  if(this.classList.toggle('bi-brightness-high-fill')){
    body.style.background = 'white';
    body.style.color = 'black';
    body.style.transition = '2s';
  }else{
    body.style.background = 'black';
    body.style.color = 'white';
    body.style.transition = '2s';
  }
})
```
