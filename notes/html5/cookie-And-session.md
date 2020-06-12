## cookie
### 可以由谁去设置
- 服务端的response头部 set-cookie
- 浏览器JS
### 谁在用
- 服务器从请求头里取出来使用
### 怎么确定发送那些cookie
- 发送当当前URL匹配的所有cookie
- 怎么匹配的 cookie的domain + path 就是完整的Path
### cookie的安全
- httpOnly js是否能访问
- secure 只有https才启用
- expires 删除时间
### cookie js
- document.cookie
## session
本质上就是一个sessionID 