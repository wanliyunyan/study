# for

## for in
使用 **for...in...** 循环遍历对象的属性时,原型链上的所有属性都将被访问,如果只是
想遍历对象自身的属性,而不遍历继承于原型链上的属性,使用 **hasOwnProperty** 方法过滤一下。 

## Object.keys()
**Object.keys()** 方法会返回一个由给定对象的自身可枚举属性组成的数组,数组中属性名的排列顺序和使用 for...in 循环遍历该对象时返回的顺序一致 （两者的主要区别是 一个 for-in 循环还会枚举其原型链上的属性）

for循环也可以写成一下面这个样子
```
let i = 1;

for(;i;){
    console.log(i);
    i++;
    if(i===2){  
        // 如果不让用break return等中止循环,可以用 i = 0 undefined null "" NaN false
    }
}
```