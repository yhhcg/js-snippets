### compose

Composes single-argument functions from right to left. The rightmost function can take multiple arguments. Each function takes the output of the previous one. For example, compose(f, g, h)(...args) is equivalent to doing f(g(h(...args))).

```js
  const compose = (...fns) => fns.reduce((preFn, nextFn) => (...args) => preFn(nextFn(...args)));
```

**example**

```js
  const add = (x, y) => x + y;
  const plus = (x) => x * 2;
  
  compose(plus, add)(1, 2); // 6
```
