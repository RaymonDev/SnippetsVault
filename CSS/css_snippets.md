## CSS

### Center an element horizontally and vertically
```css
.center-element {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
```

### Center an element vertically
```css
.center-vertically {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
}
```

### Center an element horizontally
```css
.center-horizontally {
  margin: 0 auto;
}
```


### Create a responsive flexbox container
```css
.container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}
```

### Style buttons
```css
.button {
  padding: 10px 20px;
  background-color: #007bff;
  color: #fff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}
.button:hover {
  background-color: #0056b3;
}
```

### Create a gradient background
```css
.gradient-bg {
  background: linear-gradient(to bottom, #ff9900, #ff5500);
}
```

### Add box shadow
```css
.box-shadow {
  box-shadow: 3px 3px 5px #888888;
}
```

### Style links
```css
a {
  text-decoration: none;
  color: #007bff;
}
a:hover {
  text-decoration: underline;
}
```

### Create a sticky header
```css
.sticky-header {
  position: sticky;
  top: 0;
  background-color: #ffffff;
  z-index: 100;
}
```

### Create a responsive grid layout
```css
.grid-layout {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 20px;
}
```

### Style a dropdown menu
```css
.dropdown-menu {
  display: none;
  position: absolute;
  background-color: #fff;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
}
```

### Animate an element on hover
```css
.animate-on-hover {
  transition: transform 0.3s ease;
}
.animate-on-hover:hover {
  transform: scale(1.1);
}
```

### Create a bordered box
```css
.bordered-box {
  border: 1px solid #ccc;
  padding: 10px;
}
```

### Style a navigation bar
```css
.navbar {
  background-color: #333;
  color: #fff;
  padding: 10px;
}
```

### Create a responsive image
```css
.responsive-image {
  max-width: 100%;
  height: auto;
}
```

### Style a form input
```css
.input-field {
  border: 1px solid #ccc;
  padding: 5px;
  border-radius: 3px;
}
```

### Style a progress bar
```css
.progress-bar {
  width: 100%;
  height: 20px;
  background-color: #eee;
}
.progress-fill {
  height: 100%;
  background-color: #007bff;
}
```

### Create a pulse animation
```css
.pulse-animation {
  animation: pulse 1s infinite;
}
@keyframes pulse {
  0% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.1);
  }
  100% {
    transform: scale(1);
  }
}
```

### Style a tooltip
```css
.tooltip {
  position: relative;
  cursor: pointer;
}
.tooltip-text {
  display: none;
  position: absolute;
  background-color: #333;
  color: #fff;
  padding: 5px;
  border-radius: 3px;
  bottom: 20px;
  left: 50%;
  transform: translateX(-50%);
}
.tooltip:hover .tooltip-text {
  display: block;
}
```

### Create a rotating spinner
```css
.spinner {
  animation: spin 1s infinite linear;
}
@keyframes spin {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
```

### Style a table
```css
.table {
  width: 100%;
  border-collapse: collapse;
}
.table th, .table td {
  border: 1px solid #ccc;
  padding: 10px;
}
```

### Create a 3D button effect 
```css
.button-3d {
  position: relative;
  background-color: #007bff;
  color: #fff;
  padding: 10px 20px;
}
.button-3d::before {
  content: "";
  position: absolute;
  top: 5px;
  left: 5px;
  right: 5px;
  bottom: 5px;
  background-color: #0056b3;
  z-index: -1;
}
```

### Style a horizontal rule
```css
.horizontal-rule {
  border: none;
  border-top: 1px solid #ccc;
  margin: 20px 0;
}
```

### Create a zoom-in animation
```css
.zoom-in-animation {
  animation: zoomIn 0.5s;
}
@keyframes zoomIn {
  0% {
    transform: scale(0);
  }
  100% {
    transform: scale(1);
  }
}
```

### Style a list with bullets
```css
.bullet-list {
  list-style: disc;
  padding-left: 20px;
}
```

### Create a slide-in menu
```css
.slide-in-menu {
  transform: translateX(-100%);
  transition: transform 0.3s ease;
}
.slide-in-menu.active {
  transform: translateX(0);
}
```

### Style a blockquote
```css
.blockquote {
  border-left: 2px solid #007bff;
  padding-left: 10px;
  margin-left: 20px;
  font-style: italic;
}
```

### Create a responsive card layout
```css
.card {
  width: 100%;
  max-width: 300px;
  border: 1px solid #ccc;
  border-radius: 5px;
  padding: 10px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}
```

### Style a footer
```css
.footer {
  background-color: #333;
  color: #fff;
  padding: 20px 0;
  text-align: center;
}
```

### Create a slide-down animation
```css
.slide-down-animation {
  animation: slideDown 0.5s;
}
@keyframes slideDown {
  0% {
    transform: translateY(-100%);
  }
  100% {
    transform: translateY(0);
  }
}
```

### Style a horizontal navigation menu
```css
.horizontal-menu {
  list-style: none;
  display: flex;
  justify-content: space-between;
}
.horizontal-menu li {
  margin-right: 20px;
}
```

### Create a diagonal background pattern
```css
.diagonal-pattern {
  background-image: linear-gradient(to bottom right, #007bff 50%, #fff 50%);
  background-size: 10px 10px;
}
```

### Style a notification badge
```css
.notification-badge {
  background-color: #ff5500;
  color: #fff;
  padding: 5px 10px;
  border-radius: 50%;
}
```







