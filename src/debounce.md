### debounce

Delays invoking function after waiting for milliseconds since the last time the debounced function was invoked.

```js
  const debounce = (fn, wait=0) => {
    let timeoutId;
    return function(...args) {
      timeoutId && clearTimeout(timeoutId);

      timeoutId = setTimeout(() => {
        fn.apply(this, args);
      }, wait);
    };
  }
```

**example**

```js
  let count = 1;
  const element = document.getElementsByTagName("body")[0];
  const getUserAction = (event) => {
    element.innerHTML = count++;
  };
  element.onmousemove = debounce(getUserAction, 1000);
```