### sleep

```js
  const sleep = (ms = 0) => new Promise(resolve => setTimeout(resolve, ms));
```

**example**

```js
  sleep(2000).then(() => {
    console.log('Two seconds later');
  });

  async function demo() {
    console.log('Taking a break...');
    await sleep(2000);
    console.log('Two seconds later');
  }
```
