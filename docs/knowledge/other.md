# 杂七杂八

## defer和async
- defer：浏览器指示脚本在文档被解析后执行,script被异步加载后并不会立刻执行,而是等待文档被解析完毕后执行。
- async：同样是异步加载脚本,区别是脚本加载完毕后立即执行,这导致async属性下的脚本是乱序的,对于script有先后依赖关系的情况,并不适用。

正常情况下永远不要用这两个属性

---
```
    <script src="">
        如果写src,则会执行外部js,不会执行内部js    
    </script> 
```
--- 

## 技巧
```js
// 解析参数:
Object.fromEntries((new URLSearchParams(location.search)).entries())
```