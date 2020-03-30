# 函数式编成
## 函数事接口
    只有一个方法的接口 使用FunctionalInterface注解标注表示这是一个函数式接口3
## 使用方式
    ```
    Consumer consumer = () => {}
    Consumer consumer = () => sout()
    Consumer consumer = sou::t
    ```
## 提供的函数式接口
```
    Consumer
        accept
    Function
        apply
        compose
        andThen
    Predicate
        test
 ```
 ## 关键数据结构接口
```
    Stream 
    Optional
```   
