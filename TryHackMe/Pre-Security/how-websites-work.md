# How Websites Work

- HTML builds the structure of a website.
- CSS styles it.
- JavaScript (JS) adds interactivity to it.

## HTML

```html
<img src="img/cat.jpg">
```

- This is an image tag. `src` is an attribute used to tell the browser where the image is located.
- Elements can also have an `id` attribute (`<p id="example">`), which is unique to that element.
- Unlike the `class` attribute, where many elements can share the same class, every element must have a different id so it can be identified uniquely.
- Element ids are used for styling and for JavaScript to find the element.

## JavaScript

- HTML gives the website its structure, but JS makes it interactive.
- Without JS, a website wouldn't have interactive elements and would always be static.
- For example, JS can change a button's style when it is pressed.
- JS can be written inside the page between `<script>` tags, or loaded from another file using the `src` attribute:

```html
<script src="/location/of/javascript_file.js"></script>
```

- This code finds the element with the id "demo" and changes its content to "Hack the Planet":

```javascript
document.getElementById("demo").innerHTML = "Hack the Planet";
```

- HTML elements can also have events, like `onclick` or `onmouseover`, that run JS when the event happens. This button changes the "demo" element's text to "Button Clicked" when it's clicked:

```html
<button onclick='document.getElementById("demo").innerHTML = "Button Clicked";'>Click Me!</button>
```

- `onclick` events can also be defined inside `<script>` tags instead of directly on the element.

## Sensitive Data Exposure

- This is when a website doesn't protect sensitive information, so it can be read in plain text in the front-end code (the page source).
- For example, developers sometimes forget to remove test user credentials from the website's front-end code, which can later be used to gain admin privileges and more.

## HTML Injection

- This is when a website doesn't do input sanitisation (cleaning/filtering what users type), so its input fields become vulnerable to HTML and other malicious injections.
- Whatever the user types gets shown on the page as real HTML. For example, an attacker could inject a link:

```html
<a href="http://hacker.com">http://hacker.com</a>
```
