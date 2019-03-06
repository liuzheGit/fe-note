# vue-router

- vue-router 中 规则是 : routes  而不是 routers

固定格式:

```js
var xxx = new VueRouter({
    routes: [
        {
            path: '/xx',
            name: 'xx',
            component: xx
        }
    ]
})

new Vue({
    router: xxx
})
```



[不错的vue小项目](http://kimy.coding.me/vue-assistant/#/) 来自 [掘金](https://juejin.im/post/59dae969f265da064c389644)



vue中 如果 props 如果是 `Object` 类型的 , 设置默认值得时候 需要 用 工厂函数

```js
props:{
  title: {
    type: Object,
    default: function(){
      return {
        title: '标题',
        color: '#000',
        size: 12
      }
    }
  }
}
```

## vue-cli@3

- 项目名不能有大写