
> 检测不同的数据类型

```js
  // 工具函数
  let _toString = Object.prototype.toString
  let map = {
    array: 'Array',
    object: 'Object',
    function: 'Function',
    string: 'String',
    null: 'Null',
    undefined: 'Undefined',
    boolean: 'Boolean',
    number: 'Number'
  }
  let getType = (item) => {
    return _toString.call(item).slice(8, -1)
  }
  let isTypeOf = (item, type) => {
    return map[type] && map[type] === getType(item)
  }
```