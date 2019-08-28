
> 通过class实现不同操作系统的不同样式

```js
  /**
  * 检测os 设置class
  */
  function checkOS() {
    const u = navigator.userAgent;
    const IsIOS = !!u.match(/\(i[^;]+;( U;)? CPU.+Mac OS X/);
    if (IsIOS) {
      document.getElementsByTagName('html')[0].setAttribute('class', 'ios');
    } else {
      document.getElementsByTagName('html')[0].setAttribute('class', 'android');
    }
  }
  checkOS();
```