## 笔记

- 对象中的箭头函数中的this不是 对象的this, 而是对象所在的作用域


## 知识点


**关于requestAnimationFrame**
- [raf-plus库](https://github.com/weiying-shenzhen/raf-plus/blob/master/README_zh.md)是有管理队列功能的 window.requestAnimationFrame，他保证在同一帧内最多只会执行一次相同的函数。