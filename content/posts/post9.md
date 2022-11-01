+++
title = "mvp——图形学基础"
image = "/images/post/person.png"
author = "Echo Guo"
date = 2022-07-16T14:49:24+08:00
description = "线性代数"
categories = ["线性代数"]
type = "post"

+++
**&emsp;&emsp;引擎推动的不是飞船而是宇宙。飞船压根就没动过。**


**一、 模型空间**  
&emsp;&emsp;Model Matrix将模型空间转换为世界空间

**二、世界空间**  
&emsp;&emsp;  View Matrix将世界空间转换为摄像空间

**三、摄像空间**  
&emsp;&emsp;Projection Matrix将摄像空间转换为剪裁空间  
**四、剪裁空间**  
&emsp;&emsp;这是一个中心点位于 (0, 0, 0)，角落范围在 (-1, -1, -1) 到 (1, 1, 1) 之间，2 个单位宽的立方体。该剪裁空间被压缩到一个二维空间并栅格化为图像。 

**五、GLSL表达**  
```
void main() {
  vUv = uv;
  u_color = color;
  vec4 projectedPosition = projectionMatrix * viewMatrix * modelMatrix * vec4(position, 1.0);
  
  gl_PointSize = 50.0;
  gl_Position = projectedPosition;
}
```
