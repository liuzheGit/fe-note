## 知识点

- [impress.js](https://github.com/impress/impress.js) 一个使用3d效果的演示工具库
- [underscore源码分析阅读](https://github.com/hanzichi/underscore-analysis)
- [underscore的实用](https://www.cnblogs.com/zzsdream/p/6843864.html)
- `new Date()` 直接用于计算会变成时间戳哦
### event.currentTarget&&event.target
> target:是事件触发的元素， currentTarget: 是实际绑定的元素


## npm 方法

```
$ npm repo $name  打开$name的仓库地址(github)
$ npm 
```


### 写一个js方法返回字符串是否属于合法的ip地址:
```js
function checkIP(ip){
    let reg = /^(\d+)\.(\d+)\.(\d+)\.(\d+)$/;

    if(reg.test(ip)){
        if(RegExp.$1 < 256 && RegExp.$2 < 256 && RegExp.$3 < 256 && RegExp.$4 < 256){
        return true
      }else{
        return false;
      }
    }else{
        return false;
    }
}
// 此时没有考虑 010的情况
```

## js原生懒加载

方法要点:
1. 利用`img`标签的src从私有属性`data-xx`属性中动态的添加src的值;
2. 用`document.getBoundingClientRect()`获取元素的相对屏幕的各种值;
3. 利用 `window.addEventListener('scroll')`来监听每次的距离和 `window.innerHeiht`的对比
4. 节流来提高性能, 避免scroll触发加载img事件的多次触发;


## 小程序

- 如果 app.json 中没有配置页面 title显示不正确
1. 登录发送的数据
var data = {
	encrypteddata: getres.encryptedData,  // wx.getUserInfo success 返回的数据
	iv: getres.iv,  // wx.getUserInfo success 返回的数据
	code: res.code  // wx.login success 成功的数据
};

  // 
  clickKaodian() {
    wx.navigateTo({
      url: 'kaodian/index',
    })
  },
