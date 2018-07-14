---
layout: post
title:  "对象的创建模式"
categories: javascript
tags:  Es6
author: blockxia
---

* content
{:toc}


# 1. 对象的创建模式


## 1). Object构造函数模式
	var obj = {}
	obj.name = 'Tom'
	obj.setName = function(name){this.name=name}


## 2). 对象字面量模式
	var obj = {
		name : 'Tom',
		setName : function(name){this.name = name}
	}


## 3). 构造函数模式
	function Person(name, age) {
		this.name = name
		this.age = age
		this.setName = function(name){this.name=name}
	}
	new Person('tom', 12)


## 4). 构造函数+原型的组合模式
	function Person(name, age) {
		this.name = name
		this.age = age
	}
	Person.prototype.setName = function(name){this.name=name}
	new Person('tom', 12)


# 2. 继承模式


## 1). 原型链继承 : 得到方法
	function Parent(){}
	Parent.prototype.test = function(){}
	function Child(){}
	Child.prototype = new Parent() //子类原型指向父类的实例
	Child.prototype.constructor = Child //原型的构造器指向构造函数
	var child = new Child() 
	child.test() //调用父类型的方法


## 2). 借用构造函数 : 得到属性
	function Parent(xxx){this.xxx = xxx}
	Parent.prototype.test = function(){}
	function Child(xxx,yyy){
	  Parent.call(this, xxx) //借用父类型的构造函数 相当于:this.Parent(xxx)
	}
	var child = new Child('a', 'b')  //child.xxx为'a', 但child没有test()


## 3). 组合
	function Parent(xxx){this.xxx = xxx}
	Parent.prototype.test = function(){}
	function Child(xxx,yyy){
	  Parent.call(this, xxx) //借用构造函数   this.Parent(xxx)
	}
	Child.prototype = new Parent() //得到test()
	Child.proptotype.constructor = Child
	var child = new Child() //child.xxx为'a', 也有test()



# 3. 理解



## 1). 定义一个函数背后做了什么?
	创建一个Function的实例对象
	给对象添加prototype属性, 其值为object空对象(原型对象)
	给原型对象添加constructor属性, 指向当前函数对象
## 2). new一个对象背后做了些什么?
	创建一个新的空对象
	给对象设置__proto__, 值为构造函数对象的prototype属性值
	通过对象执行构造函数体(给对象添加属性/方法)


## 4. 编码实现: 根据一个一维数组生成一个二维数组(内部数组最大长度是6)
	const arr1 = [1, 3, 5, 7, 13, 9, 14, 12, 11, 9, 4, 2]
	const arr2 = []
	let smallArr = []
	const max = 6

	arr1.forEach(item => {

	  if(smallArr.length===max) {
	    smallArr = []
	  }

	  if(smallArr.length===0) {
	    arr2.push(smallArr)
	  }

	  smallArr.push(item)
	})
	console.log(arr2)



###最后给大家来个语法讲解，需要宝宝的可以参考
Markdown 语法简介
markdown 语法十分简单，非常有利于写作，这里做一个简单介绍，熟悉的读者可以跳过这一章节。

# 表示标题，## 表示2级标题，同理####表示4级标题

空行表示新的段落，如果不空行的话，markdown 认为是同一段落

[A](B) 这样样式表示为链接，A为你想要显示的文字，B为实际的链接

![A](B) 这种样式表示图片，A为图片的描述文字，B为图片链接

* 表示无序列表，1,2,3 表示有序列表

以上就是 Markdown 的基本语法。