## weui



### 表单输入

radio 不是隐藏的是用定位的:

```css
    position: absolute;
    left: -9999em;
```



input[type="radio"] 单选若想生效需要 多个设置同样的name属性值



input 的 pattern 属性规定用于验证输入字段的模式 如 : pattern="[0-9]*" 则输入除了0-9的 都会被忽略



:active 是一个链接被点击时候的伪类



**-webkit-tap-highlight-color** 是一个没有标准化的属性，能够设置点击链接的时候出现的高亮颜色。显示给用户的高光是他们成功点击的标识，以及暗示了他们点击的元素。



行内元素做 名词加解释的布局时 可以 名词 用 `float:left`  解释 用 `display:block`; 来占满空间, 这样既可以 做到一行显示,  此时 解释 再添加 `overflow:hidden;` 可以 空出开 名词的空间