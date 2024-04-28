# React Fundamental

### createElement

![Notes-14](https://github.com/YagneshP/daily_routine/assets/29221654/165a6b06-f3e4-49ad-a358-ad8ce3e356b3)

```js
// selecting root element from the html file where we want to put our all react element.
const rootElement = document.getElementById("root");
// using createElement API from React
const helloWorld = React.createElement(
  "div",
  { className: "classy" },
  "Hello World"
);
```
