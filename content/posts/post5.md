+++
title = "ARTS打卡计划第二周"
image = "/images/post/post-1.jpeg"
author = "Echo Guo"
date = 2020-03-22T14:49:24+08:00
description = "React learning"
categories = ["React Learning"]
type = "post"

+++
## 一、Algorithm  
[20. 有效的括号](https://leetcode-cn.com/problems/valid-parentheses/)
![](https://p1-jj.byteimg.com/tos-cn-i-t2oaga2asx/gold-user-assets/2020/3/22/17100c58110d1731~tplv-t2oaga2asx-image.image)
**我的思路：**  
字符串第一位入栈，之后的每一位依次和前一位匹配，匹配成功，出栈，不成功则入栈。最终，栈为空，则是有效括号，否则无效。
## 二、Review
[9 Tips for Building Awesome Reusable React Components](https://blog.bitsrc.io/9-tips-for-building-awesome-reusable-react-components-b91f4846a30a)  
9条编写完美可复用React组件的建议
1. Use TypeScript — avoid prop-types  
**使用TypeScript做类型检查，避免使用prop-types**  
TypeScript and prop-types are currently two of the most popular ways to type-check React code. The former validates types at compile-time, whereas the latter performs at runtime.  
**TypeScript and prop-types是目前React中最流行的类型检查方法，前者在编译时检查，而后者则是在运行时检查。**
2. Define Components (Not Just Props & Events)  
**定义组件（不只是props 和 Events）**
3. Write Your TS in a Way that Enables Auto Documentation  
**写TS时要启用文档自动生成功能**
4. Inherit Prop Types for Native-HTML-like Components
5. One Directory For Each Component  
**为组件编写目录**
6. Use Aliases
7. Use Enums (Instead of Multiple Booleans) 
**使用枚举值，而不是过多使用布尔值**
8. Set Defaults
9. Restrict styling with themes  
**通过主题限制组件的样式**  
To provide better predictability to your component’s behavior (including its visual appearance) limit the degree of freedom your component consumers have in overriding your component styling properties.  




## 三、Tip
使用gitbook serve 和gitbook build时莫名报错（之前一切正常），如图
![](https://p1-jj.byteimg.com/tos-cn-i-t2oaga2asx/gold-user-assets/2020/3/19/170f283c4f86cfec~tplv-t2oaga2asx-image.image)
解决方法是找到copyPluginAssets.js文件删除或注释第112行  
/.gitbook/versions/版本/lib/output/website/copyPluginAssets.js

![](https://p1-jj.byteimg.com/tos-cn-i-t2oaga2asx/gold-user-assets/2020/3/19/170f2873672d20a8~tplv-t2oaga2asx-image.image)

## 四、Share

[JS中的求值策略](https://juejin.im/post/6844904099616391182)