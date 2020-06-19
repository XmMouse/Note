## 启用
- display： grid
## container - 带有template和s
### grid-template-rows  grid-template-columns
- 值 - 轨道宽度
    - 常规长度单位 px em vh等 - 适用于固定布局 
    - fr 瓜分剩余单位 - 多边自适应布局
    - auto 填满剩余单位 - 单边自适应布局
    - repeate(number,mode) - 适用于子模块宽度固定布局
        - number 重复的次数 
        - model 空格分割的数组 
- 作用
    - 定义轨道宽度
    - 网格线的名称
        - 手动写出来
        - 省略-网格线的名称用数字表示
### grid-template-areas
- 作用
    - 命名轨道块
        - 名字相同的轨道块作为一个整体完成了span功能
### grid-row-gap/grid-column-gap
- 轨道间的空格
- grid-gap
    - 只有一个值
    - 有两个值
### justify-items/align-items
- 所有的单元格里边的内容与网格对齐
- 值
    - start
    - end
    - strech
    - center - 填满
### justify-content/align-content
- 用于网格区域大小小于网格容器
- 值
    - start
    - end
    - strech
    - space-around(两边空格是中间空格的一半)
    - space-between
    - space-evenly(两边空格和中间空格一样大)
### grid-auto-columns/grid-auto-rows
- 当定位网格超出网格容器时隐式网格如何被创建
- grid-auto-columns: 50px
### grid-auto-flow
- 指出没有手工指定网格位置时怎么定位布局
### grid
- <grid-template-rows> / <grid-template-columns> | <grid-auto-flow> [<grid-auto-rows> [ / <grid-auto-columns>]
## object
### grid-column-start/grid-column-end/grid-row-start/grid-row-end/grid-column/grid-row
- 此处定位使用的时网格线
- 值
    - <number> | <name> | span <number> | span <name> | auto ;
    - 上一条说明一种用法知道一条线可以向两边扩散
    - （number）网格县序号（span number）向后跨越指定格数start已知（3）向前跨越指定格数end已知道（4）跨越指定格数
### grid-area
### justify-self/align-self
    本身在单元格的对齐方式