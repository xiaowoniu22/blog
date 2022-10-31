+++
title = "JS中的求值策略"
image = "/images/post/post-2.jpg"
author = "Echo Guo"
date = 2021-06-13T14:49:24+08:00
description = "JS learning"
categories = ["JS Learning"]
type = "post"

+++
## 一、是啥
求值策略（Evaluation strategy）是啥？  
是一种策略    
是一种决定什么时候，用什么方式计算函数参数的策略  
是一种分为严格求值和非严格求值的策略
![](https://p1-jj.byteimg.com/tos-cn-i-t2oaga2asx/gold-user-assets/2020/3/22/171012f3b2b2d41a~tplv-t2oaga2asx-image.image)


## 二、为啥  
为啥会需要这样一种策略？  

定义一个函数
```
function sum(x, y) {
    return x + y;
}
```
调用它
```
sum(8, 3);
```
这时候，问题产生了，编程语言需要在啥时候，用什么方式计算函数参数呢？这就是求值策略存在的意义。
下面用伪代码来解释一下严格求值和非严格求职的执行机制
```
//严格求值
function sum(x=8, y=3) {
    return x + y;
}
//非严格求值
function sum(x, y) {
    return (x=8) + (y=3);
}
```

正如所见，严格求值是参数在进入函数之前计算，而非严格求值则是在参数被调用的时候进行计算，不调用，不进行多余计算。

## 三、js？
JS中的求值策略是哪一种呢？  
先放结论，JavaScript 语言采用严格求值策略。  
将这一结论作为前提，我们再来解释一下严格求值策略的特性。针对js中的基本数据类型和引用数据类型，从现象倒推，可以总结为传值调用，传引用调用和传共享对象调用。
这里，我借鉴一下[Javascript中的求值策略](https://zhuanlan.zhihu.com/p/33035557)这篇文章中的代码示例
```
function magic(num, objectA, objectB) {
     num = num * 6;
     objectA = {name: 'AA'} 
     objectB.name = 'BB';
}
const num = 1;
const objectA = {name: 'A'};
const objectB = {name: 'B'};
magic(num, objectA, objectB);
console.log(num); // 1
console.log(objectA); // {name: "A"}
console.log(objectB); // {name: "BB"} 
```
**console.log(num); // 1 代表传值调用。** 参数的num=1，是复制了数字1，所以函数内部的操作不会影响外部的num值。  
</br>
**console.log(objectB);// {name: "BB"} 则代表传引用调用。**   参数中的objectB={name: 'B'}，只是复制objectB的引用，实际还是指向相同的地址，所以函数内部修改objectB的属性，外部的objectB也会受到影响。  
</br>
**console.log(objectA); // {name: "A"}   代表传共享对象调用。**  参数objectA={name: 'A'}，与函数里的操作objectA = {name: 'AA'}，使函数内部和外部是两个独立的object，互不影响，所以函数内部的操作也不会影响外部objectA的值。  
</br>

</br>

**看了好几篇文章，这里是我自己的理解，如有误，请指正。**

## 延伸
[惰性求值](https://juejin.im/post/6844903661450035207)  
[Thunk函数](http://www.ruanyifeng.com/blog/2015/05/thunk.html)


## 参考  
[Thunk 函数的含义和用法](http://www.ruanyifeng.com/blog/2015/05/thunk.html)  
[Javascript中的求值策略](https://zhuanlan.zhihu.com/p/33035557)  
[求值策略](https://www.cnblogs.com/tomxu/archive/2012/02/08/2341439.html)
