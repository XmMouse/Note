## 解决的问题
- 利用流布局实现动画不需要手动计算动画结果
## 原理
- 利用渲染总是在一次事件循环的最后执行
- 过程
> FLIP的思路掌握后，只要你知道元素动画前的状态和元素动画后的状态，你都可以轻松的通过「倒置状态」后，让它们做一个流畅的动画后到达目的地，并且此时的 DOM 状态是很干净的，而不是通过大量计算的方式强迫它从 0, 0 位移到 100, 100，并且让 DOM 样式上留下 transform: translate(100px, 100px) 类似的字样。
## Web Animation API
```
const keyframes = [
  {
    transform: `translate(${invert.left}px, ${invert.top}px)`,
  },
  { transform: "" },
]
const options = {
  duration: 300,
  easing: "cubic-bezier(0,0,0.32,1)",
}

const animation = currentRect.img.animate(keyframes, options)
```
## requestAnimationFremwork
- 略去