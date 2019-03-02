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