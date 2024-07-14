## Welcome to my code snippets

### Auto Typed
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
#credits to https://github.com/mattboldt/typed.js
---