记录JavaScript的知识


## 语法 api

### body.json()

Body  mixin 的 json() 方法使用一个 Response 流，并将其读取完成。它返回一个 promise ，解析结果是将文本体解析为 JSON。

## 脚手架工具

[Yeoman](https://yeoman.io/) 直接快速地生成一个最符合你的需求的项目。(待了解)


## webpack

### 解决自动在html写入单独文件
[web-webpack-plugin](https://github.com/gwuhaolin/web-webpack-plugin)


## js博客-github

- [jawil 玄学](https://github.com/jawil/blog)
- [mqyqingfeng](https://github.com/mqyqingfeng/Blog)
- [SunShinewyf](https://github.com/SunShinewyf/issue-blog)

## js面试题

```js
console.log(foo);

function foo(){
    console.log("foo");
}
var foo = 1;
```
会打印函数，而不是 undefined 。

这是因为在进入执行上下文时，首先会处理函数声明，其次会处理变量声明，如果如果变量名称跟已经声明的形式参数或函数相同，则变量声明不会干扰已经存在的这类属性。

## js正则的学习

https://github.com/jawil/blog/issues/20