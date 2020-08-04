### box-shadown
- offset-x
- offset-y
- blur
- repand
### border-image
- 瓷砖切分九宫格后除去四个角落和中心-剩余上下左右四段边框
- border-image-source url()
- border-image-slice 上 有 下 左
- border-image-repeat 如何利用除了4个角以外的4部分填充边框
    - stretch 拉伸一个瓷砖
    - round 如果无法刚刚填满边框压缩所有瓷砖来填满
    - space 如果无法刚刚填满边框拉伸所有瓷砖来填满
    - repeat 如果无法刚刚填满边框多用一个瓷砖切割两边来完成
### 媒体插查询
媒体查询的含义：一种查询语句
#### html中可以使用媒体查询
一般用在style或者link上面确定要使用的css文件
#### js中使用
1. windown.matchMedia():MediaQueryList
2. MediaQueryList.matchs
3. MediaQueryList.addListener
#### 在css中使用
- @media deviceList (max-width:1200px) and (min-width: 600px)
#### 媒体查询的语法
- 媒体查询由两部分组成
    - 媒体类型
        - all (默认)
        - screen (屏幕)
        - speech (声音阅读器)
        - print (默认)
    - 媒体特查询
        - 括号+特性值 => (hover)
        - aspect-ratio视窗宽高比
        - hover 是否允许旋停
        - light-level 环境光亮度
        - orientation 视窗旋转方向
        - width 视口宽度
        - max-和min-可以确定中间的值可以使用>(大于)和<(小于)符号代替
    - 复杂媒体查询
        - and
        - or
        - not
### 字符
- @font-face{
    font-family:
    src: url() format()
}
### filter