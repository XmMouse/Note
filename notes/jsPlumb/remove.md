### 以任何方式使用了Element都必须调用以下方式清除
jsPlumb.remove（只是清除本身）
jsPlumb.empty（清除本身与相关的EndPoint ）
### remove Connection
````
var conn = jsPlumb.connect({ some params});
...
jsPlumb.detach(conn);
````
#### 删除元素上的所有连接
````
jsPlumb.deleteConnectionsForElement(el, [params])
````
#### 断开所有连接
````
jsPlumb.detachEveryConnection();
````
#### Remove Endpoint
````
var ep = jsPlumb.addEndpoint(someElement, { ... });
...
jsPlumb.deleteEndpoint(ep);
jsPlumb.deleteEveryEndpoint() = jsPlumb.reset
````