## DOM和document是两个东西
DOM是文档对象模型document是文档，document属于DOM的一部分
## 继承关系
- EventTarget
- GlobalEventHandlers
    - Node
        - parentNode
            - Element
                - HTMLDocument
                - DivDocument
            - Document
                - HTMLDocument
    - windows
## EventTarget
- addEventListener
- removeEventListener
- dispathEvent
## GlobalEventHandlers
这个接口的作用是允许直接onXxx这种写法而不是addListener这种写法
## Node
只是和树形结构有关  
### property  
文档有关
- baseURI - 所处文档的URI
- ownDocument
遍历有关
- childNodes
- firstChild
- lastChild
- nextSibling
- previousSibling
- parentNode
- parentElement
节点本身有关
- nodeName
- isConnected
- nodeType
- textContent
### methods
操作节点
- appendChild
- cloneNode(deep)
- insertBefore()
- removeChild
- replaceChild
判断和对比
- contains 包含子节点
- hasChildNodes
- normalize 合并文本节点清空空白节点
获取
- getRootNode
## ParentNode
### property
- children
- firstElementChildren
- lastElementChildren
- childElementCount
### method
- append
- prepend
- querySelector
- querySelectorAll
## document
文档模型
### property
子元素
- all
- body
- head
- documentElement
- anchors - 锚点元素
- forms
- images
- links - 超链接
- styleSheetSets - 所有可用的样式列表
- selectedStyleSheetSet - 已使用样式列表
- cookie
- defaultView - windows
属性
- contentType
- dir
- domain
- location
- title
- URL
- readyState - loading正在加载 - interactive-js可用 complete - 完成
- documentUrl
- fonts
- hidden - 属于visibilityState的一个状态
- visibilityState - visible hidden prerender
- activeElement
- fullScreenElement
特殊
- timeline 继承来自AnimationTimeline控制动画的播放速度(firfox)
### methods
- 状态改变
    - readyStateChange
    - visibilityChange
    - DOMContentLoaded
以下是全局代理事件-是由其他元素产生的事件-不通过冒泡捕获  
- 粘贴板
    - cut
    - copy
    - plate
- 选择事件
    - selectechange
    - selectstart
- 动画事件
- 过渡事件
    - transitoncancel
    - transitonstart
    - transitonend
    - transitonrun
- 聚焦事件
    - focus
    - blur
- input事件
    - change
    - submit
    - input
    - valid
- dialog事件
    - close
- 拖拽事件
    - dragstart
    - dragend
    - dragenter
    - dragexit
    - dragover
    - drop
- video/audio事件
    - error
    - cancel
    - durationchange
    - canplay
    - canplaythrough
    - loadeddata
    - playing
    - ratechange
    - waiting
- 全屏
    - fullscreenchange
    - fullscreenchange
- 键盘
    - keydown
    - keyup
- 触摸事件
    - touchstart
    - touchsend
    - touchmove
    - touchcancel - 和touchend有执行顺序
- request
    - loadstart
    - loadend
    - progress
- 鼠标事件
    - click
    - dbclick
    - mousemove
    - mouseenter
    - mouseout
    - mouseleave
    - mouseover
- 鼠标无限滚动Pointer Lock API
    - Element.requestPointerLock()
    - Document.exitPointerLock()
- 通用指针系统
    - pointercancel
    - pointerdown
    - pointerup
    - pointerover
    - pointerout
    - pointermove
    - pointerlockchange
document该有的方法  
- create
    - createElement
    - createEvent
    - createRange
- query
    - getElementById
    - getElementsByName
    - getElementsByClassName
    - getElementsByTagName
## Element


