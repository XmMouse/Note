# sass
## sass中的特殊符号
- : 赋值
- % 占位符选择器-只能被继承如果不被继承就不会被编译成css
- $ 变量符号
- & 父选择器
- #{} 模板字符串-将值编译为无符号的字符串作为css的编译值
## sass中的扩展
- @import @import "" 全局导入-局部混入
- @media 反向包含父容器
- @extend 使用向所有被继承选择器出现的地方添加同等一个选择器
## sass与scss
### 区别
sass使用无大括号无分号的格式但是保留了冒号Scss只是在css3的基础上扩展
### 转换
二者可以使用import相互引入sass-covert转换
## 特性
1. 完全兼容CSS3
2. 嵌套(css模块化)
3. 变量Sass核心用来约束全局一致性的问题
4. mixin()
5. 函数 模式计算-比如只能是8的倍数等
6. 控制指令，自定义输出格式
## Nested
- 选择器嵌套
- 属性嵌套(避免属性重复书写font backgound)
```
    .css3{
        font: {
            size: 24px
        }
    }
```
## 数据类型
显示类型
- 数字10 10px
- 字符串
- 颜色 
- 数组
---
编程类型
- 布尔值
- null 变量未赋值
- 数组 
- map
### 字符串
- 有符号的作为值
- 无符号的作为选择器（属性）
- red green solid none
### 数组
- 用来作为-css函数的输入 
- translate(1px,2px) 
- background green url;
## Boolean
- and not or
## 计算符号
- 计算符号连接的是有符号的字符串则进行计算
- 计算符号连接的是无符号的字符串则当成无符号的
## 变量
- $varible 
- !default 判断为null使用
## 导入与编译
- @import .css url() http:// 作为普通的css语句
- 默认导入编译
- 导入不编译命名scss文件前加_
- @import也可以在嵌套中使用
## @media
- 可以写在css内部然后便以后把父样式写入@media内部
## 指令
- @at-root 把指令的内容和父选择器写道根目录下
- @debug 输出
- @warn 输出
- @if @else if @else
- @for（范围） @each（枚举） 
- @while
- @media
- @extends 
- @mixin 定义混合可以定义参数
- @include 引用混合
- @function 定义一个函尽量只是作为数据类型的计算
## 输出格式
- ：nested
- ：expanded
- ：compact
- ：compressed
## sass
- 扩展了指令