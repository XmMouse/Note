# TypeScript
## 基本类型
1. boolean
2. number 5(10) 0x22(16) 0b(2) 0o(8)
3. string
4. [] Array
5. [] Tuple给数组每一个元素确定的类型(返回多个值的时候)
6. enum 给常量一个分组
7. any 跳过编译检查
8. void
9. null undefined
10. never 跑出错误的时候
11. Object
12. as <string>someValue 强制类型转换
## 申明变量
1. let
2. const
3. var
4. 解构
5. ...剩余变量 ...展开
6. 解构重命名 :
7. 结构默认值 =
8. 函数申明解构
```
type C = { a: string, b?: number }
function f({ a, b }: C): void {
    // ...
}
```
## 接口
1. interface
2. 可选属性 ？：
3. 只读属性 readonly
4. 可索引类型[index:string]: string 解决接口只限制部分问题
5. 数据传递类型
6. 可索引类型（可扩展）
7. 函数类型 定义个一个函数
8. 类类型implements
9. 接口可以继承
10. 类可以继承实现
## 类
1. class
2. 继承
3. public private readonly
4. 存取器
5. 静态属性
6. 抽象类
## 函数
1. 函数类型
2. 定义函数可以使用类型推断而不写函数类型
3. 可选参数，默认参数和剩余参数
4. this和箭头函数
```
函数的this指向问题
Function.call()第一个参数就是this的值只是和调用的地方有关和定义的地方无关
```
## 泛型
```
泛型的作用规定在某个区域（函数或者类）那些地方只能用相同的值
```
1. 泛型函数
2. 泛型类
3. 泛型约束 - 可以确定一部分<T extends Lengthwise>
## 枚举
```
用一个数据结构组织把常量分组
```
1. 数字枚举
2. 字符串枚举
2. 异构枚举
2. 枚举赋值可以使用之前的值进行计算
## 类型兼容
结构类型是一种只使用其成员来描述类型的方式。 它正好与名义（nominal）类型形成对比
## 交叉类型
1. 类似多继承
## 联合类型
2. a|b
3. 为了判断联合类型具体为哪个类型使用类型断言(<Fish>pet).swim
4. 自定义类保护
>function isFish(pet: Fish | Bird): pet is Fish {
    return (<Fish>pet).swim !== undefined;
}
5. 
> typeof x === "number"
6. 
>instanceof