+++
title = "promise就是状态机—挑战一句话解释一个概念"
image = "/images/post/person.png"
author = "Echo Guo"
date = 2022-08-05T14:49:24+08:00
description = "本质"
categories = ["本质"]
type = "post"

+++
**&emsp;&emsp;我告诉你，Promise就是有限状态机，这样就容易理解了吧**


**一、 有限状态机**  
&emsp;&emsp;有限个状态  
&emsp;&emsp;链式绑定回调函数  
&emsp;&emsp;状态转移触发回调函数

**&emsp;&emsp;回调函数的绑定和触发也是订阅模式的思想**