#### property
嵌入页面
- frameElement parent - 父窗口
- frameElement
- length
- frames - 子窗口
- self - 当前窗口
- top - 顶级窗口
- opener - 打开当前窗口的窗口
尺寸
- innerHeight-innerwidth viewPort高度(包括滚动条-一般值用户可以通过js或者css控制显示的去徐)
- outerHeight-outerwidth 整个窗口宽高
- pageXoffset-pageXoffset 文档在窗口左上角和右上角的偏移位置
- screenLeft-secreenTop 只是screenX-screenY的别名
- screenX-screenY 浏览器左边到操作系统作桌面的距离
- scrollX-scrollY 浏览器滚动的距离
存储
- indexDB
- localStorage
- sessionStorage
- applicationCache
- caches
控制台
- console
平台
- devicePixelRatio
- navigator
- screen
地址
- location-和document.location是同一个
历史
- history
全屏模式
- fullScreen 是否处于全屏模式
安全
- isSecureContext
- crypto 
    - subtle - 这个比较又用可以进行HASH
webComponents
- customElements
#### method
动画
- requestAnimationFrame-cancelAnimationFrame
空闲
- requestIdleCallback-cancelIdleCallback
事件捕获
- captureEvents
style
- getComputedStyle(element,pseudoElt)
coordinate system
- convertPointFromNodeToPage
- convertPointFromPageToNode
base-64
- 字符串编码的问题
    - btoa 字符串转base64(只能是ASCII字符串不能是中文encodeUrlComponent解决)
    - atob base64转字符串
createImageBitmap(image, sx, sy, sw, sh[, options]) 接口表示能够被绘制到 <canvas> 上的位图图像
- HTMLImageElement, SVGImageElement, HTMLVideoElement, HTMLCanvasElement, Blob, ImageData, ImageBitmap
- ImageBitmap
- ctx.drawImage
窗口控制
- minimize 最小化
- moveTo 最小化
- moveBy 最小化
- open 最小化
- close 最小化
iframe间通信  
通常iframe之间要通信只限于有相同的协议相同的域名相同的端口
- postMessage 绕过这种传统的机制
````
targetWindow.postMessage()
window.addEventListener("message", ()=>{}, false);
````