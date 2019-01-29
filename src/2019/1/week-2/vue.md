# vue笔记

## props

- 对于非props的特性, 在组件上(父)可以添加任意的特性, 最终会反应到这个组件的根实例上.
- 对与绝大多种特性来说, 从外部提供给组件的值会替换掉组件内部的值, 入 外部的`type="data"`替换掉`type="number"`.但是到了`style`和`class`时, vue会智能的进行合并
- 禁用特性继承, 可以在组件选项中用`inheritAttrs: false`
- 子组件想要获取vue根实例的数据可以使用: `this.$root.${name}`
- 访问子组件实例或子元素用 `ref`