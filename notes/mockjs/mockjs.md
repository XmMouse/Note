### 语法
-'字段名|[重复或者范围]'：显示格式和内容
### String
- 'name|[repeat]': String
### number
- 'name|[range].[range]': placeHolder // 范围内取值
- 'name|[+step]': Number // 一次增加几个content
### Boolean
- 'name|[]': true|false
### Object
- 'name|[propertiesNumber]': {name:template}
### Array
- 'name|[contRange]': [template]
### Function
- 'name': function(){this} // 执行该function
### RegExp
- 'name|[repeat]': Regex
### Path
- 从模板路径生成新的数据
- 路径分类
    1. @/ 绝对路径
    2. @../ 相对路径
- Absolute Path
````
Mock.mock({
  "foo": "Hello",
  "nested": {
    "a": {
      "b": {
        "c": "Mock.js"
      }
    }
  },
  "absolutePath": "@/foo @/nested/a/b/c"
})
结果
{
  "foo": "Hello",
  "nested": {
    "a": {
      "b": {
        "c": "Mock.js"
      }
    }
  },
  "absolutePath": "Hello Mock.js"
}
````
- Relative Path
````
Mock.mock({
  "foo": "Hello",
  "nested": {
    "a": {
      "b": {
        "c": "Mock.js"
      }
    }
  },
  "relativePath": {
    "a": {
      "b": {
        "c": "@../../../foo @../../../nested/a/b/c"
      }
    }
  }
})
结果
{
  "foo": "Hello",
  "nested": {
    "a": {
      "b": {
        "c": "Mock.js"
      }
    }
  },
  "relativePath": {
    "a": {
      "b": {
        "c": "Hello Mock.js"
      }
    }
  }
}
````
## 数据占位符
- Random.boolean(min,max) - Mock.mock('@boolean')-Mock.mock('@boolean()')
- Random.natural(min, max) - Mock.mock('@natrual')-Mock.mock('@natrual()')
- Random.intger(min, max) - Mock.mock('@intger')-Mock.mock('@intger()')
- Random.float(min, max,dmin,dmax) - Mock.mock('@float')-Mock.mock('@float()')
- Random.character(pool,min, max) - Mock.mock('@character')-Mock.mock('@character()') // number upper lower symbol String
- Random.string(pool,min,max) - Mock.mock('@string')-Mock.mock('@string()')
- Random.range(start,stop,step) - Mock.mock('@range')-Mock.mock('@range()')
- Random.date(format) - Mock.mock('@date')-Mock.mock('@date(format)')
- Random.time(format) - Mock.mock('@time')-Mock.mock('@time(format)')
- Random.datetime(format) - Mock.mock('@datetime')-Mock.mock('@datetime(format)')
- Random.Image( size?, background?, foreground?, format?, text? ) - Mock.mock('@datetime')-Mock.mock('@datetime(format)')