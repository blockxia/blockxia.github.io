---
layout: post
title:  "vue-router"
categories: vue
tags: hash#
author: blockxia

---

* content
{:toc}

## 1.去除vue路由跳转地址栏后的哈希值#，我们只需要在路由跳转的管理文件router目录下的index.js中加上一句代码即可去掉哈希值#

```js

import Vue from 'vue'
//1.引入vue-router
import Router from 'vue-router'

import find from '../components/find'
import mall from '../components/mall'
import microshop from '../components/microshop'
import cloud from '../components/cloud'
import personalcenter from '../components/personalcenter'

//2.使用vue-router
Vue.use(Router)

//3.实例化router这个构造函数
let router = new Router({
//去掉地址中的哈希#
mode:"history",
//5.映射，什么样的地址跳转到什么样的page
routes:[
{
//根目录
path:'/',
name:'首页',
component:mall
},
{
//发现page
path:'/find',
name:'发现',
component:find
},
{
//微店page
path:'/microshop',
name:'购物袋',
component:microshop
},
{
//云仓page
path:'/cloud',
name:'云仓',
component:cloud
},
{
//我的page
path:'/personalcenter',
name:'我的',
component:personalcenter
}
]
});
//page跳转后title改变
router.afterEach(function (to) {
document.title = to.name
})
export default router

```

