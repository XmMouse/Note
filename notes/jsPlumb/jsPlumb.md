## 连线组件
#### 安装
#### 多示例模式
- 默认组册再windwow下
- var firstInstance = jsPlumb.getInstance();
#### ElementID
- 如果没有会手动添加
#### 方法参数
- NodeLists Selectors
- ElementIds
- Elements
- 以上三者的数组
#### z-index
- 所有要插入的element最好不要有层级
#### 添加容器组件
- 容器组件必须添加position:absoute 
````
var j = jsPlumb.getInstance({
  Container:"foo"
});
````
#### 某个元素可拖拽
- 通知刷新
````
myInstanceOfJsPlumb.draggable("elementId");
````
#### 停止绘图
- 批量操作
- 每次处理EndPoint Connection 都会重绘
````
jsPlumb.setSuspendDrawing(true);
...
- load up all your data here -
...
jsPlumb.setSuspendDrawing(false, true);// 第二个参数代表重绘所有 如果不使用重绘所有则使用jsPlumb.batch函数批量处理
````
#### 重绘所有
````
repaintEverything
````
