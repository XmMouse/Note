### property
标签属性
- attributes
    - getNamedItem
    - setNamedItem
    - removeNamedItem
    - item
- classList
    - item(index)
    - contains
    - add
    - remove
    - replace
    - toggle
    - keys
    - values
    - entries
- className
- id
内容
- innerHTML
- outerHTML
- innerText
遍历
- nextElementSibling
- previousElementSibling 
尺寸
- clientHeight/clientWidth --- content+padding
- clientLeft/clientTop --- border-width + scrolling-width
- scrollHeight/scrollWidth
- scrollTop/scrollLeft
- scrollTopMax
标签
- tagName
### event
- onfullscreenchange
- onfullscreenerror
### method
web components
- attachShadow
- createShadowRoot
动画
- getAnimations
- animate
attributes
- getAttribute
- getAttributeNames
- hasAttributes 至少有一个属性
- hasAttribute
- removeAttribute
- toggleAttribute
- setAttribute
寻找
- closest 最近的祖先
- getElementsByClassName
- getElementsByTagName
- matches 判断当前element是否符合选择器
- querySelector
- querySelectorAll
节点操作
- insertAdjacentElement(position, element) --- beforebegin（本身前面）/afterbegin（第一个子孩子前面）/beforeend（最后一个子孩子后面）/afterend本省后边
- insertAdjacentHTML
- insertAdjacentText
- remove
尺寸
- getBoundingClientRect
- getClientRects - 内联元素
鼠标捕获
- requestPointerLock
- setCapture
- setPointerCapture
全屏
- requestPointerLock
滚动
- scrollIntoView 当前元素到窗口可视区域
- scroll
- scrollBy