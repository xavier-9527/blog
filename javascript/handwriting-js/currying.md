## 柯里化

### 定义

在数学和计算机科学中，柯里化是一种将使用多个参数的一个函数转换成一系列使用一个参数的函数的技术。

> 通俗易懂的解释：用闭包把参数保存起来，当参数的数量足够执行函数了，就开始执行函数。

### 实现

> 判断当前函数传入的参数是否大于或等于 fn 需要参数的数量，如果是，直接执行 fn
> 如果传入参数数量不够，返回一个闭包，暂存传入的参数，并重新返回 currying 函数

```js

```

### 应用场景

- 参数复用

```js
function getUrl(protocol, domain, path) {
  return protocol + "://" + domain + "/" + path;
}

var page1 = getUrl("http", "www.google.com", "page1.html");
var page2 = getUrl("http", "www.google.com", "page2.html");
```

使用 currying 来简化它：

```js
let site = currying(simpleURL)("http", "www.google.com");
let page1 = site("page1.html");
```
