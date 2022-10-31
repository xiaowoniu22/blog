+++
title = "React setState合并和批量处理——React"
image = "/images/post/post-1.jpeg"
author = "Echo Guo"
date = 2020-03-14T14:49:24+08:00
description = "React learning"
categories = ["React Learning"]
type = "post"

+++
**State的更新什么时候是同步，什么时候是异步**

**1、 State的更新什么时候是同步，什么时候是异步。**  
&emsp;&emsp;正如我们所知，react中使用setState更新state,而state的更新大多数情况下是异步的，但是有些情况却是同步的。
 在React中，如果是由React引发的事件处理（比如通过onClick引发的事件处理），调用setState不会同步更新this.state，除此之外的setState调用会同步执行this.state。所谓“除此之外”，指的是绕过React通过addEventListener直接添加的事件处理函数，还有通过setTimeout/setInterval产生的异步调用。**

**二、为什么是异步**  
&emsp;&emsp;如果setState是同步更新state，而state的更新又会触发组件的重新渲染，那么每次setState都会渲染组件，这对性能是很大的消耗。所以react进行了setState的合并和批量延迟更新，正如官网所述：  

![](/images/post/post-2-1.jpg)

**三、如何实现setState的合并和批量延迟**  
&emsp;&emsp;查看react源码发现，代码中有一个变量锁isBatchingUpdates，isBatchingUpdates表示是否进行批量更新，初始化时默认为false，batchedUpdates方法会将isBatchingUpdates设为true  
```
var ReactDefaultBatchingStrategy = {
  isBatchingUpdates: false,

  batchedUpdates: function(callback, a, b, c, d, e) {
    var alreadyBatchingUpdates = ReactDefaultBatchingStrategy.isBatchingUpdates;

    ReactDefaultBatchingStrategy.isBatchingUpdates = true;

    if (alreadyBatchingUpdates) {
      return callback(a, b, c, d, e);
    } else {
      return transaction.perform(callback, null, a, b, c, d, e);
    }
  },
};

module.exports = ReactDefaultBatchingStrategy;
```  
为了合并setState，我们需要一个队列来保存每次setState的数据，然后在一段时间后，清空这个队列并渲染组件，这个队列就是dirtyComponents。当isBatchingUpdates为true时，将会执行 dirtyComponents.push(component); 将组件push到dirtyComponents队列。
 调用setState()时，其实已经调用了ReactUpdates.batchedUpdates，此时isBatchingUpdates便是true。


**至此，setState实现了合并和批量处理。**
