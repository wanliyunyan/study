# valueOf()与toString()

这两个方法有意思的地方在于什么时候使用，总结如下：
1. valueOf()偏向于运算，toString()偏向于显示
2. 对象转换时，优先调用toString()
3. 强转字符串的情况下，优先调用toString()方法；强转数字的情况下优先调用valueOf()
4. 正常情况下，优先调用toString()
5. 在有运算操作符的情况下valueOf()的优先级高于toString()，这里需要注意的是当调用valueOf()方法无法运算后还是会再调用toString()方法

基本上，所有JS数据类型都拥有valueOf和toString这两个方法，null除外

## valueOf()

| 对象 | 返回值 | 类型 |
| ------- | ------- |------- |
| Array | 数组本身 | Array |
| Boolean | Boolean 值 | Boolean |
| Date | 存储的时间是从 1970 年 1 月 1 日午夜开始计的毫秒数 UTC | Number |
| Function | 函数本身 | Function |
| Number | 数字值 | Number |
| Object | 对象本身 | Object |
| String | 字符串 | String |

## toString()

| 对象 | 返回值 | 类型 |
| ------- | ------- |------- |
| Array | 数组的元素被转换为字符串，这些字符串由逗号分隔，连接在一起。其操作与 Array.toString 和 Array.join 方法相同 | String |
| Boolean | 字符串“true”，“false” | String |
| Date | 字符串日期，如"Fri Dec 23 2016 11:24:47 GMT+0800 (中国标准时间)" | String |
| Function | 函数字符串 | String |
| Number | 字符串形式值 | String |
| Object | "[object Object]" | String |
| String | 字符串 | String |

---

## 例子

```
let aaa = {
    i: 10,
    valueOf: function() { return this.i+30; },
    toString: function() { return this.valueOf()+10; }
}
alert(aaa > 20); // true 调用的 valueOf
alert(+aaa); // 40 调用的 valueOf
alert(aaa); // 50 调用的 toString
```