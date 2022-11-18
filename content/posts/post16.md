+++
title = "不要再纠结于原型链和继承了"
author = "Echo Guo"
date = 2022-11-10T14:49:24+08:00
description = "原型链和继承"
categories = ["原型链和继承"]
type = "post"

+++
从这两个角度角度理解js原型链和继承，希望你不要再纠结原型链了。  
1. **原型链就是链表**
2. **从构造函数的属性（及方法）的类型出发来实现继承（此处没有考虑静态属性和方法）**

&emsp;&emsp;首先，要明白原型链就是链表，链表就包含节点和连接方式两个要素。实例对象或者构造函数的原型对象都可以作为节点，总之节点就是个对象。连接方式就是每个节点的__proto__（[[Prototype]]）,每个节点通过__proto__指向上一个节点来实现继承。  
    
&emsp;&emsp;所以，当你需要实现继承的时候只需要将节点的__proto__指向需要继承的父节点就可以了。这时你可能想到直接修改子节点的__proto__，像这样
    
```
child.prototype.__proto__ = Parent.prototype
```


  但是

![image.png](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/1e1b027b7d424f42928c34078359a341~tplv-k3u1fbpfcp-watermark.image?)

此时，你需要一个新的对象，这个对象的__proto__ 指向Parent.prototype，直接替换掉child.prototype即可。显而易见，这个对象当然就是父节点的实例对象

```
child.prototype = new Parent()
```

当然,这样不是最好的，会执行构造函数中不必要的操作，按照上边警告中的推荐：

```
child.prototype = Object.create(Parent.prototype)
```

至此，原型属性的继承已经实现了，但是还有实例属性，那就需要

```
function Child(){
    Parent.call(this)
    ...
}
```
这样，构造函数的实例属性和原型属性就都实现继承了


从这两个角度理解，是不是简单清晰，不要再纠结原型链和继承了。
