### pipe  

A pipe flowing left-to-right.

The leftmost function can take multiple arguments.  
Each function takes the output of the previous one.

```js
  const pipe = (...fns) => fns.reduce((preFn, nextFn) => (...args) => nextFn(preFn(...args)));
```

**example**

```js
  const getName = (person) => person.name;
  const uppercase = (string) => string.toUpperCase();
  
  pipe(getName, uppercase)({name: 'yhhcg'}); // "YHHCG"
```
