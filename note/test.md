## 枚举

### 语法
- jdk5新增特性，是一种新的类型，是某种数据可能取值的集合
- enum 与 class、interface 具有相同地位；
- 可以继承多个接口；
- 可以拥有构造器、成员方法、成员变量；
- 默认继承 java.lang.Enum 类，所以不能继承其他父类；其中 java.lang.Enum 类实现了java.lang.Serializable 和 java.lang.Comparable 接口；
- 使用 **enum** 定义，默认使用 final 修饰，因此不能派生子类；
- 构造器默认使用 private 修饰，且只能使用 -private 修饰；
- 枚举类所有实例必须在第一行给出，默认添加 public static final 修饰，否则无法产生实例；
- 如果打算自定义自己的方法，那么必须在enum实例序列的最后添加一个**分号**。

### 示例代码
    enum Color {
        Red, Green, Blue, Yellow
    }

***

- hashMap底层原理............................................
- 反射机制
- 二分查找算法
- SQL优化
- JVM（）
- 锁：
- 单例模式
- 框架底层原理：mybatis一级缓存，二级缓存
