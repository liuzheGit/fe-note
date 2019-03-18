## css 关键帧动画 (水波纹)

```css
@keyframes m {
    0% {
        box-shadow: 0 0 0 0 rgba(52,223,165,.8);
        border-color: rgba(52,223,165,.6)
    }

    80% {
        box-shadow: 0 0 0 10px rgba(52,223,165,0)
    }

    100% {
        box-shadow: 0 0 0 0 rgba(52,223,165,0)
    }
}

/*use*/

*{
    animation: m 2s infinite;
}
```

## background-size:100% 和 cover区别

**100%和cover都是用于将图片扩大或缩放来适应整个容器**

background-size: 100% 100%; 按容器比例撑满, 图片变形;
background-size: cover; 把背景图片放大到适合元素容器的尺寸, 图片比例不便, 但是超出容器的部分会被裁掉;

当为百分比的时候, 100%和100% 100%也会显示不一样的效果:
background-size: 这个属性有两个值, 
第一个值(1)为x轴方向的缩放比例或者px, 第二个值为y轴方向的缩放比例或者px,
如果只写一个值(2), 则第二个默认值认为auto(根据图片比例)
- 第1种效果你一定会看到完整的背景图片，但是有可能被挤压(失去图片原来的比例)
- 第2种效果你不一定能看到完整的图片，但是图片的比例没有发生变化。

## :nth-child和:nth-of-type差异

> 其他: :last-child CSS 伪类 代表父元素的最后一个子元素。

`p:nth-child(2)`: 是p标签, 且此p标签是所有标签中的第二个元素
`p:nth-of-type(2)`: 是p标签, 只要是父级的第二个就行

## svg

- [SVG-Loaders](https://github.com/SamHerbert/SVG-Loaders)

## html

- marquee 标签做滚动字幕 