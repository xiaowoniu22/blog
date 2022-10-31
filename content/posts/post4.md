+++
title = "ARTS打卡计划第一周"
image = "/images/post/post-1.jpeg"
author = "Echo Guo"
date = 2020-03-15T14:49:24+08:00
description = "React learning"
categories = ["React Learning"]
type = "post"

+++
## 一、Algorithm  
[121. 买卖股票的最佳时机](https://leetcode-cn.com/problems/best-time-to-buy-and-sell-stock/solution/121-mai-mai-gu-piao-de-zui-jia-shi-ji-by-leetcode-/)  
本人的暴力解法：
![](https://p1-jj.byteimg.com/tos-cn-i-t2oaga2asx/gold-user-assets/2020/3/12/170cf010aac39dbe~tplv-t2oaga2asx-image.image)
最优解法： 

![](https://p1-jj.byteimg.com/tos-cn-i-t2oaga2asx/gold-user-assets/2020/3/12/170cf0a66cc9124b~tplv-t2oaga2asx-image.image)
## 二、Review
[4 Best Practices To Write Quality JavaScript Modules](https://dmitripavlutin.com/javascript-modules-best-practices/)  
总结：  
1、Prefer named exports  
**使用命名的exports代替default exports；**  
2、No work during import  
The module-level scope shouldn’t do heavy computation like parsing JSON, making HTTP requests, reading local storage, etc.  
**module作用域中不要进行JSON解析、http请求、读取本地存储等复杂计算**  
3、 Favor high cohesion modules  
**编写高内聚modules**  
4、Avoid long relative paths  
**避免使用过长相对路径**  
通过webpack或babel-plugin-module-resolver配置根路径的方式处理
## 三、Tip

![](https://p1-jj.byteimg.com/tos-cn-i-t2oaga2asx/gold-user-assets/2020/3/14/170d95eb1573bfc3~tplv-t2oaga2asx-image.image)
十分想吐槽一下，react-route为什么没有路由嵌套
## 四、Share
本周梳理了react中setState的异步机制和批量推迟更新机制  
[React setState合并和批量处理](https://juejin.im/post/6844904090103709704)
