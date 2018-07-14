---
layout: post
title:  "vuex的一些基本编码"
categories: code
tags:   vue-cli
author: blockxia
---

* content
{:toc}

## 1. 使用vuex的一些基本编码：
```
创建所有相关的模块: store/index|state|mutations|actions|getters|mutation-types
    设计state: 从后台获取的数据
    实现actions:
        定义异步action: async/await
        流程:　发ajax获取数据, commit给mutation
    实现mutations: 给状态赋值
    实现index: 创建store对象
    main.js: 配置store
	在组件中使用
		this.$store.dispatch()
		mapState()/mapGetters()/mapActions()
```






## 2. 模板中显示数据的来源：
```
data
	props
	computed: 根据data/props/vuex的state或getters计算产生

```
```js













