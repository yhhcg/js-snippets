### pipe  

A pipe flowing left-to-right.

The leftmost function can take multiple arguments.  
Each function takes the output of the previous one.
For example, pipe(f, g, h)(...args) is equivalent to doing h(g(f(...args))).

```js
  const pipe = (...fns) => fns.reduce((preFn, nextFn) => (...args) => nextFn(preFn(...args)));
```

**example**

```js
  const add = (x, y) => x + y;
  const plus = (x) => x * 2;
  
  compose(add, plus)(1, 2); // 6
```
