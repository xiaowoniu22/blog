+++
title = "原型链就是链表——挑战一句话解释一个概念"
image = "/images/post/person.png"
author = "Echo Guo"
date = 2022-08-02T14:49:24+08:00
description = "本质"
categories = ["本质"]
type = "post"

+++
**&emsp;&emsp;Hi，原型链就是链表**


**一、 节点和连接方式**  
&emsp;&emsp;原型链上的节点是各种实例对象和原型对象，如： Function.prototype 、 Object.prototype ……  
&emsp;&emsp;原型链通过 __proto __ 属性连接各种原型对象  
例如：   
```
arr.__ proto __ = Array.prototype；
Array.__ proto __= Object.prototype；
Object.__ proto __= null 

```


