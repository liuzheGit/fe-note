## 笔记

- 对象中的箭头函数中的this不是 对象的this, 而是对象所在的作用域
- 用Array.prototype.slice() 来获取数组的拷贝
- 想要实现链式调用, 需要在函数的方法中`return this`;
- 命名规范, 类的私有属性和方法前用 `_` 下划线区分;
- 用管道 `|` 修饰符可以实现`Math.floor` , 例如: `1.22 | 0  = 1`
**padStart() padEnd()**
- ES2017 引入了字符串补全长度的功能。如果某个字符串不够指定长度，会在头部或尾部补全。`padStart()`用于补全头部，`padEnd`用于补全尾部。
```javascript
	'x'.padStart(5, 'ab') // 'ababx'
	'x'.padStart(4, 'ab') // 'abax'
	'x'.padEnd(5, '0') //'50000'
	'x'.padEnd(6, '01')  //"x01010"
```
**a标签中 href="" 和 href="#" 和 href="javascript:void(0)"详解**

> 工作中如果想把a链接设置为空的一般有3中方法
- `a href=""`
	默认打开当前页面，会刷新一下。

- `a href="#"`
	浏览器地址栏会加#。不刷新页面，但会回到页面顶部。点击之后会回到页面最上边，原理：点击一个锚点，但是锚点为空，就默认回到顶部了

- `a href="javascript:void(0)"`
	void是一个操作符，这个操作符指定要计算一个表达式但是不返回值。如果在void中写入0，则什么也不执行，就形成了一个空链接。


## 知识点


**关于requestAnimationFrame**
- [raf-plus库](https://github.com/weiying-shenzhen/raf-plus/blob/master/README_zh.md)是有管理队列功能的 window.requestAnimationFrame，他保证在同一帧内最多只会执行一次相同的函数。

**用clearfix清楚浮动**
```css
.clearfix::after{
  content: '';
  display: block;  /* 而不是inline-block */
  clear: both;
}
```

## 库文件

- 灯箱效果 [magnificPopup](https://github.com/dimsemenov/Magnific-Popup)
- easy饼图数据 [easyPieChart](https://github.com/rendro/easy-pie-chart/)
- 神奇的动态布局 [Isotope](https://github.com/metafizzy/isotope)
- 无缝网格布局 [Packery](https://github.com/metafizzy/packery)
- 滚动切换视差 [localscroll](http://www.jq22.com/jquery-info1665)
- 视觉差特效引擎 [Parallax](http://www.htmleaf.com/Demo/201508152420.html)
- d动画插件库 [wow](https://github.com/matthieua/WOW) 依赖 animate.css
- 背景视频播放 [mb.YTPlayer](http://pupunzi.open-lab.com/mb-jquery-components/jquery-mb-ytplayer/)
- [better-scroll](https://github.com/ustbhuangyi/better-scroll): 提高滚动体验插件
	- [中文文档](https://ustbhuangyi.github.io/better-scroll/doc/zh-hans/options-advanced.html)


## 前端博客

**博友**
- [xdlmr](https://xdlmr.github.io/)
- [ky](https://yk1062008412.github.io/)
- [qi](https://github.com/QiShaoXuan/animate_resume_ts)


## Material组件

[Material-web](https://github.com/material-components/material-components-web)

[Vue组件](https://github.com/stasson/vue-mdc-adapter)


## OOP
- 用 `defineProperty` 修改 configurable 配置属性 为 false 的时候, 如果此时目标属性没有 , 则 之后在设置目标属性, 则无效
	如果之前的对象有目标属性,则 可以生效
	```js
		// 没目标属性	
		var person = {};
		Object.defineProperty(person, 'name', {
			configurable: false,
			value: 'lttztt'
		});
		
		person.name = 'jack';
		
		console.log(person.name)   // lttztt
		// 有目标属性
		var person = {
			name: 'jack'
		};
		Object.defineProperty(person, 'name', {
			configurable: false,
			value: 'lttztt'
		});
		
		person.name = 'tom';
		
		console.log(person.name)   // tom
	```
- 多次调用`Object.defineProperty` 修改同一个属性, 如果某次修改 `configurable: false`, 则之后的
	再次设置就会有限制;
- 访问器属性 `getter / setter` 只能通过 `Object.defineProperty` 来定义 (用get和set)
- 用 `newObject.constructor === 构造函数` 检测对象的类型
- 检测对象类型用 `newObject instanceof 构造函数`
- `__proto__` 是存在于 实例和 构造函数的原型对象之间的.
- 虽然实例中无法用`__proto__`, 但是判断 实例是否属于构造函数创建的可以用: 
	`Person.prototype.isPrototypeOf(person1)   // true` 代表是;
- 还有一个ES5新增的 `Object.getPrototypeOf()` 返回`__proto__`值, 例如:
	`Object.getPrototypeOf(person1) === Person.prototype // true`
	- 也就是说可以通过 `Object.getPrototypeOf()` 方便的取得实例对象的原型对象;
- `delete`操作符可以完全删除实例属性
- 使用 `hasOwmProterty`方法可以检测一个属性是存在于实例中, 还是原原型对象中;
- 使用 `hasPrototypeProperty(person, 'name')`方法可以判断 属性是否从存在于原型对象上;
- 原型的属性方法过多可以使用 `Person.prototype = {}`, 指向一个对象, 但此时使用 `person.constructor === Person // false`,
	如果要解决这个问题可以在 字面量 `{}`中 添加 `constructor: Perons,`
- 原型上的方法可是实时的反应在实例上, 但是 如果此时把 原型指向一个对象,则会改变这个动态性;
- js继承本质上是重写原型对象, 代之以一个新类型的实例
- 子类需要覆盖父类的方法的时候, 需要在重写原型之后进行
- 当继承的有引用类型的值的时候, 会导致子类的实例维护的是同一份引用类型的属性.
	- 解决: 子类的构造函数调用 父类的方法, 并且给当前this传给父类, `Animal.call(this)`;
	- 这样做的好处还有一个, 可以给父类传递参数
- 数组去重中用到: arr.indexOf(item) 小于0则不再数组中
- [ 图片知识 (全)](https://github.com/LiangJunrong/document-library/blob/master/other-library/Interview/PersonalExperience/Other-%E5%9B%BE%E7%89%87.md)



## [职业路线图](https://github.com/kamranahmedse/developer-roadmap)