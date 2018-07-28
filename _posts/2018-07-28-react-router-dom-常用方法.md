---
layout: post
title:  "react-router-dom"
categories: react-router
tags: react-router
author: blockxia

---

* content
{:toc}



## 1. react-router-dom库(作用和API)
	1). 作用: 用来实现SPA
	2). API
		组件: HashRouter/BrowserRouter/Route/Switch/Redirect/Link/NavLink
		对象:所有的路由组件的props有几个属性:
			history(路由的管理对象): push()/replace()/goBack()/goForword()
			match: 请求路径中的参数数据
			location: pathname(当前请求的路由路径)

## 2. redux库(作用和API)
	1). 作用: 集中式管理多个组件共享的状态, 一般从后台获取的数据都会用redux管理
	2). API:
			createStore()
			combinReducers()
			applyMiddleware()
			store.getState()
			store.dispatch(action)
			store.subscribe(callback)

## 3. react-redux库(作用和API)
	1). 作用: 简化在组件中使用redux的编码
	2). 提供2个API
		<Provider store={store}>: 为所有容器组件提供全局的store对象
		connect(state=> ({xxx: state.xxx}), {action1, action2})(UI组件): 包装ui组件生成容器组件, 实现ui组件与redux的数据通信

## 4. 下面举例给大家举例，编写一个同步action和异步action
	const receiveUser = (user) => ({type: RECEIVE_USER, data: user})
	const getUser = () => {
		return async dispatch => {
			const response = await reqUser()
			const result = response.data
			if(result.code===0) {
				dispatch(receiveUser(result.data))
			}
		}
	}

## 5. chrome调试应用的常用功能(窗口)
	Elements: 查看DOM标签和样式
	Console: 查看打印和错误信息
	NetWork: 查看请求(url, 请求方式, 请求参数)和响应
	Application: 查看浏览器端存储(localStorage, cookie)
	Sources: debugger调试
	react: 查看react组件(state, props)

## 6. 后台路由回调函数处理的3个步骤

	1). 通过req读取请求参数数据
	2). 处理数据(与数据库交互)
	3). 通过res向浏览器端返回响应

## 7. async与await的理解和使用

	1). 理解: 同步编码方式实现异步ajax请求, 简化promise的使用
	2). 使用:
		在调用接口请求函数语句的左侧指定await, 直接接收异步返回的response
		在await所在的函数左侧指定async


## 8. react前后台应用整体结构图

![react前后台应用整体结构图](https://i.imgur.com/zfGZ7Eb.png)


## 9. 组件对象的3大属性
	1). state: 值为容器对象, 保存的是组件内可变的数据,组件根据state中的数据显示, 要更新界面只要更新state即可
	2). props: 值为容器对象, 保存的是从组件外传递过来的数据, 当前组件只读, 父组件修改了自动显示新数据
	3). refs: 值为容器对象, 保存的是n个有ref属性的dom元素对象, 属性名是ref指定的标识名称, 值为对应的dom元素