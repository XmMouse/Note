## ecms
## 全局属性
- Infinity
- NaN
- undifined
- null
- globalthis
## 全局函数
- eval()
- uneval() 浏览器不支持
- isFinite():()=> x !== Infinity
- isNaN() 
- parseFloat 有非法省略 Vs Number() 非法报错
- parseInt(String, radix[2-36]) 多进制转换为十进制
- decodeURI()
- encodURI()
- decodeComponentURI()  
- encodeComponentURI()
```
encodeComponentURI和encodeURI的区别
component会编码URI链接有的特殊字符不干扰解析主干解析
```
## 基本对象
### Object
#### 创建对象
new Object Object.create() {}
### 遍历对象
- for in 遍历原型和可枚举
- for of 可迭代可枚举
- keys 可迭代可枚举
- getOwnPropertyNames 可枚举和不可枚举
- getOwnPropertySymbols
- getOwnPropertySymbols
#### Object函数方法
- assign(object,...object)
- Object.is() 解决NaN不想等问题
---
属性管理
- definePreperty(object, name , descriptor)
- definePerperties
- keys
- entries
- alues
- getOwnPerpertyDescriptor()
- getOwnPropertySymbols()
- getOwnPrepertyNames()
---
原型管理
- create(prop，propertiesObject)
- getPrototypeOf()
- setPrototypeOf()
---
状态管理
- freeze 不能增删查改
- isFrozen
- seal 不可新增删除属性不可配置只能在原有的基础上读写
- isSealed
- preventExtensions 不可扩展
- isExtensible
### Object.prototype







