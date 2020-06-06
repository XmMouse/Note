## 历史
- img - 占用网络资源多
- img-splite - 维护成本高（不好改变）
- font库 固定的字体图标（图标不全）！()[https://fontawesome.com/?from=io]
- iconfont  高大全的icon库
    - unicode 按字体的方式使用
    >@font-face {
   font-family: "iconfont";
   src: url('iconfont.eot'); /* IE9*/
   src: url('iconfont.eot#iefix') format('embedded-opentype'), /* IE6-IE8 */
   url('iconfont.woff') format('woff'), /* chrome, firefox */
   url('iconfont.ttf') format('truetype'), /* chrome, firefox, opera, Safari, Android, iOS 4.2+*/
   url('iconfont.svg#iconfont') format('svg'); /* iOS 4.1- */
 }
  > \<i class="iconfont">&#xe604;\</i>
- font-class  
基本原理还是使用unicode
    > ../font_8d5l8fzk5b87iudi.css

    > \<i class="iconfont icon-xxx">\</i>
- symbol - svg-icon
 - 支持多色图标了，不再受单色限制。
 - 支持像字体那样通过font-size,color来调整样式。
 - 支持 ie9+
 - 可利用CSS实现动画。
 - 减少HTTP请求。
 - 矢量，缩放不失真
 - 可以很精细的控制SVG图标的每一部分
  > ./iconfont.js
  > \<style type="text/css">
    .icon {
       width: 1em; height: 1em;
       vertical-align: -0.15em;
       fill: currentColor;
       overflow: hidden;
    }
\</style>
 > \<svg class="icon" aria-hidden="true">
    <use xlink:href="#icon-xxx"></use>
\</svg>
 - svg-sprite
 可以把多个svg合并为一个svg
 > 下来我们就要自己来制作 svg-sprite 了。这里要使用到 svg-sprite-loader 这个神器了， 它是一个 webpack loader ，可以将多个 svg 打包成 svg-sprite 。
我们来介绍如何在 vue-cli 的基础上进行改造，加入 svg-sprite-loader。
我们发现vue-cli默认情况下会使用 url-loader 对svg进行处理，会将它放在/img 目录下，所以这时候我们引入svg-sprite-loader 会引发一些冲突。
 > import '@/src/icons/qq.svg; //引入图标

\<svg><use xlink:href="#qq" />\</svg>  //使用图标
 - 自动导入
 require.context有三个参数：
 - svgo 压缩svg
自动导入svg