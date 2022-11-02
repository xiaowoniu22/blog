+++
title = "我对前端性能的一点理解"
image = "/images/post/performance.jpg"
author = "Echo Guo"
date = 2022-09-10T14:49:24+08:00
description = "性能"
categories = ["性能"]
type = "post"

+++
**&emsp;&emsp;我对前端性能的一点理解**

大多数情况性能没那么重要，因为react已经够快了。而如何组织代码是重要的。

一、代码规范和编程习惯是有利于性能的，在编程过程中应该遵守。比如：  
&emsp;&emsp;1、不使用内联style  
&emsp;&emsp;2、减少reflow， reflow会引起repain，repaint是整个页面的重新渲染  

二、从工程话的角度优化性能，如gzip，dll等。就像前面说的，如何组织代码很重要    
三、有些优化方案不是绝对的，要看场景和项目规模，是发生了性能问题才去优化的（借助工具去检测性能）



