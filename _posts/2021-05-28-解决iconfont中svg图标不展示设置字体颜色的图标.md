---
layout: post
title:  "解决iconfont中svg图标不展示设置字体颜色的图标"
categories: iconfont
tags: iconfont
author: blockxia

---
* content
{:toc}



## 1. 设置style样式即可实现


```js
svg {
 fill:currentColor;
}
path{
  fill:unset;
}

```


