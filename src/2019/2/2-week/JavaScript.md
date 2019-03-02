## 笔记

- 对象中的箭头函数中的this不是 对象的this, 而是对象所在的作用域


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