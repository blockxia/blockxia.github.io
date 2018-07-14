## 1. 描述一下你的项目
	1)此项目为外卖Web App (SPA)
	2)包括商家, 商品, 购物车, 用户等多个子模块
	3)使用Vue全家桶+ES6+Webpack等前端最新最热的技术
	4)采用模块化、组件化、工程化的模式开发

## 2. 说说你的项目的技术选型
	1). 前端数据处理/交互/组件化: vue/vue-router/vuex/mint-ui/swiper
	2). 前后台交互: axios/postman/mockjs
	3). 模块化: es6/babel
	4). 项目构建/工程化: webpack/脚手架/eslint
	5). css预编译器: stylus

## 3. 什么是接口, 如何对接口
	1). 接口: url / 请求方式 / 请求参数格式 / 响应数据格式
	2). 对接口: 根据接口文档请求后台, 看真实接口与文档是否一致

## 4. 详细说明如何判断函数中的this
	1). 正常情况: 执行函数的方式决定了函数中的this
		直接调用: fn()       window
		new调用: new fn()   新创建的对象 
		对象调用: obj.fn()   obj对象
		call/apply调用: fn.call(obj)   第一个参数指定的对象
	2). 特别情况:
		bind()返回的函数: fn.bind(obj)()  第一个参数指定的对象
		箭头函数: 使用的外部的this(内部没有自己的this)
		回调函数
			定时器回调/ajax回调/数组遍历相关方法回调: window2
			dom事件监听回调: dom元素
			组件生命周期回调: 组件对象 

## 5. Vue的MVVM实现结构图
![](https://i.imgur.com/6o73Ujg.png)	

const func = (function (a) {
  this.a = a
  return function (a) {
    a += this.a
    return a
  }
})((function (a, b) {
  return a
})(1, 2))

console.log(func(4))
