## Lambda表达式

1. Java 8.0新特性，它允许我们将函数当成参数传递给某个方法，或者把代码本身当作数据处理。

2. 函数式接口在Java中是指：有且仅有一个抽象方法的接口。 函数式接口，即适用于函数式编程场景的接口。而Java中的函数式编程体现就是Lambda，所以函数式接口就是可以适用于Lambda使用的接口。

3. Lambda表达式的语法结构

- (参数列表，对应的是接口中对应的抽象方法的参数列表) -> {对抽象方法的实现}

4. 四大内置核心函数式接口
   
- Consumer<T> : 消费型接口（无返回值，有去无回）
    void accept(T t);
- Supplier<T> : 供给型接口
    T get();        
- Function<T,R> : 函数型接口
    R apply(T t);      
- Predicate<T> : 断言型接口
    boolean test(T t);
- 四大核心接口的-->扩展子接口

5. Lambda具体应用场景

- 使用() -> {} 替代匿名类
  
        public class ThreadDemo {
            public static void main(String[] s) {
                /**
                * 不使用Lambda
                */
                Thread t1 = new Thread(new Runnable() {
                    @Override
                    public void run() {
                        System.out.println("no use lambda");
                    }
                });
                /**
                * 使用Lambda,代码要简洁一些
                */
                Thread t2 = new Thread(() -> System.out.println("use lambda"));
        
                t1.run();
                t2.run();
        }

- 实际上Lambda的类型就是对应函数接口的类型
- 必须有相应的函数接口 + 类型推断机制 => 可以使用lambda表达式