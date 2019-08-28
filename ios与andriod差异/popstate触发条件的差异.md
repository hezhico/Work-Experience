

> 从A页面location到B页面，从B页面history.back(-1)返回到A页面

```js
  // A页面
  const state = {
    title: 'title',
    url: '#preventback',
  };
  window.history.pushState(state, 'title', '#preventback');
  window.addEventListener('popstate', (event) => {
    // todo something
    document.title = ' popstatein';
  });

  // andriod 不会触发popstate
  // ios     触发popstate
```