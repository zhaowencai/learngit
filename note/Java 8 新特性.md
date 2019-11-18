## Java 8 新特性

1. Map 中新增方法
   
- forEach() 结合lambda表达式使用的新型迭代方法
- getOrDefault(k, defaultValue) 取不到key对应的值则返回默认值
- replace(K key, V value)，只有在当前Map中key的映射存在时才用value去替换原来的值
- replace(K key, V oldValue, V newValue)，只有在当前Map中key的映射存在且等于oldValue时才用newValue去替换原来的值
- replaceAll(BiFunction<? super K,? super V,? extends V> function) 作用是对Map中的每个映射执行function指定的操作，并用function的执行结果替换原来的value
- **String::length**的语法形式叫做方法引用，

2. Streams API

- stream并不是某种数据结构，它只是数据源的一种视图
- Stream<T> **filter**(Predicate<? super T> predicate) 过滤器，返回一个只包含满足predicate条件元素的Stream
- void **forEach**(Consumer<? super E> action) 迭代
- Stream<T> **distinct**()，作用是返回一个去除重复元素之后的Stream
- **sorted**() 排序，自然顺序排序或者传入比较器