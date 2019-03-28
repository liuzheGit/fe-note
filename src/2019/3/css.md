## 效果


- zichi的css-secrets[github](https://github.com/hanzichi/css-secrets)
- [css教程ruanyf](https://github.com/wangdoc/css-tutorial/tree/master/docs)

### 文字单行居中, 多行后左排列[jsbin](http://js.jirengu.com/filih/2/edit)
```css
	.wrap{
	  width: 200px;
	  border: 1px solid;
	  text-align: center;
	  
	}

	.content{
	  display: inline-block;
	  text-align: left;
	  border: 1px solid red;
	}
```

### 运用伪类和`vertical-align`实现重置居中[jsbin](http://js.jirengu.com/qavof/3/edit)
```css
	.wrap{
	  height: 300px;
	  border: 1px solid;
	  text-align: center;
	}
	.wrap::before{
	  content: '';
	  display: inline-block;
	  height: 100%;
	  vertical-align: middle;
	}
	.c{
	  text-align: center;
	  display: inline-block;
	  border: 1px solid red;
	  vertical-align: middle;
	}
```

### 运用`flex`和`margin`实现垂直主水平居中
```css
	.wrapper {
    height: 200px;
    background: red;
    display: flex;
  }

  .inner {
    padding: 50px;
    background: blue;

    margin: auto;
  }
```

### 伪元素实现右箭头 [jsbin](http://js.jirengu.com/tuzon/3/edit)
```html
  <div class="wrap">
      <div class="arrow"></div>
  </div>
```
```css
.arrow{
  width: 140px;
  height: 140px;
  background: rgba(0,0,0,0.4);
  border-radius: 50%;
  position: relative;
  transform: translateX(70px);
}
.arrow::after{
  content: '';
  width: 30px;
  height: 30px;
  position: absolute;
  left: 18%;
  top: 50%;
  color: white;
  border-right: 2px solid;
  border-top: 2px solid;
  transform: rotate(45deg) translate(-50%);
}

.arrow:hover{
  background: rgba(0,0,0,0.8);
}
.wrap{
  /* width: 300px; */
  display: inline-block;
  border: 1px solid;
  position: relative;
  overflow: hidden;
}
```